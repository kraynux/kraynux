# プロジェクトのアーキテクチャ — Clean Architecture

**言語：**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

このドキュメントでは、プロジェクトがどのように構成されているか、なぜこの構成を選んだのか、各フォルダーに何が入っているのかを説明します。アプリケーションの仕組みを理解したい訪問者と、プロジェクトに貢献したり保守したりしたい開発者の両方を対象としています。

このアプリケーションは **Clean Architecture** に従っています。ソフトウェアの中核は、技術的な詳細、ユーザーインターフェース、外部依存から切り離されています。この分離により、プロジェクトは読みやすく、テストしやすく、保守しやすく、発展させやすくなります。

---

## 1. 基本原則

アプリケーションは複数のレイヤーに分かれており、それぞれが明確な役割を持っています。

中心となる考え方はシンプルです：

```text
インターフェースがアクションを要求する。
アプリケーションがそのアクションを調整する。
ドメインがビジネスルールを適用する。
ポートがアプリケーションに必要なものを定義する。
インフラストラクチャが具体的な実装を提供する。
```

そのため、プロジェクトの重要なロジックは次のものに直接依存しません：

- ターミナル；
- グラフィカルインターフェース；
- データベース；
- ネットワーク；
- ファイルシステム；
- 外部ライブラリ；
- システムツール。

この独立性により、ソフトウェアの一部を置き換えても、残りをすべて書き直す必要はありません。

---

## 2. 全体像

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              起動、ライフサイクル、依存性の注入
        ├── core/             横断的なケイパビリティ、enum、例外
        ├── domain/           純粋なビジネスロジック
        ├── application/      ユースケース：commands と queries
        ├── infrastructure/   バックエンド、ストレージ、エクスポート、ログ、システムプローブ…
        ├── ports/            Protocol / ABC の契約
        ├── interfaces/       CLI と TUI
        ├── plugins/          組み込み拡張
        └── shared/           パース、ネットワーク、整形、横断的ユーティリティ
```

---

## 3. 依存関係の図

依存関係は常に同じ方向に向かわなければなりません：

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

具体的には：

- `interfaces/` は `application/` を呼び出せます。
- `application/` は `domain/` を呼び出し、`ports/` で定義された契約を使えます。
- `domain/` は `application/`、`infrastructure/`、`interfaces/` のいずれにも依存しません。
- `infrastructure/` は `ports/` で定義された契約を実装します。
- `app/` はレイヤーを組み立て、必要な依存関係を提供します。

基本ルール：

> ドメインはインフラストラクチャを決して知らない。  
> インフラストラクチャはポートを知っているが、ドメインはインフラストラクチャを知らない。

---

## 4. `app/` フォルダー

### 役割

`app/` フォルダーはアプリケーションの **組み立て地点** です。

含まれるもの：

- アプリケーションの起動；
- ライフサイクル；
- 依存性注入のコンテナー；
- 動作に必要なオブジェクトの構築；
- 具体的な実装の選択；
- 設定の初期化；
- レイヤー間の接続。

### 責務の例

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| ファイル | 役割 |
|---|---|
| `bootstrap.py` | アプリケーションを起動し、起動するインターフェースを選ぶ |
| `container.py` | 依存関係を生成し、接続する |
| `lifecycle.py` | 起動、停止、後片付けを管理する |

### ルール

`app/` にはビジネスロジックを置きません。

次のことは決めません：

- 何がビジネスルールか；
- データをどう計算すべきか；
- リクエストをどう解析すべきか；
- ファイルをどうエクスポートすべきか。

既存のコンポーネントを組み立てるだけです。

---

## 5. `core/` フォルダー

### 役割

`core/` フォルダーにはプロジェクトの **横断的な語彙** が入っています。

複数のレイヤーで共有されるものの、それ自体はビジネスルールではない要素をまとめます。

含まれうるもの：

- ケイパビリティ；
- 列挙型；
- 定数；
- 横断的な例外；
- 共通の型；
- プラットフォーム情報；
- レベルや状態の定義。

### 例

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| ファイル | 役割 |
|---|---|
| `capabilities.py` | 利用可能または有効化可能なケイパビリティを記述する |
| `constants.py` | プロジェクトの定数を持つ |
| `enums.py` | 取りうる状態、種類、レベルを定義する |
| `exceptions.py` | 横断的なエラーを定義する |

### ルール

`core/` は軽量かつ安定していなければなりません。

含めてはいけないもの：

- 複雑なビジネスロジック；
- ネットワーク呼び出し；
- ディスクアクセス；
- ユーザーインターフェースのコード；
- 外部ライブラリへの直接依存。

---

## 6. `domain/` フォルダー

### 役割

`domain/` フォルダーは **プロジェクトの心臓部** です。

純粋なビジネスロジック、つまりアプリケーションが実際に何をするかを定義するルール、概念、計算が入っています。

含まれうるもの：

- エンティティ；
- 値オブジェクト（value object）；
- ポリシー；
- ビジネスルール；
- ドメインサービス；
- 計算；
- ビジネス上の検証；
- ビジネスデータモデル。

### 例

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| 要素 | 役割 |
|---|---|
| エンティティ | 同一性を持つビジネスオブジェクト |
| 値オブジェクト | 不変で検証済みの値 |
| ポリシー | 再利用可能なビジネスルール |
| ドメインサービス | 単一のエンティティに属さないビジネスロジック |

### 厳格なルール

`domain/` フォルダーは：

- ディスクにアクセスしない；
- ネットワーク呼び出しをしない；
- システムコマンドを実行しない；
- データベースにアクセスしない；
- ユーザーインターフェースを import しない；
- インフラストラクチャを import しない；
- 避けられる場合は外部の技術ライブラリに依存しない。

ドメインは、サーバー、ファイル、ネットワーク、インターフェースなしでテストできなければなりません。

---

## 7. `application/` フォルダー

### 役割

`application/` フォルダーはユースケースを調整します。

次の問いに答えます：

> 「ユーザーがこのアクションを要求したとき、何が起こるのか？」

含まれるもの：

- commands；
- queries；
- ユースケース；
- オーケストレーター；
- アクションハンドラー；
- ドメインとポートの間の調整。

### commands / queries の区別

| 種類 | 目的 | データを変更する |
|---|---|---|
| Command | アクションを実行する | はい |
| Query | 情報を読み取る、または計算する | いいえ |

例：

| Command | Query |
|---|---|
| 設定を適用する | 現在の設定を読む |
| 解析を開始する | 解析結果を取得する |
| レポートをエクスポートする | 利用可能な項目を一覧表示する |
| データを削除する | 履歴を参照する |

### 例

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### ルール

`application/` に含めないもの：

- ターミナルへの表示；
- Textual のインターフェース；
- Rich のコマンド；
- データベースへの直接アクセス；
- 外部ツールの直接呼び出し。

調整はしますが、技術的な詳細は実装しません。

---

## 8. `ports/` フォルダー

### 役割

`ports/` フォルダーは、アプリケーションが期待する **契約** を定義します。

ポートは **アプリケーションが何を必要としているか** を記述し、それをどう実装するかは強制しません。

一般的に含まれるもの：

- `Protocol`；
- 抽象クラス `ABC`；
- リポジトリのインターフェース；
- エクスポートのインターフェース；
- プローブのインターフェース；
- 外部サービスのインターフェース；
- ストレージのインターフェース。

### 例

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| ポート | 役割 |
|---|---|
| `Repository` | データを読み取る、または保存する |
| `Exporter` | 指定された形式で出力を生成する |
| `Probe` | システムやネットワークの情報を収集する |
| `Storage` | 永続化バックエンドを管理する |

### 概念的な例

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

この契約が言っていること：

> 「アプリケーションには、レポートをエクスポートできるオブジェクトが必要だ。」

言っていないこと：

- エクスポートが Markdown かどうか；
- エクスポートが JSON かどうか；
- ファイルがローカルに書き込まれるかどうか；
- エクスポートがネットワーク経由で送られるかどうか。

これらの選択は `infrastructure/` の役割です。

### ルール

ポートは契約であり、実装ではありません。

含めてはいけないもの：

- 複雑なビジネスロジック；
- ディスクアクセス；
- ネットワーク呼び出し；
- 具体的な実装；
- 外部ライブラリへの直接依存。

---

## 9. `infrastructure/` フォルダー

### 役割

`infrastructure/` フォルダーには、ポートの **具体的な実装** が入っています。

外部の世界と通信するレイヤーです。

含まれうるもの：

- ファイルアクセス；
- データベースアクセス；
- Markdown、JSON、CSV などへのエクスポート；
- ロギング；
- ネットワーク呼び出し；
- システムプローブ；
- 外部ツールの制御された実行；
- サードパーティライブラリ向けアダプター；
- リポジトリの実装；
- ストレージの実装。

### 例

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

| 要素 | 役割 |
|---|---|
| `sqlite_repository.py` | SQLite でリポジトリを実装する |
| `json_file_repository.py` | JSON ファイルでリポジトリを実装する |
| `markdown_exporter.py` | レポートを Markdown でエクスポートする |
| `json_exporter.py` | レポートを JSON でエクスポートする |
| `process_probe.py` | プロセスに関する情報を収集する |
| `filesystem_probe.py` | ファイルシステムに関する情報を収集する |
| `structured_logger.py` | 構造化ログを生成する |

### ルール

`infrastructure/` は、次のものに直接アクセスできる唯一のレイヤーです：

- ファイルシステム；
- ネットワーク；
- SQLite；
- 外部ライブラリ；
- システムツール；
- サブプロセス（必要かつ制御されている場合）。

この集約により、次のことが容易になります：

- テスト；
- セキュリティ監査；
- バックエンドの置き換え；
- 副作用の抑制。

---

## 10. `interfaces/` フォルダー

### 役割

`interfaces/` フォルダーには、ユーザーから見える入口が入っています。

次のものを明確に分けます：

- CLI；
- TUI；
- 将来の Web または API インターフェース。

### 構成

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

| インターフェース | 技術 | 役割 |
|---|---|---|
| `cli/` | Rich | コマンドラインインターフェース |
| `tui/` | Textual | ターミナル上の対話型インターフェース |

### CLI

CLI はコマンドラインインターフェースです。

次のことができます：

- アプリケーションを起動する；
- 特定のアクションを実行する；
- 結果を表示する；
- 作業を自動化する；
- ツールをスクリプトに組み込む；
- SSH 経由でアプリケーションをリモートで使う。

### TUI

TUI はターミナル上の対話型インターフェースです。

次のことができます：

- 機能間を移動する；
- 情報を表示する；
- アクションを実行する；
- 結果を参照する；
- すべてのコマンドを覚えなくてもアプリケーションを使う。

### ルール

インターフェースにはビジネスロジックを置きません。

インターフェースは：

- ユーザーの意図を受け取る；
- `application/` のユースケースを呼び出す；
- 結果を表示する；
- エラーを分かりやすいメッセージに変換する。

してはいけないこと：

- インフラストラクチャを直接呼び出す；
- サブプロセスを実行する；
- ファイルに直接アクセスする；
- ビジネスルールを持つ；
- `application/` のロジックを重複させる。

---

## 11. `plugins/` フォルダー

### 役割

`plugins/` フォルダーは **組み込み拡張** 専用です。

プロジェクトの中核を重くせずに機能を追加できます。

たとえばプラグインは次のことができます：

- エクスポート形式を追加する；
- プローブを追加する；
- コマンドを追加する；
- TUI 画面を追加する；
- 外部連携を追加する；
- オプションのケイパビリティを追加する。

### 原則

プラグインはプロジェクトの他の部分と同じルールに従わなければなりません：

- ポートを迂回しない；
- ドメインを直接変更しない；
- 明確な契約を通じて機能を公開する；
- アプリケーションを壊さずに無効化できる。

### 構成例

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### ルール

プラグインは拡張であり、裏口ではありません。

全体のアーキテクチャを尊重し、プロジェクトの中核との循環依存を作ってはいけません。

---

## 12. `shared/` フォルダー

### 役割

`shared/` フォルダーには、ドメインにもアプリケーションにもインフラストラクチャにも属さない横断的なユーティリティが入っています。

再利用可能な汎用関数をまとめます。

含まれうるもの：

- パース；
- ネットワークユーティリティ；
- 整形；
- テキスト処理；
- 日付ヘルパー；
- パスヘルパー；
- 汎用的な検証ユーティリティ；
- シリアライズヘルパー。

### 例

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| フォルダー | 役割 |
|---|---|
| `parsing/` | テキスト、JSON、YAML などの解析 |
| `network/` | 汎用的なネットワークユーティリティ |
| `formatting/` | 値、日付、サイズ、表の整形 |
| `utils/` | 横断的なユーティリティ関数 |

### ルール

`shared/` を何でも放り込むフォルダーにしてはいけません。

ユーティリティを `shared/` に置くのは、次の条件を満たす場合だけです：

- 再利用できる；
- 汎用的である；
- 特定のユースケースに依存しない；
- 複数のレイヤーで役立つ。

---

## 13. 責務のまとめ

| フォルダー | 主な役割 | 依存してよいもの | 依存してはいけないもの |
|---|---|---|---|
| `app/` | アプリケーションを組み立てて起動する | すべてのレイヤー | — |
| `core/` | 語彙、定数、enum、例外 | 必要なら `shared/` | `infrastructure/`, `interfaces/` |
| `domain/` | 純粋なビジネスロジック | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | ユースケースを調整する | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | 契約を定義する | 必要なら `domain/` | `infrastructure/`, `interfaces/` |
| `infrastructure/` | ポートを実装し、外部と通信する | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | ユーザーとやり取りする | `application/`, `core/` | `infrastructure/` への直接依存 |
| `plugins/` | 拡張を追加する | 拡張の種類による | アーキテクチャの迂回 |
| `shared/` | 横断的なユーティリティ | ビジネスレイヤーには依存しない | 特定のビジネスロジック |

---

## 14. アクションの流れの例

ユーザーがレポートを Markdown でエクスポートするよう要求した場合を考えます。

```text
1. ユーザーが CLI コマンドを実行する。

2. interfaces/cli/
   コマンドとそのオプションを受け取る。

3. interfaces/cli/
   application/ の対応するユースケースを呼び出す。

4. application/
   意図を検証し、アクションを準備する。

5. application/
   ドメインを使ってレポートを組み立てる、または検証する。

6. application/
   ReportExporter ポートを通じてエクスポートを要求する。

7. infrastructure/
   MarkdownExporter の実装を提供する。

8. infrastructure/
   Markdown ファイルをディスクに書き込む。

9. interfaces/cli/
   ユーザーに結果を表示する。
```

簡略図：

```text
CLI
 ↓
Application
 ↓
Domain
 ↓
Port Exporter
 ↓
Infrastructure Markdown
 ↓
Markdown ファイル
```

---

## 15. なぜこのアーキテクチャなのか？

### 読みやすさ

各フォルダーの役割は 1 つだけなので、機能を追加・修正する場所を見つけやすくなります。

### テストのしやすさ

ドメインは、インターフェース、データベース、ネットワークアクセスなしでテストできます。

### 保守性

インターフェース、ストレージ、外部ツールを変更しても、ビジネスロジックを書き直す必要があってはなりません。

### セキュリティ

ファイル、ネットワーク、サブプロセス、データベースといった機密性の高いアクセスは `infrastructure/` に集約されています。これにより監査と管理が容易になります。

### 拡張性

次のものを追加できます：

- 新しいインターフェース；
- 新しいエクスポート形式；
- 新しいストレージバックエンド；
- 新しいプラグイン；
- 新しいシステムプローブ；

いずれもビジネスの中核を変更せずに行えます。

### 移植性

アプリケーションは特定の技術に縛られることなく、別の環境、システム、操作方法へと発展できます。

---

## 16. 覚えておきたいルール

- ドメインは純粋である。
- アプリケーションは調整する。
- ポートは必要なものを宣言する。
- インフラストラクチャは実装する。
- インターフェースは表示し、入力を受け取る。
- `app/` は組み立てる。
- `core/` と `shared/` は横断的な語彙とユーティリティを提供する。
- プラグインはアーキテクチャを迂回せずに拡張する。

ひとことで言えば：

> **アプリケーションは、何をするか、どのようにするか、ユーザーがどう使うかを分離する。**
