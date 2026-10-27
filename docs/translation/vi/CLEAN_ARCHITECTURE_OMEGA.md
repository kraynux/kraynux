# Kiến trúc dự án — Clean Architecture

**Ngôn ngữ:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Tài liệu này giải thích dự án được tổ chức như thế nào, vì sao lại chọn cách tổ chức này và mỗi thư mục chứa những gì. Tài liệu dành cho cả khách tham quan muốn hiểu cách ứng dụng hoạt động lẫn các lập trình viên muốn đóng góp hoặc bảo trì dự án.

Ứng dụng tuân theo **Clean Architecture**: phần lõi của phần mềm được tách biệt khỏi các chi tiết kỹ thuật, giao diện người dùng và các phụ thuộc bên ngoài. Sự tách biệt này giúp dự án dễ đọc, dễ kiểm thử, dễ bảo trì và dễ phát triển hơn.

---

## 1. Nguyên tắc chung

Ứng dụng được chia thành các tầng, mỗi tầng có một vai trò rõ ràng.

Ý tưởng cốt lõi rất đơn giản:

```text
Giao diện yêu cầu một hành động.
Ứng dụng điều phối hành động đó.
Miền nghiệp vụ áp dụng các quy tắc nghiệp vụ.
Các port xác định những gì ứng dụng cần.
Hạ tầng cung cấp các triển khai cụ thể.
```

Nhờ vậy, phần logic quan trọng của dự án không phụ thuộc trực tiếp vào:

- terminal;
- giao diện đồ họa;
- cơ sở dữ liệu;
- mạng;
- hệ thống tệp;
- thư viện bên ngoài;
- công cụ hệ thống.

Sự độc lập này cho phép thay thế một phần phần mềm mà không phải viết lại toàn bộ phần còn lại.

---

## 2. Tổng quan

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Khởi động, vòng đời và tiêm phụ thuộc
        ├── core/             Khả năng, enum và ngoại lệ dùng chung
        ├── domain/           Logic nghiệp vụ thuần
        ├── application/      Ca sử dụng: commands và queries
        ├── infrastructure/   Backend, lưu trữ, xuất dữ liệu, log, đầu dò hệ thống…
        ├── ports/            Hợp đồng Protocol / ABC
        ├── interfaces/       CLI và TUI
        ├── plugins/          Tiện ích mở rộng tích hợp
        └── shared/           Phân tích cú pháp, mạng, định dạng và tiện ích dùng chung
```

---

## 3. Sơ đồ phụ thuộc

Các phụ thuộc phải luôn đi theo cùng một hướng:

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

Trong thực tế:

- `interfaces/` có thể gọi `application/`.
- `application/` có thể gọi `domain/` và sử dụng các hợp đồng định nghĩa trong `ports/`.
- `domain/` không phụ thuộc vào `application/`, `infrastructure/` hay `interfaces/`.
- `infrastructure/` triển khai các hợp đồng định nghĩa trong `ports/`.
- `app/` lắp ráp các tầng và cung cấp các phụ thuộc cần thiết.

Quy tắc cốt lõi:

> Miền nghiệp vụ không bao giờ biết đến hạ tầng.  
> Hạ tầng biết các port, nhưng miền nghiệp vụ không biết hạ tầng.

---

## 4. Thư mục `app/`

### Vai trò

Thư mục `app/` là **điểm lắp ráp** của ứng dụng.

Nó chứa:

- phần khởi động ứng dụng;
- vòng đời;
- container tiêm phụ thuộc;
- việc tạo các đối tượng cần thiết cho hoạt động;
- việc chọn các triển khai cụ thể;
- việc khởi tạo cấu hình;
- việc kết nối giữa các tầng.

### Ví dụ về trách nhiệm

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Tệp | Vai trò |
|---|---|
| `bootstrap.py` | Khởi động ứng dụng và chọn giao diện cần chạy |
| `container.py` | Tạo và kết nối các phụ thuộc |
| `lifecycle.py` | Quản lý khởi động, dừng và dọn dẹp |

### Quy tắc

`app/` không chứa logic nghiệp vụ.

Nó không quyết định:

- quy tắc nghiệp vụ là gì;
- một dữ liệu phải được tính như thế nào;
- một yêu cầu phải được phân tích như thế nào;
- một tệp phải được xuất ra như thế nào.

Nó chỉ lắp ráp các thành phần đã có.

---

## 5. Thư mục `core/`

### Vai trò

Thư mục `core/` chứa **bộ từ vựng dùng chung** của dự án.

Nó gom các phần tử được nhiều tầng chia sẻ nhưng bản thân chúng không phải là quy tắc nghiệp vụ.

Nó có thể chứa:

- các khả năng (capabilities);
- các kiểu liệt kê;
- các hằng số;
- các ngoại lệ dùng chung;
- các kiểu dữ liệu chung;
- thông tin nền tảng;
- định nghĩa các mức hoặc trạng thái.

### Ví dụ

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Tệp | Vai trò |
|---|---|
| `capabilities.py` | Mô tả các khả năng có sẵn hoặc có thể kích hoạt |
| `constants.py` | Chứa các hằng số của dự án |
| `enums.py` | Định nghĩa các trạng thái, kiểu hoặc mức có thể có |
| `exceptions.py` | Định nghĩa các lỗi dùng chung |

### Quy tắc

`core/` phải luôn nhẹ và ổn định.

Nó không được chứa:

- logic nghiệp vụ phức tạp;
- lệnh gọi mạng;
- truy cập đĩa;
- mã giao diện người dùng;
- phụ thuộc trực tiếp vào thư viện bên ngoài.

---

## 6. Thư mục `domain/`

### Vai trò

Thư mục `domain/` là **trái tim của dự án**.

Nó chứa logic nghiệp vụ thuần: các quy tắc, khái niệm và phép tính thực sự xác định ứng dụng làm gì.

Nó có thể chứa:

- các thực thể;
- value object;
- các chính sách (policies);
- các quy tắc nghiệp vụ;
- các dịch vụ miền;
- các phép tính;
- các kiểm tra hợp lệ nghiệp vụ;
- các mô hình dữ liệu nghiệp vụ.

### Ví dụ

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Phần tử | Vai trò |
|---|---|
| Thực thể | Đối tượng nghiệp vụ có danh tính |
| Value object | Giá trị bất biến và đã được kiểm tra hợp lệ |
| Chính sách | Quy tắc nghiệp vụ có thể tái sử dụng |
| Dịch vụ miền | Logic nghiệp vụ không thuộc về riêng một thực thể |

### Quy tắc nghiêm ngặt

Thư mục `domain/`:

- không truy cập đĩa;
- không gọi mạng;
- không thực thi lệnh hệ thống;
- không truy cập cơ sở dữ liệu;
- không import giao diện người dùng;
- không import hạ tầng;
- không phụ thuộc vào thư viện kỹ thuật bên ngoài khi có thể tránh.

Miền nghiệp vụ phải kiểm thử được mà không cần máy chủ, tệp, mạng hay giao diện.

---

## 7. Thư mục `application/`

### Vai trò

Thư mục `application/` điều phối các ca sử dụng.

Nó trả lời câu hỏi:

> “Điều gì xảy ra khi người dùng yêu cầu hành động này?”

Nó chứa:

- các command;
- các query;
- các ca sử dụng;
- các bộ điều phối;
- các bộ xử lý hành động;
- sự phối hợp giữa miền nghiệp vụ và các port.

### Phân biệt commands / queries

| Loại | Mục đích | Thay đổi dữ liệu |
|---|---|---|
| Command | Thực hiện một hành động | Có |
| Query | Đọc hoặc tính toán một thông tin | Không |

Ví dụ:

| Command | Query |
|---|---|
| Áp dụng một cấu hình | Đọc cấu hình hiện tại |
| Chạy một phân tích | Lấy kết quả của một phân tích |
| Xuất một báo cáo | Liệt kê các mục có sẵn |
| Xóa dữ liệu | Xem lịch sử |

### Ví dụ

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Quy tắc

`application/` không chứa:

- hiển thị trên terminal;
- giao diện Textual;
- lệnh Rich;
- truy cập trực tiếp cơ sở dữ liệu;
- lệnh gọi trực tiếp tới công cụ bên ngoài.

Nó điều phối, nhưng không triển khai các chi tiết kỹ thuật.

---

## 8. Thư mục `ports/`

### Vai trò

Thư mục `ports/` định nghĩa các **hợp đồng** mà ứng dụng mong đợi.

Một port mô tả **những gì ứng dụng cần**, mà không áp đặt cách triển khai.

Nó thường chứa:

- `Protocol`;
- các lớp trừu tượng `ABC`;
- giao diện repository;
- giao diện xuất dữ liệu;
- giao diện đầu dò;
- giao diện dịch vụ bên ngoài;
- giao diện lưu trữ.

### Ví dụ

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Vai trò |
|---|---|
| `Repository` | Đọc hoặc lưu dữ liệu |
| `Exporter` | Tạo đầu ra theo một định dạng nhất định |
| `Probe` | Thu thập thông tin hệ thống hoặc mạng |
| `Storage` | Quản lý một backend lưu trữ bền vững |

### Ví dụ khái niệm

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Hợp đồng này nói:

> “Ứng dụng cần một đối tượng có khả năng xuất một báo cáo.”

Nó không nói:

- việc xuất sẽ ở định dạng Markdown;
- việc xuất sẽ ở định dạng JSON;
- tệp sẽ được ghi cục bộ;
- việc xuất sẽ được gửi qua mạng.

Những lựa chọn này thuộc về `infrastructure/`.

### Quy tắc

Port là hợp đồng, không phải triển khai.

Chúng không được chứa:

- logic nghiệp vụ phức tạp;
- truy cập đĩa;
- lệnh gọi mạng;
- triển khai cụ thể;
- phụ thuộc trực tiếp vào thư viện bên ngoài.

---

## 9. Thư mục `infrastructure/`

### Vai trò

Thư mục `infrastructure/` chứa các **triển khai cụ thể** của các port.

Đây là tầng giao tiếp với thế giới bên ngoài.

Nó có thể chứa:

- truy cập tệp;
- truy cập cơ sở dữ liệu;
- xuất ra Markdown, JSON, CSV hoặc định dạng khác;
- ghi log;
- lệnh gọi mạng;
- đầu dò hệ thống;
- thực thi có kiểm soát các công cụ bên ngoài;
- bộ chuyển đổi (adapter) cho thư viện bên thứ ba;
- triển khai repository;
- triển khai lưu trữ.

### Ví dụ

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

| Phần tử | Vai trò |
|---|---|
| `sqlite_repository.py` | Triển khai một repository bằng SQLite |
| `json_file_repository.py` | Triển khai một repository bằng các tệp JSON |
| `markdown_exporter.py` | Xuất báo cáo sang Markdown |
| `json_exporter.py` | Xuất báo cáo sang JSON |
| `process_probe.py` | Thu thập thông tin về các tiến trình |
| `filesystem_probe.py` | Thu thập thông tin về hệ thống tệp |
| `structured_logger.py` | Tạo log có cấu trúc |

### Quy tắc

`infrastructure/` là tầng duy nhất được phép truy cập trực tiếp vào:

- hệ thống tệp;
- mạng;
- SQLite;
- các thư viện bên ngoài;
- các công cụ hệ thống;
- các tiến trình con, khi cần thiết và có kiểm soát.

Sự tập trung này giúp:

- kiểm thử dễ hơn;
- kiểm tra bảo mật dễ hơn;
- thay thế backend dễ hơn;
- hạn chế tác dụng phụ.

---

## 10. Thư mục `interfaces/`

### Vai trò

Thư mục `interfaces/` chứa các điểm vào mà người dùng nhìn thấy.

Nó tách bạch rõ ràng:

- CLI;
- TUI;
- các giao diện web hoặc API có thể có trong tương lai.

### Cấu trúc

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

| Giao diện | Công nghệ | Vai trò |
|---|---|---|
| `cli/` | Rich | Giao diện dòng lệnh |
| `tui/` | Textual | Giao diện tương tác trong terminal |

### CLI

CLI là giao diện dòng lệnh.

Nó cho phép:

- khởi chạy ứng dụng;
- thực hiện một hành động cụ thể;
- hiển thị kết quả;
- tự động hóa một tác vụ;
- tích hợp công cụ vào script;
- sử dụng ứng dụng từ xa qua SSH.

### TUI

TUI là giao diện tương tác trong terminal.

Nó cho phép:

- điều hướng giữa các tính năng;
- xem thông tin;
- thực hiện hành động;
- tra cứu kết quả;
- sử dụng ứng dụng mà không cần nhớ mọi lệnh.

### Quy tắc

Giao diện không chứa logic nghiệp vụ.

Chúng:

- nhận ý định của người dùng;
- gọi một ca sử dụng trong `application/`;
- hiển thị kết quả;
- chuyển lỗi thành thông báo dễ hiểu.

Chúng không được:

- gọi trực tiếp hạ tầng;
- thực thi tiến trình con;
- truy cập trực tiếp tệp;
- chứa quy tắc nghiệp vụ;
- sao chép logic của `application/`.

---

## 11. Thư mục `plugins/`

### Vai trò

Thư mục `plugins/` dành riêng cho **các tiện ích mở rộng tích hợp**.

Nó cho phép thêm tính năng mà không làm nặng phần lõi của dự án.

Ví dụ, một plugin có thể:

- thêm một định dạng xuất;
- thêm một đầu dò;
- thêm một lệnh;
- thêm một màn hình TUI;
- thêm một tích hợp bên ngoài;
- thêm một khả năng tùy chọn.

### Nguyên tắc

Một plugin phải tuân theo cùng các quy tắc như phần còn lại của dự án:

- không đi vòng qua các port;
- không sửa trực tiếp miền nghiệp vụ;
- cung cấp tính năng qua các hợp đồng rõ ràng;
- có thể tắt mà không làm hỏng ứng dụng.

### Cấu trúc khả dĩ

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Quy tắc

Plugin là tiện ích mở rộng, không phải cửa sau.

Nó phải tuân thủ kiến trúc tổng thể và không được tạo phụ thuộc vòng với phần lõi của dự án.

---

## 12. Thư mục `shared/`

### Vai trò

Thư mục `shared/` chứa các tiện ích dùng chung không thuộc miền nghiệp vụ, ứng dụng hay hạ tầng.

Nó gom các hàm chung có thể tái sử dụng.

Nó có thể chứa:

- phân tích cú pháp;
- tiện ích mạng;
- định dạng;
- xử lý văn bản;
- hàm hỗ trợ ngày tháng;
- hàm hỗ trợ đường dẫn;
- tiện ích kiểm tra hợp lệ chung;
- hàm hỗ trợ tuần tự hóa.

### Ví dụ

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Thư mục | Vai trò |
|---|---|
| `parsing/` | Phân tích văn bản, JSON, YAML hoặc định dạng khác |
| `network/` | Tiện ích mạng chung |
| `formatting/` | Định dạng giá trị, ngày tháng, kích thước hoặc bảng |
| `utils/` | Các hàm tiện ích dùng chung |

### Quy tắc

`shared/` không được trở thành thư mục chứa tạp nham.

Một tiện ích chỉ nên nằm trong `shared/` nếu nó:

- có thể tái sử dụng;
- mang tính chung;
- độc lập với một ca sử dụng cụ thể;
- hữu ích cho nhiều tầng.

---

## 13. Tóm tắt trách nhiệm

| Thư mục | Vai trò chính | Có thể phụ thuộc vào | Không được phụ thuộc vào |
|---|---|---|---|
| `app/` | Lắp ráp và khởi động ứng dụng | Mọi tầng | — |
| `core/` | Từ vựng, hằng số, enum và ngoại lệ | `shared/` nếu cần | `infrastructure/`, `interfaces/` |
| `domain/` | Logic nghiệp vụ thuần | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Điều phối các ca sử dụng | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Định nghĩa các hợp đồng | `domain/` nếu cần | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Triển khai port và giao tiếp với bên ngoài | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Tương tác với người dùng | `application/`, `core/` | `infrastructure/` trực tiếp |
| `plugins/` | Thêm tiện ích mở rộng | Tùy loại tiện ích | Đi vòng qua kiến trúc |
| `shared/` | Tiện ích dùng chung | Không tầng nghiệp vụ nào | Logic nghiệp vụ cụ thể |

---

## 14. Ví dụ về luồng của một hành động

Giả sử một người dùng yêu cầu xuất một báo cáo sang Markdown.

```text
1. Người dùng chạy một lệnh CLI.

2. interfaces/cli/
   Nhận lệnh và các tùy chọn.

3. interfaces/cli/
   Gọi ca sử dụng tương ứng trong application/.

4. application/
   Kiểm tra ý định và chuẩn bị hành động.

5. application/
   Dùng miền nghiệp vụ để tạo hoặc kiểm tra báo cáo.

6. application/
   Yêu cầu xuất qua port ReportExporter.

7. infrastructure/
   Cung cấp triển khai MarkdownExporter.

8. infrastructure/
   Ghi tệp Markdown xuống đĩa.

9. interfaces/cli/
   Hiển thị kết quả cho người dùng.
```

Sơ đồ đơn giản:

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
Tệp Markdown
```

---

## 15. Vì sao chọn kiến trúc này?

### Dễ đọc

Mỗi thư mục có một vai trò duy nhất, giúp dễ tìm nơi cần thêm hoặc sửa một tính năng.

### Dễ kiểm thử

Miền nghiệp vụ có thể được kiểm thử mà không cần giao diện, cơ sở dữ liệu hay truy cập mạng.

### Dễ bảo trì

Việc thay đổi giao diện, cách lưu trữ hay một công cụ bên ngoài không được đòi hỏi viết lại logic nghiệp vụ.

### Bảo mật

Các truy cập nhạy cảm — tệp, mạng, tiến trình con, cơ sở dữ liệu — được tập trung trong `infrastructure/`. Điều này giúp việc kiểm tra và kiểm soát dễ dàng hơn.

### Khả năng mở rộng

Có thể thêm:

- một giao diện mới;
- một định dạng xuất mới;
- một backend lưu trữ mới;
- một plugin mới;
- một đầu dò hệ thống mới;

mà không phải sửa phần lõi nghiệp vụ.

### Tính di động

Ứng dụng có thể phát triển sang các môi trường, hệ thống hoặc cách tương tác khác mà không bị ràng buộc vào một công nghệ cụ thể.

---

## 16. Các quy tắc cần nhớ

- Miền nghiệp vụ là thuần.
- Ứng dụng điều phối.
- Các port khai báo nhu cầu.
- Hạ tầng triển khai.
- Giao diện hiển thị và thu nhận.
- `app/` lắp ráp.
- `core/` và `shared/` cung cấp từ vựng và tiện ích dùng chung.
- Plugin mở rộng mà không đi vòng qua kiến trúc.

Tóm lại trong một câu:

> **Ứng dụng tách biệt những gì nó làm, cách nó làm và cách người dùng sử dụng nó.**
