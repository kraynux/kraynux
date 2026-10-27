# 프로젝트 아키텍처 — Clean Architecture

**언어:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

이 문서는 프로젝트가 어떻게 구성되어 있는지, 왜 이런 구성을 선택했는지, 각 폴더에 무엇이 들어 있는지를 설명합니다. 애플리케이션의 동작 방식을 이해하고 싶은 방문자와, 프로젝트에 기여하거나 유지보수하려는 개발자 모두를 위한 문서입니다.

이 애플리케이션은 **Clean Architecture**를 따릅니다. 소프트웨어의 핵심은 기술적 세부 사항, 사용자 인터페이스, 외부 의존성으로부터 분리되어 있습니다. 이러한 분리 덕분에 프로젝트를 읽고, 테스트하고, 유지보수하고, 발전시키기가 쉬워집니다.

---

## 1. 기본 원칙

애플리케이션은 여러 계층으로 나뉘며, 각 계층은 명확한 역할을 가집니다.

핵심 아이디어는 간단합니다:

```text
인터페이스가 작업을 요청한다.
애플리케이션이 그 작업을 조율한다.
도메인이 비즈니스 규칙을 적용한다.
포트가 애플리케이션에 필요한 것을 정의한다.
인프라스트럭처가 구체적인 구현을 제공한다.
```

따라서 프로젝트의 중요한 로직은 다음에 직접 의존하지 않습니다:

- 터미널;
- 그래픽 인터페이스;
- 데이터베이스;
- 네트워크;
- 파일 시스템;
- 외부 라이브러리;
- 시스템 도구.

이러한 독립성 덕분에 나머지를 모두 다시 작성하지 않고도 소프트웨어의 일부를 교체할 수 있습니다.

---

## 2. 전체 구조

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              부트스트랩, 생명주기, 의존성 주입
        ├── core/             공통 capability, enum, 예외
        ├── domain/           순수 비즈니스 로직
        ├── application/      유스케이스: commands 와 queries
        ├── infrastructure/   백엔드, 저장소, 내보내기, 로그, 시스템 프로브…
        ├── ports/            Protocol / ABC 계약
        ├── interfaces/       CLI 와 TUI
        ├── plugins/          내장 확장 기능
        └── shared/           파싱, 네트워크, 포맷팅, 공통 유틸리티
```

---

## 3. 의존성 다이어그램

의존성은 항상 같은 방향을 따라야 합니다:

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

실제로는:

- `interfaces/`는 `application/`을 호출할 수 있습니다.
- `application/`은 `domain/`을 호출하고 `ports/`에 정의된 계약을 사용할 수 있습니다.
- `domain/`은 `application/`, `infrastructure/`, `interfaces/` 어느 것에도 의존하지 않습니다.
- `infrastructure/`는 `ports/`에 정의된 계약을 구현합니다.
- `app/`은 계층을 조립하고 필요한 의존성을 제공합니다.

핵심 규칙:

> 도메인은 인프라스트럭처를 절대 알지 못한다.  
> 인프라스트럭처는 포트를 알지만, 도메인은 인프라스트럭처를 알지 못한다.

---

## 4. `app/` 폴더

### 역할

`app/` 폴더는 애플리케이션의 **조립 지점**입니다.

포함하는 것:

- 애플리케이션 시작;
- 생명주기;
- 의존성 주입 컨테이너;
- 동작에 필요한 객체 생성;
- 구체적인 구현 선택;
- 설정 초기화;
- 계층 간 연결.

### 책임 예시

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| 파일 | 역할 |
|---|---|
| `bootstrap.py` | 애플리케이션을 시작하고 실행할 인터페이스를 선택 |
| `container.py` | 의존성을 생성하고 연결 |
| `lifecycle.py` | 시작, 종료, 정리를 관리 |

### 규칙

`app/`에는 비즈니스 로직이 없습니다.

다음을 결정하지 않습니다:

- 무엇이 비즈니스 규칙인지;
- 데이터를 어떻게 계산해야 하는지;
- 요청을 어떻게 분석해야 하는지;
- 파일을 어떻게 내보내야 하는지.

이미 있는 구성 요소를 조립할 뿐입니다.

---

## 5. `core/` 폴더

### 역할

`core/` 폴더에는 프로젝트의 **공통 어휘**가 들어 있습니다.

여러 계층이 함께 쓰지만 그 자체로는 비즈니스 규칙이 아닌 요소들을 모아 둡니다.

포함할 수 있는 것:

- capability;
- 열거형;
- 상수;
- 공통 예외;
- 공통 타입;
- 플랫폼 정보;
- 수준이나 상태의 정의.

### 예시

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| 파일 | 역할 |
|---|---|
| `capabilities.py` | 사용 가능하거나 활성화할 수 있는 capability를 기술 |
| `constants.py` | 프로젝트 상수를 보관 |
| `enums.py` | 가능한 상태, 유형, 수준을 정의 |
| `exceptions.py` | 공통 오류를 정의 |

### 규칙

`core/`는 가볍고 안정적이어야 합니다.

포함해서는 안 되는 것:

- 복잡한 비즈니스 로직;
- 네트워크 호출;
- 디스크 접근;
- 사용자 인터페이스 코드;
- 외부 라이브러리에 대한 직접 의존.

---

## 6. `domain/` 폴더

### 역할

`domain/` 폴더는 **프로젝트의 심장**입니다.

순수 비즈니스 로직, 즉 애플리케이션이 실제로 무엇을 하는지 정의하는 규칙, 개념, 계산이 들어 있습니다.

포함할 수 있는 것:

- 엔티티;
- 값 객체(value object);
- 정책(policy);
- 비즈니스 규칙;
- 도메인 서비스;
- 계산;
- 비즈니스 검증;
- 비즈니스 데이터 모델.

### 예시

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| 요소 | 역할 |
|---|---|
| 엔티티 | 식별성을 가진 비즈니스 객체 |
| 값 객체 | 불변이며 검증된 값 |
| 정책 | 재사용 가능한 비즈니스 규칙 |
| 도메인 서비스 | 하나의 엔티티에 속하지 않는 비즈니스 로직 |

### 엄격한 규칙

`domain/` 폴더는:

- 디스크에 접근하지 않습니다;
- 네트워크를 호출하지 않습니다;
- 시스템 명령을 실행하지 않습니다;
- 데이터베이스에 접근하지 않습니다;
- 사용자 인터페이스를 import하지 않습니다;
- 인프라스트럭처를 import하지 않습니다;
- 피할 수 있다면 외부 기술 라이브러리에 의존하지 않습니다.

도메인은 서버, 파일, 네트워크, 인터페이스 없이도 테스트할 수 있어야 합니다.

---

## 7. `application/` 폴더

### 역할

`application/` 폴더는 유스케이스를 조율합니다.

다음 질문에 답합니다:

> "사용자가 이 작업을 요청하면 무슨 일이 일어나는가?"

포함하는 것:

- commands;
- queries;
- 유스케이스;
- 오케스트레이터;
- 작업 핸들러;
- 도메인과 포트 사이의 조율.

### commands / queries 구분

| 유형 | 목적 | 데이터 변경 |
|---|---|---|
| Command | 작업을 수행 | 예 |
| Query | 정보를 읽거나 계산 | 아니요 |

예시:

| Command | Query |
|---|---|
| 설정 적용 | 현재 설정 읽기 |
| 분석 시작 | 분석 결과 가져오기 |
| 보고서 내보내기 | 사용 가능한 항목 나열 |
| 데이터 삭제 | 기록 조회 |

### 예시

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### 규칙

`application/`에 포함되지 않는 것:

- 터미널 출력;
- Textual 인터페이스;
- Rich 명령;
- 데이터베이스 직접 접근;
- 외부 도구 직접 호출.

조율은 하지만 기술적 세부 사항은 구현하지 않습니다.

---

## 8. `ports/` 폴더

### 역할

`ports/` 폴더는 애플리케이션이 기대하는 **계약**을 정의합니다.

포트는 **애플리케이션에 무엇이 필요한지**를 설명할 뿐, 어떻게 구현해야 하는지는 강제하지 않습니다.

일반적으로 포함하는 것:

- `Protocol`;
- 추상 클래스 `ABC`;
- 리포지토리 인터페이스;
- 내보내기 인터페이스;
- 프로브 인터페이스;
- 외부 서비스 인터페이스;
- 저장소 인터페이스.

### 예시

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| 포트 | 역할 |
|---|---|
| `Repository` | 데이터를 읽거나 저장 |
| `Exporter` | 지정된 형식으로 출력 생성 |
| `Probe` | 시스템 또는 네트워크 정보 수집 |
| `Storage` | 영속성 백엔드 관리 |

### 개념 예시

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

이 계약이 말하는 것:

> "애플리케이션에는 보고서를 내보낼 수 있는 객체가 필요하다."

말하지 않는 것:

- 내보내기가 Markdown인지;
- 내보내기가 JSON인지;
- 파일이 로컬에 기록되는지;
- 내보내기가 네트워크로 전송되는지.

이런 선택은 `infrastructure/`의 몫입니다.

### 규칙

포트는 계약이지 구현이 아닙니다.

포함해서는 안 되는 것:

- 복잡한 비즈니스 로직;
- 디스크 접근;
- 네트워크 호출;
- 구체적인 구현;
- 외부 라이브러리에 대한 직접 의존.

---

## 9. `infrastructure/` 폴더

### 역할

`infrastructure/` 폴더에는 포트의 **구체적인 구현**이 들어 있습니다.

외부 세계와 통신하는 계층입니다.

포함할 수 있는 것:

- 파일 접근;
- 데이터베이스 접근;
- Markdown, JSON, CSV 등으로 내보내기;
- 로깅;
- 네트워크 호출;
- 시스템 프로브;
- 외부 도구의 통제된 실행;
- 서드파티 라이브러리용 어댑터;
- 리포지토리 구현;
- 저장소 구현.

### 예시

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

| 요소 | 역할 |
|---|---|
| `sqlite_repository.py` | SQLite로 리포지토리를 구현 |
| `json_file_repository.py` | JSON 파일로 리포지토리를 구현 |
| `markdown_exporter.py` | 보고서를 Markdown으로 내보냄 |
| `json_exporter.py` | 보고서를 JSON으로 내보냄 |
| `process_probe.py` | 프로세스 정보를 수집 |
| `filesystem_probe.py` | 파일 시스템 정보를 수집 |
| `structured_logger.py` | 구조화된 로그를 생성 |

### 규칙

`infrastructure/`는 다음에 직접 접근할 수 있는 유일한 계층입니다:

- 파일 시스템;
- 네트워크;
- SQLite;
- 외부 라이브러리;
- 시스템 도구;
- 필요하고 통제된 경우의 하위 프로세스.

이렇게 한곳에 모으면 다음이 쉬워집니다:

- 테스트;
- 보안 감사;
- 백엔드 교체;
- 부작용 제한.

---

## 10. `interfaces/` 폴더

### 역할

`interfaces/` 폴더에는 사용자에게 보이는 진입점이 들어 있습니다.

다음을 명확히 분리합니다:

- CLI;
- TUI;
- 앞으로 생길 수 있는 웹 또는 API 인터페이스.

### 구조

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

| 인터페이스 | 기술 | 역할 |
|---|---|---|
| `cli/` | Rich | 명령줄 인터페이스 |
| `tui/` | Textual | 터미널 대화형 인터페이스 |

### CLI

CLI는 명령줄 인터페이스입니다.

다음을 할 수 있습니다:

- 애플리케이션 실행;
- 특정 작업 수행;
- 결과 표시;
- 작업 자동화;
- 도구를 스크립트에 통합;
- SSH로 원격에서 애플리케이션 사용.

### TUI

TUI는 터미널 대화형 인터페이스입니다.

다음을 할 수 있습니다:

- 기능 사이를 이동;
- 정보 보기;
- 작업 수행;
- 결과 조회;
- 모든 명령을 외우지 않고도 애플리케이션 사용.

### 규칙

인터페이스에는 비즈니스 로직이 없습니다.

인터페이스는:

- 사용자의 의도를 받습니다;
- `application/`의 유스케이스를 호출합니다;
- 결과를 표시합니다;
- 오류를 이해하기 쉬운 메시지로 바꿉니다.

해서는 안 되는 것:

- 인프라스트럭처를 직접 호출;
- 하위 프로세스 실행;
- 파일에 직접 접근;
- 비즈니스 규칙 포함;
- `application/`의 로직 중복.

---

## 11. `plugins/` 폴더

### 역할

`plugins/` 폴더는 **내장 확장 기능** 전용입니다.

프로젝트 핵심을 무겁게 하지 않고 기능을 추가할 수 있게 해 줍니다.

예를 들어 플러그인은 다음을 할 수 있습니다:

- 내보내기 형식 추가;
- 프로브 추가;
- 명령 추가;
- TUI 화면 추가;
- 외부 연동 추가;
- 선택적 capability 추가.

### 원칙

플러그인은 프로젝트의 나머지와 같은 규칙을 지켜야 합니다:

- 포트를 우회하지 않습니다;
- 도메인을 직접 수정하지 않습니다;
- 명확한 계약을 통해 기능을 노출합니다;
- 애플리케이션을 망가뜨리지 않고 비활성화할 수 있습니다.

### 가능한 구조

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### 규칙

플러그인은 확장이지 뒷문이 아닙니다.

전체 아키텍처를 존중해야 하며, 프로젝트 핵심과 순환 의존을 만들어서는 안 됩니다.

---

## 12. `shared/` 폴더

### 역할

`shared/` 폴더에는 도메인, 애플리케이션, 인프라스트럭처 어디에도 속하지 않는 공통 유틸리티가 들어 있습니다.

재사용 가능한 범용 함수를 모아 둡니다.

포함할 수 있는 것:

- 파싱;
- 네트워크 유틸리티;
- 포맷팅;
- 텍스트 처리;
- 날짜 헬퍼;
- 경로 헬퍼;
- 범용 검증 유틸리티;
- 직렬화 헬퍼.

### 예시

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| 폴더 | 역할 |
|---|---|
| `parsing/` | 텍스트, JSON, YAML 등의 분석 |
| `network/` | 범용 네트워크 유틸리티 |
| `formatting/` | 값, 날짜, 크기, 표의 포맷팅 |
| `utils/` | 공통 유틸리티 함수 |

### 규칙

`shared/`가 잡동사니 폴더가 되어서는 안 됩니다.

유틸리티는 다음 조건을 만족할 때만 `shared/`에 둡니다:

- 재사용 가능할 것;
- 범용적일 것;
- 특정 유스케이스에 의존하지 않을 것;
- 여러 계층에 유용할 것.

---

## 13. 책임 요약

| 폴더 | 주요 역할 | 의존해도 되는 대상 | 의존하면 안 되는 대상 |
|---|---|---|---|
| `app/` | 애플리케이션 조립 및 시작 | 모든 계층 | — |
| `core/` | 어휘, 상수, enum, 예외 | 필요 시 `shared/` | `infrastructure/`, `interfaces/` |
| `domain/` | 순수 비즈니스 로직 | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | 유스케이스 조율 | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | 계약 정의 | 필요 시 `domain/` | `infrastructure/`, `interfaces/` |
| `infrastructure/` | 포트 구현 및 외부와 통신 | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | 사용자와 상호작용 | `application/`, `core/` | `infrastructure/` 직접 의존 |
| `plugins/` | 확장 추가 | 확장 유형에 따라 다름 | 아키텍처 우회 |
| `shared/` | 공통 유틸리티 | 어떤 비즈니스 계층에도 의존하지 않음 | 특정 비즈니스 로직 |

---

## 14. 작업 흐름 예시

사용자가 보고서를 Markdown으로 내보내 달라고 요청하는 경우를 생각해 봅시다.

```text
1. 사용자가 CLI 명령을 실행한다.

2. interfaces/cli/
   명령과 옵션을 받는다.

3. interfaces/cli/
   application/의 해당 유스케이스를 호출한다.

4. application/
   의도를 검증하고 작업을 준비한다.

5. application/
   도메인을 사용해 보고서를 만들거나 검증한다.

6. application/
   ReportExporter 포트를 통해 내보내기를 요청한다.

7. infrastructure/
   MarkdownExporter 구현을 제공한다.

8. infrastructure/
   Markdown 파일을 디스크에 기록한다.

9. interfaces/cli/
   사용자에게 결과를 표시한다.
```

간단한 다이어그램:

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
Markdown 파일
```

---

## 15. 왜 이 아키텍처인가?

### 가독성

각 폴더의 역할이 하나뿐이어서 기능을 추가하거나 수정할 위치를 찾기 쉽습니다.

### 테스트 용이성

도메인은 인터페이스, 데이터베이스, 네트워크 접근 없이 테스트할 수 있습니다.

### 유지보수성

인터페이스, 저장소, 외부 도구를 바꾸더라도 비즈니스 로직을 다시 작성할 필요가 없어야 합니다.

### 보안

파일, 네트워크, 하위 프로세스, 데이터베이스 같은 민감한 접근은 `infrastructure/`에 모여 있습니다. 덕분에 감사와 통제가 쉬워집니다.

### 확장성

다음을 추가할 수 있습니다:

- 새 인터페이스;
- 새 내보내기 형식;
- 새 저장소 백엔드;
- 새 플러그인;
- 새 시스템 프로브;

비즈니스 핵심을 수정하지 않고도 말입니다.

### 이식성

애플리케이션은 특정 기술에 묶이지 않고 다른 환경, 시스템, 상호작용 방식으로 발전할 수 있습니다.

---

## 16. 기억할 규칙

- 도메인은 순수하다.
- 애플리케이션은 조율한다.
- 포트는 필요를 선언한다.
- 인프라스트럭처는 구현한다.
- 인터페이스는 표시하고 입력을 받는다.
- `app/`은 조립한다.
- `core/`와 `shared/`는 공통 어휘와 유틸리티를 제공한다.
- 플러그인은 아키텍처를 우회하지 않고 확장한다.

한 문장으로:

> **애플리케이션은 무엇을 하는지, 어떻게 하는지, 사용자가 어떻게 사용하는지를 분리한다.**
