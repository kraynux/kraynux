# 项目架构 — Clean Architecture

本文档说明项目的组织方式、选择这种组织方式的原因，以及每个目录所包含的内容。它既面向希望了解应用程序整体运作方式的访问者，也面向希望参与开发或维护该应用程序的开发者。

本应用程序遵循 **Clean Architecture（整洁架构）**：软件核心与技术细节、用户界面以及外部依赖相互隔离。这种分离使项目更易于阅读、测试、维护和演进。

---

## 1. 总体原则

应用程序被划分为多个层次，每一层都有明确的职责。

核心思想很简单：

```text
接口请求执行一个操作。
应用程序对该操作进行编排。
领域层应用业务规则。
端口定义应用程序所需的能力。
基础设施提供具体实现。
```

因此，项目中的重要逻辑不会直接依赖于：

- 终端；
- 图形界面；
- 数据库；
- 网络；
- 文件系统；
- 外部库；
- 系统工具。

这种独立性使我们可以替换软件的某一部分，而无需重写其他所有部分。

---

## 2. 总体结构

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              引导启动、生命周期和依赖注入
        ├── core/             跨层能力、枚举和异常
        ├── domain/           纯业务逻辑
        ├── application/      用例：commands 和 queries
        ├── infrastructure/   后端、存储、导出、日志、系统探测……
        ├── ports/            Protocol / ABC 契约
        ├── interfaces/       CLI 和 TUI
        ├── plugins/          内置扩展
        └── shared/           解析、网络、格式化和跨层工具
```

---

## 3. 依赖关系图

依赖关系必须始终朝同一方向流动：

```text
interfaces
    ↓
application
    ↓
domain
    ↑
ports
    ↑
infrastructure
```

实际规则如下：

- `interfaces/` 可以调用 `application/`。
- `application/` 可以调用 `domain/`，并使用 `ports/` 中定义的契约。
- `domain/` 不依赖 `application/`、`infrastructure/` 或 `interfaces/`。
- `infrastructure/` 实现 `ports/` 中定义的契约。
- `app/` 负责组装各层，并提供所需的依赖。

核心规则：

> 领域层永远不了解基础设施。  
> 基础设施了解端口，但领域层不了解基础设施。

---

## 4. `app/` 目录

### 职责

`app/` 目录是应用程序的**组装点**。

它包含：

- 应用程序启动；
- 生命周期管理；
- 依赖注入容器；
- 构建运行所需的对象；
- 选择具体实现；
- 初始化配置；
- 建立各层之间的连接。

### 职责示例

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| 文件 | 职责 |
|---|---|
| `bootstrap.py` | 启动应用程序，并选择要启动的界面 |
| `container.py` | 创建并连接依赖 |
| `lifecycle.py` | 管理启动、停止和清理 |

### 规则

`app/` 不包含业务逻辑。

它不决定：

- 什么是业务规则；
- 数据应如何计算；
- 请求应如何分析；
- 文件应如何导出。

它只负责组装现有组件。

---

## 5. `core/` 目录

### 职责

`core/` 目录包含项目的**跨层通用词汇**。

它汇集了由多个层次共享、但其本身并不构成业务规则的元素。

它可以包含：

- 能力；
- 枚举；
- 常量；
- 跨层异常；
- 通用类型；
- 平台信息；
- 级别或状态定义。

### 示例

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| 文件 | 职责 |
|---|---|
| `capabilities.py` | 描述可用或可启用的能力 |
| `constants.py` | 包含项目常量 |
| `enums.py` | 定义可能的状态、类型或级别 |
| `exceptions.py` | 定义跨层异常 |

### 规则

`core/` 必须保持轻量且稳定。

它不得包含：

- 复杂的业务逻辑；
- 网络调用；
- 磁盘访问；
- 用户界面代码；
- 对外部库的直接依赖。

---

## 6. `domain/` 目录

### 职责

`domain/` 目录是项目的**核心**。

它包含纯业务逻辑：真正定义应用程序功能的规则、概念和计算。

它可以包含：

- 实体；
- 值对象；
- 策略；
- 业务规则；
- 领域服务；
- 计算；
- 业务验证；
- 业务数据模型。

### 示例

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| 元素 | 职责 |
|---|---|
| 实体 | 具有身份的业务对象 |
| 值对象 | 不可变且经过验证的值 |
| 策略 | 可复用的业务规则 |
| 领域服务 | 不属于单一实体的业务逻辑 |

### 严格规则

`domain/` 目录：

- 不进行任何磁盘访问；
- 不进行任何网络调用；
- 不执行系统命令；
- 不访问数据库；
- 不导入用户界面；
- 不导入基础设施；
- 在可能避免的情况下，不依赖外部技术库。

领域层必须能够在没有服务器、文件、网络和界面的情况下进行测试。

---

## 7. `application/` 目录

### 职责

`application/` 目录负责编排用例。

它回答以下问题：

> “当用户请求执行此操作时，会发生什么？”

它包含：

- commands；
- queries；
- 用例；
- 编排器；
- 操作处理器；
- 领域层与端口之间的协调逻辑。

### commands 与 queries 的区别

| 类型 | 目的 | 是否修改数据 |
|---|---|---|
| Command | 执行一个操作 | 是 |
| Query | 读取或计算信息 | 否 |

示例：

| Command | Query |
|---|---|
| 应用配置 | 读取当前配置 |
| 启动分析 | 获取分析结果 |
| 导出报告 | 列出可用项目 |
| 清除数据 | 查看历史记录 |

### 示例

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### 规则

`application/` 不包含：

- 终端输出；
- Textual 界面；
- Rich 命令；
- 对数据库的直接访问；
- 对外部工具的直接调用。

它负责协调，但不实现技术细节。

---

## 8. `ports/` 目录

### 职责

`ports/` 目录定义应用程序所期望的**契约**。

端口描述的是**应用程序需要什么**，而不规定它必须如何实现。

它通常包含：

- `Protocol` 定义；
- 抽象 `ABC` 类；
- 仓库接口；
- 导出接口；
- 探测接口；
- 外部服务接口；
- 存储接口。

### 示例

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| 端口 | 职责 |
|---|---|
| `Repository` | 读取或存储数据 |
| `Exporter` | 以指定格式生成输出 |
| `Probe` | 收集系统或网络信息 |
| `Storage` | 管理持久化后端 |

### 概念示例

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

该契约表示：

> “应用程序需要一个能够导出报告的对象。”

它并不说明：

- 导出是否采用 Markdown 格式；
- 导出是否采用 JSON 格式；
- 文件是否写入本地；
- 导出是否通过网络发送。

这些选择属于 `infrastructure/`。

### 规则

端口是契约，而不是实现。

它们不得包含：

- 复杂的业务逻辑；
- 磁盘访问；
- 网络调用；
- 具体实现；
- 对外部库的直接依赖。

---

## 9. `infrastructure/` 目录

### 职责

`infrastructure/` 目录包含端口的**具体实现**。

它是与外部世界通信的层次。

它可以包含：

- 文件访问；
- 数据库访问；
- Markdown、JSON、CSV 或其他格式的导出；
- 日志记录；
- 网络调用；
- 系统探测；
- 受控执行外部工具；
- 第三方库适配器；
- 仓库实现；
- 存储实现。

### 示例

```text
infrastructure/
├── storage/
│   ├── sqlite_repository.py
│   └── json_file_repository.py
├── export/
│   ├── markdown_exporter.py
│   └── json_exporter.py
├── system/
│   ├── process_probe.py
│   └── filesystem_probe.py
└── logging/
    └── structured_logger.py
```

| 元素 | 职责 |
|---|---|
| `sqlite_repository.py` | 使用 SQLite 实现仓库 |
| `json_file_repository.py` | 使用 JSON 文件实现仓库 |
| `markdown_exporter.py` | 将报告导出为 Markdown |
| `json_exporter.py` | 将报告导出为 JSON |
| `process_probe.py` | 收集进程信息 |
| `filesystem_probe.py` | 收集文件系统信息 |
| `structured_logger.py` | 生成结构化日志 |

### 规则

`infrastructure/` 是唯一被允许直接访问以下内容的层次：

- 文件系统；
- 网络；
- SQLite；
- 外部库；
- 系统工具；
- 子进程（仅在必要且受控时）。

这种集中化有助于：

- 测试；
- 安全审计；
- 替换后端；
- 限制副作用。

---

## 10. `interfaces/` 目录

### 职责

`interfaces/` 目录包含用户可见的入口点。

它明确区分：

- CLI；
- TUI；
- 未来可能的 Web 或 API 界面。

### 结构

```text
interfaces/
├── cli/
│   ├── main.py
│   ├── commands/
│   └── rendering/
└── tui/
    ├── app.py
    ├── screens/
    └── widgets/
```

| 界面 | 技术 | 职责 |
|---|---|---|
| `cli/` | Rich | 命令行界面 |
| `tui/` | Textual | 交互式终端界面 |

### CLI

CLI 是命令行界面。

它允许用户：

- 启动应用程序；
- 执行特定操作；
- 显示结果；
- 自动化任务；
- 将工具集成到脚本中；
- 通过 SSH 远程使用应用程序。

### TUI

TUI 是终端中的交互式界面。

它允许用户：

- 浏览功能；
- 查看信息；
- 执行操作；
- 查看结果；
- 无需记住所有命令即可使用应用程序。

### 规则

界面不包含业务逻辑。

它们：

- 接收用户意图；
- 调用 `application/` 中的用例；
- 显示结果；
- 将错误转换为易于理解的消息。

它们不得：

- 直接调用基础设施；
- 执行子进程；
- 直接访问文件；
- 包含业务规则；
- 复制 `application/` 中的逻辑。

---

## 11. `plugins/` 目录

### 职责

`plugins/` 目录保留给**内置扩展**。

它允许在不使项目核心过载的情况下添加功能。

例如，插件可以：

- 添加一种导出格式；
- 添加一个探测器；
- 添加一个命令；
- 在 TUI 中添加一个界面；
- 添加外部集成；
- 添加可选能力。

### 原则

插件必须遵守与项目其他部分相同的规则：

- 不绕过端口；
- 不直接修改领域层；
- 通过明确的契约公开其功能；
- 在不破坏应用程序的情况下保持可禁用状态。

### 可能的结构

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### 规则

插件是扩展，而不是后门。

它必须遵循整体架构，并且不得与项目核心形成循环依赖。

---

## 12. `shared/` 目录

### 职责

`shared/` 目录包含既不属于领域层、也不属于应用层或基础设施层的跨层工具。

它汇集可复用的通用函数。

它可以包含：

- 解析；
- 网络工具；
- 格式化；
- 文本处理；
- 日期辅助函数；
- 路径辅助函数；
- 通用验证工具；
- 序列化辅助函数。

### 示例

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| 目录 | 职责 |
|---|---|
| `parsing/` | 解析文本、JSON、YAML 或其他格式 |
| `network/` | 通用网络工具 |
| `formatting/` | 格式化值、日期、大小或表格 |
| `utils/` | 跨层工具函数 |

### 规则

`shared/` 不应变成一个杂物箱。

只有当某个工具满足以下条件时，才应放入 `shared/`：

- 可复用；
- 通用；
- 独立于特定用例；
- 对多个层次有用。

---

## 13. 职责摘要

| 目录 | 主要职责 | 可以依赖 | 不得依赖 |
|---|---|---|---|
| `app/` | 组装并启动应用程序 | 所有层次 | — |
| `core/` | 词汇、常量、枚举和异常 | 必要时可依赖 `shared/` | `infrastructure/`、`interfaces/` |
| `domain/` | 纯业务逻辑 | `core/` | `application/`、`infrastructure/`、`interfaces/` |
| `application/` | 编排用例 | `domain/`、`ports/`、`core/` | `infrastructure/`、`interfaces/` |
| `ports/` | 定义契约 | 必要时可依赖 `domain/` | `infrastructure/`、`interfaces/` |
| `infrastructure/` | 实现端口并与外部世界通信 | `ports/`、`domain/`、`core/`、`shared/` | `interfaces/` |
| `interfaces/` | 与用户交互 | `application/`、`core/` | 直接依赖 `infrastructure/` |
| `plugins/` | 添加扩展 | 取决于扩展类型 | 绕过架构 |
| `shared/` | 跨层工具 | 不依赖业务层 | 特定业务逻辑 |

---

## 14. 操作流程示例

以用户请求将报告导出为 Markdown 为例。

```text
1. 用户执行一条 CLI 命令。

2. interfaces/cli/
   接收命令及其选项。

3. interfaces/cli/
   调用 application/ 中对应的用例。

4. application/
   验证用户意图并准备操作。

5. application/
   使用领域层构建或验证报告。

6. application/
   通过 ReportExporter 端口请求导出。

7. infrastructure/
   提供 MarkdownExporter 实现。

8. infrastructure/
   将 Markdown 文件写入磁盘。

9. interfaces/cli/
   向用户显示结果。
```

简化示意图：

```text
CLI
 ↓
Application
 ↓
Domain
 ↓
Exporter Port
 ↓
Markdown Infrastructure
 ↓
Markdown File
```

---

## 15. 为什么采用这种架构？

### 可读性

每个目录都有唯一职责，因此更容易找到应添加或修复功能的位置。

### 可测试性

领域层可以在没有界面、数据库或网络访问的情况下进行测试。

### 可维护性

修改界面、存储方式或外部工具时，不应需要重写业务逻辑。

### 安全性

敏感访问——文件、网络、子进程、数据库——都集中在 `infrastructure/` 中。这便于审计和控制。

### 可演进性

可以添加：

- 新界面；
- 新导出格式；
- 新存储后端；
- 新插件；
- 新系统探测；

而无需修改业务核心。

### 可移植性

应用程序可以演进到其他环境、系统或交互模式，而不与某项特定技术绑定。

---

## 16. 需要记住的规则

- 领域层是纯粹的。
- 应用层负责编排。
- 端口声明需求。
- 基础设施负责实现。
- 界面负责显示和收集。
- `app/` 负责组装。
- `core/` 和 `shared/` 提供跨层词汇和工具。
- 插件在不绕过架构的情况下进行扩展。

用一句话概括：

> **应用程序将“它做什么”、“它如何做”以及“用户如何使用它”分离开来。**
