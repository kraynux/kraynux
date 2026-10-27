# Quy trình phát triển — [PROJECT_NAME]

**Ngôn ngữ:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Trường | Giá trị |
|---|---|
| Dự án | [PROJECT_NAME] |
| Phiên bản mục tiêu | [TARGET_VERSION] |
| Người phụ trách | [TÊN] |
| Ngày tạo | [YYYY-MM-DD] |
| Cập nhật lần cuối | [YYYY-MM-DD] |
| Trạng thái chung | Bản nháp / Đang thực hiện / Đã xác nhận / Đang vận hành |
| Môi trường mục tiêu | [Linux / Debian / Máy chủ / Máy trạm] |
| Ngôn ngữ chính | [Python / Bash / Lua / Khác] |
| Kho mã | [URL_HOẶC_ĐƯỜNG_DẪN] |

## Quy tắc chung

- [ ] Không viết mã trước khi kế hoạch cuối cùng được xác nhận.
- [ ] Mọi quyết định quan trọng đều được ghi lại.
- [ ] Mọi bất thường đều được ghi nhận.
- [ ] Mọi bản sửa lỗi đều được kiểm thử.
- [ ] Mọi thay đổi hành vi đều được ghi lại.
- [ ] Sao lưu được thực hiện trước mọi can thiệp trên môi trường vận hành.
- [ ] AI phân tích và đề xuất; con người quyết định, xác nhận và triển khai.
- [ ] Mã nguồn luôn khớp với tài liệu cuối cùng.

## Theo dõi tổng thể các giai đoạn

| Giai đoạn | Tác nhân | Sản phẩm chính | Trạng thái | Ngày xác nhận |
|---:|---|---|---|---|
| 1 | Con người | Nhu cầu và thiết kế | [ ] | [YYYY-MM-DD] |
| 2 | Con người | Bản phác kiến trúc và kế hoạch sơ bộ | [ ] | [YYYY-MM-DD] |
| 3 | AI | Phân tích, tác dụng phụ, kế hoạch cuối cùng | [ ] | [YYYY-MM-DD] |
| 4 | Con người | Lõi dự án đã được lập trình | [ ] | [YYYY-MM-DD] |
| 5 | AI | Kiểm tra mã, sửa lỗi và kiểm thử | [ ] | [YYYY-MM-DD] |
| 6 | Con người | Kiểm thử thực tế trên môi trường vận hành | [ ] | [YYYY-MM-DD] |
| 7 | AI | Kế hoạch sửa lỗi và lập trình hoàn thiện | [ ] | [YYYY-MM-DD] |
| 8 | Con người | Kiểm thử cuối cùng | [ ] | [YYYY-MM-DD] |
| 9 | Con người | Bản nháp tài liệu | [ ] | [YYYY-MM-DD] |
| 10 | AI | Tài liệu cuối cùng | [ ] | [YYYY-MM-DD] |
| 11 | Con người | Đưa vào vận hành | [ ] | [YYYY-MM-DD] |

---

# Giai đoạn 1 — Suy nghĩ, nhu cầu, cách dùng và thiết kế

**Tác nhân: Con người**  
**Mục tiêu:** xác định vấn đề, người dùng, cách dùng thực tế, các ràng buộc và giới hạn của dự án.

## 1. Vấn đề ban đầu

- Vấn đề đã xác định: [CẦN ĐIỀN]
- Tình trạng hiện tại: [CẦN ĐIỀN]
- Hậu quả của vấn đề: [CẦN ĐIỀN]
- Mục tiêu của dự án: [CẦN ĐIỀN]

## 2. Người dùng mục tiêu

| Người dùng | Nhu cầu chính | Trình độ kỹ thuật | Cách dùng dự kiến |
|---|---|---|---|
| [Người dùng 1] | [CẦN ĐIỀN] | [Mới bắt đầu / Kỹ thuật / Chuyên gia] | [CẦN ĐIỀN] |
| [Người dùng 2] | [CẦN ĐIỀN] | [Mới bắt đầu / Kỹ thuật / Chuyên gia] | [CẦN ĐIỀN] |

## 3. Kịch bản sử dụng

### Kịch bản thông thường

- Bối cảnh: [CẦN ĐIỀN]
- Hành động của người dùng: [CẦN ĐIỀN]
- Kết quả mong đợi: [CẦN ĐIỀN]

### Kịch bản giới hạn

- Bối cảnh: [CẦN ĐIỀN]
- Hành động của người dùng: [CẦN ĐIỀN]
- Kết quả mong đợi: [CẦN ĐIỀN]

### Kịch bản lỗi

- Bối cảnh: [CẦN ĐIỀN]
- Hành động của người dùng: [CẦN ĐIỀN]
- Kết quả mong đợi: [CẦN ĐIỀN]

### Kịch bản bị cấm hoặc nguy hiểm

- Bối cảnh: [CẦN ĐIỀN]
- Hành vi mong đợi: [Từ chối / Cảnh báo / Chặn / Ghi log]
- Lý do: [CẦN ĐIỀN]

## 4. Tính năng

### Bắt buộc

- [ ] [Tính năng 1]
- [ ] [Tính năng 2]
- [ ] [Tính năng 3]

### Hữu ích nhưng có thể hoãn

- [ ] [Tính năng 1]
- [ ] [Tính năng 2]

### Tùy chọn

- [ ] [Tính năng 1]

### Loại trừ

- [ ] [Tính năng bị loại trừ]
- Lý do: [CẦN ĐIỀN]

## 5. Ràng buộc

| Lĩnh vực | Ràng buộc | Mức ưu tiên |
|---|---|---|
| Hệ thống | [Linux / Debian / Phiên bản] | [Cao / Trung bình / Thấp] |
| Ngôn ngữ | [Python / Bash / Lua] | [Cao / Trung bình / Thấp] |
| Phụ thuộc | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Hiệu năng | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Bảo mật | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Tương thích | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Bảo trì | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Triển khai | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |

## 6. Rủi ro đã xác định

| Rủi ro | Tác động | Xác suất | Biện pháp phòng ngừa |
|---|---|---|---|
| [Rủi ro 1] | [Thấp / Trung bình / Cao] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] |
| [Rủi ro 2] | [Thấp / Trung bình / Cao] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] |

## 7. Quyết định đã đưa ra

| ID | Quyết định | Lý do | Ngày |
|---:|---|---|---|
| D-001 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [YYYY-MM-DD] |
| D-002 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [YYYY-MM-DD] |

## 8. Câu hỏi còn mở

- [ ] [Câu hỏi 1]
- [ ] [Câu hỏi 2]

## Xác nhận giai đoạn 1

- [ ] Vấn đề được phát biểu rõ ràng.
- [ ] Người dùng đã được xác định.
- [ ] Các kịch bản sử dụng chính đã được mô tả.
- [ ] Các tính năng bắt buộc đã được liệt kê.
- [ ] Giới hạn của dự án đã rõ ràng.
- [ ] Các ràng buộc kỹ thuật đã được nắm rõ.
- [ ] Các rủi ro chính đã được xác định.

**Trạng thái:** [ ] Bản nháp / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 2 — Phác thảo, thành phần chính và kế hoạch phát triển

**Tác nhân: Con người**  
**Mục tiêu:** chuyển nhu cầu thành một kiến trúc logic và một kế hoạch phát triển khả thi.

## 1. Thành phần chính

| Thành phần | Trách nhiệm | Không được làm | Mức ưu tiên |
|---|---|---|---|
| Giao diện / CLI | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Lõi nghiệp vụ | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Cấu hình | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Mô hình dữ liệu | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Dịch vụ | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Lưu trữ | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Xuất dữ liệu | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Log | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Bảo mật | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| Kiểm thử | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |

## 2. Luồng chính

```text
[Dữ liệu người dùng nhập]
    → [Giao diện]
    → [Kiểm tra hợp lệ]
    → [Lõi nghiệp vụ]
    → [Dịch vụ / Mô-đun]
    → [Kết quả]
    → [Đầu ra / Lưu trữ / Log]
```

## 3. Các mô-đun dự kiến

| Mô-đun | Vai trò | Phụ thuộc | Mức ưu tiên |
|---|---|---|---|
| [module_1] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| [module_2] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |
| [module_3] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Cao / Trung bình / Thấp] |

## 4. Cây thư mục sơ bộ

```text
[PROJECT_NAME]/
├── src/
│   └── [project_name]/
│       ├── __init__.py
│       ├── config.py
│       ├── exceptions.py
│       ├── logging.py
│       ├── models/
│       ├── core/
│       ├── services/
│       └── cli/
├── tests/
│   ├── unit/
│   └── integration/
├── docs/
├── scripts/
└── CHANGELOG.md
```

## 5. Phụ thuộc dự kiến

| Phụ thuộc | Mục đích sử dụng | Phiên bản tối thiểu | Lý do |
|---|---|---|---|
| [Phụ thuộc 1] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| [Phụ thuộc 2] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |

## 6. Phân chia công việc phát triển

| Giai đoạn | Nội dung | Mức ưu tiên | Ước lượng |
|---:|---|---|---|
| 1 | Nền tảng: cấu trúc, cấu hình, lỗi, log | [Cao / Trung bình] | [Thời lượng] |
| 2 | Mô hình và hợp đồng | [Cao / Trung bình] | [Thời lượng] |
| 3 | Lõi nghiệp vụ | [Cao / Trung bình] | [Thời lượng] |
| 4 | Giao diện / CLI | [Cao / Trung bình] | [Thời lượng] |
| 5 | Lưu trữ / xuất dữ liệu | [Cao / Trung bình] | [Thời lượng] |
| 6 | Kiểm thử | [Cao / Trung bình] | [Thời lượng] |
| 7 | Tài liệu và đóng gói | [Cao / Trung bình] | [Thời lượng] |

## Xác nhận giai đoạn 2

- [ ] Các thành phần chính đã được xác định.
- [ ] Mỗi mô-đun có trách nhiệm rõ ràng.
- [ ] Các luồng chính đã được mô tả.
- [ ] Cây thư mục sơ bộ đã được xác định.
- [ ] Các phụ thuộc chính đã được xác định.
- [ ] Thứ tự phát triển đã được xác định.
- [ ] Chưa có công việc phát triển nào bắt đầu.

**Trạng thái:** [ ] Bản nháp / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 3 — Phân tích của AI, tác dụng phụ và kế hoạch cuối cùng

**Tác nhân: AI**  
**Mục tiêu:** phân tích các tài liệu do con người soạn, xác định rủi ro và đưa ra kế hoạch cuối cùng khả thi.

## 1. Tài liệu được phân tích

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Tài liệu khác]

## 2. Prompt phân tích của AI

```text
Hãy phân tích dự án này mà không viết mã.

1. Phát hiện các điểm không nhất quán.
2. Phát hiện các chức năng còn thiếu.
3. Phát hiện các trách nhiệm đặt sai chỗ.
4. Xác định các tác dụng phụ có thể xảy ra.
5. Xác định các trường hợp lỗi.
6. Xác định các rủi ro bảo mật.
7. Xác định các vấn đề tương thích.
8. Đề xuất một cấu trúc dự án vững chắc hơn.
9. Đề xuất một kế hoạch phát triển cuối cùng.
10. Chỉ ra những điểm phải do con người quyết định.
```

## 3. Điểm không nhất quán phát hiện được

| ID | Mô tả | Tác động | Đề xuất | Quyết định của con người |
|---:|---|---|---|---|
| A-001 | [CẦN ĐIỀN] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] | [Chấp nhận / Từ chối / Hoãn] |
| A-002 | [CẦN ĐIỀN] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] | [Chấp nhận / Từ chối / Hoãn] |

## 4. Tác dụng phụ đã xác định

| ID | Tác dụng phụ | Yếu tố kích hoạt | Tác động | Phòng ngừa | Trạng thái |
|---:|---|---|---|---|---|
| SE-001 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] | [Mở / Đã xử lý / Chấp nhận] |
| SE-002 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Thấp / Trung bình / Cao] | [CẦN ĐIỀN] | [Mở / Đã xử lý / Chấp nhận] |

## 5. Các trường hợp lỗi cần lường trước

| Trường hợp | Hành vi mong đợi | Thông báo / log mong đợi | Kiểm thử liên quan |
|---|---|---|---|
| Thiếu tệp | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| Bị từ chối quyền | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| Mạng không khả dụng | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| Dữ liệu nhập không hợp lệ | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| Người dùng ngắt giữa chừng | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |
| Dữ liệu bị hỏng | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] |

## 6. Rủi ro bảo mật

| Rủi ro | Kịch bản | Biện pháp | Mức ưu tiên |
|---|---|---|---|
| [Rủi ro 1] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [P0 / P1 / P2] |
| [Rủi ro 2] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [P0 / P1 / P2] |

## 7. Kế hoạch phát triển cuối cùng

| Giai đoạn | Mục tiêu | Sản phẩm | Tiêu chí hoàn thành | Phụ thuộc |
|---:|---|---|---|---|
| 1 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Không có] |
| 2 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Giai đoạn 1] |
| 3 | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Giai đoạn 2] |

## Xác nhận giai đoạn 3

- [ ] Các điểm không nhất quán đã được xử lý hoặc ghi lại.
- [ ] Các tác dụng phụ đã được xác định.
- [ ] Các trường hợp lỗi đã được lường trước.
- [ ] Các rủi ro bảo mật đã được xử lý.
- [ ] Kế hoạch cuối cùng đã được con người xác nhận.
- [ ] Các quyết định cuối cùng đã được ghi lại.

**Trạng thái:** [ ] Bản nháp / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 4 — Lập trình lõi dự án

**Tác nhân: Con người**  
**Mục tiêu:** phát triển lõi chức năng mà không thêm tính năng ngoài phạm vi.

## 1. Phạm vi lập trình

- [ ] Cấu trúc dự án
- [ ] Môi trường ảo
- [ ] Phụ thuộc
- [ ] Cấu hình
- [ ] Mô hình dữ liệu
- [ ] Ngoại lệ
- [ ] Ghi log
- [ ] Dịch vụ nghiệp vụ
- [ ] Lõi nghiệp vụ
- [ ] Kiểm thử đơn vị
- [ ] CLI / giao diện
- [ ] Tích hợp

## 2. Thứ tự triển khai

| Thứ tự | Thành phần | Tệp / mô-đun | Trạng thái | Commit |
|---:|---|---|---|---|
| 1 | [Thành phần] | [đường dẫn] | [ ] | [hash] |
| 2 | [Thành phần] | [đường dẫn] | [ ] | [hash] |
| 3 | [Thành phần] | [đường dẫn] | [ ] | [hash] |

## 3. Quy tắc commit

- Một commit = một mục đích duy nhất.
- Không trộn lẫn tính năng, sửa lỗi và tái cấu trúc.
- Thông điệp khuyến nghị:

```text
[type]: [mô tả ngắn]

[type] = feat, fix, refactor, test, docs, chore
```

Ví dụ:

```text
feat: thêm việc nạp và kiểm tra cấu hình
```

## 4. Kiểm thử ban đầu

| Kiểm thử | Mục tiêu | Lệnh | Kết quả mong đợi | Trạng thái |
|---|---|---|---|---|
| [Kiểm thử 1] | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [ ] |
| [Kiểm thử 2] | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [ ] |

## Xác nhận giai đoạn 4

- [ ] Lõi nghiệp vụ hoạt động.
- [ ] Các dữ liệu nhập chính được kiểm tra hợp lệ.
- [ ] Các lỗi chính được xử lý.
- [ ] Các kiểm thử đơn vị đều đạt.
- [ ] Dự án khởi động được ở chế độ cơ bản.
- [ ] Không có tính năng ngoài phạm vi nào được thêm vào.

**Trạng thái:** [ ] Đang thực hiện / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 5 — AI phân tích mã, sửa lỗi và kiểm thử

**Tác nhân: AI**  
**Mục tiêu:** phát hiện khiếm khuyết, tác dụng phụ và rủi ro trước khi kiểm thử thực tế.

## 1. Prompt kiểm tra của AI

```text
Hãy phân tích mã mà không viết lại toàn bộ.

1. Kiểm tra sự phù hợp với kế hoạch phát triển.
2. Phát hiện các lỗi có khả năng xảy ra.
3. Phát hiện các tác dụng phụ.
4. Phát hiện rò rỉ tài nguyên.
5. Phát hiện các lỗi chưa được xử lý.
6. Phát hiện dữ liệu nhập chưa được kiểm tra.
7. Phát hiện các vấn đề bảo mật.
8. Phát hiện các vấn đề hiệu năng.
9. Phát hiện mã chết.
10. Phát hiện các trách nhiệm đặt sai chỗ.
11. Đề xuất các bản sửa có trọng tâm.
12. Đề xuất các kiểm thử còn thiếu.
```

## 2. Kết quả kiểm tra

| ID | Tệp / hàm | Phát hiện | Mức độ nghiêm trọng | Bản sửa đề xuất | Trạng thái |
|---:|---|---|---|---|---|
| C-001 | [đường dẫn] | [CẦN ĐIỀN] | [Nghiêm trọng / Lớn / Nhỏ] | [CẦN ĐIỀN] | [Mở / Đã sửa / Đã xác nhận] |
| C-002 | [đường dẫn] | [CẦN ĐIỀN] | [Nghiêm trọng / Lớn / Nhỏ] | [CẦN ĐIỀN] | [Mở / Đã sửa / Đã xác nhận] |

## 3. Kiểm thử được bổ sung

| Kiểm thử | Mục tiêu | Tệp kiểm thử | Trạng thái |
|---|---|---|---|
| [Kiểm thử 1] | [CẦN ĐIỀN] | [đường dẫn] | [ ] |
| [Kiểm thử 2] | [CẦN ĐIỀN] | [đường dẫn] | [ ] |

## Xác nhận giai đoạn 5

- [ ] Các lỗi nghiêm trọng đã được sửa.
- [ ] Các tác dụng phụ đã được xử lý hoặc ghi lại.
- [ ] Các kiểm thử đơn vị đều đạt.
- [ ] Các kiểm thử tích hợp đều đạt.
- [ ] Mã nguồn phù hợp với kế hoạch cuối cùng.
- [ ] Các bản sửa được áp dụng dần dần.

**Trạng thái:** [ ] Đang thực hiện / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 6 — Nghiên cứu thực tế và kiểm thử trên môi trường vận hành

**Tác nhân: Con người**  
**Mục tiêu:** xác nhận phần mềm trong điều kiện thực tế và ghi nhận mọi bất thường.

## 1. Môi trường kiểm thử

| Thành phần | Giá trị |
|---|---|
| Máy | [CẦN ĐIỀN] |
| Hệ thống | [CẦN ĐIỀN] |
| Phiên bản phần mềm | [CẦN ĐIỀN] |
| Môi trường | [Vận hành có kiểm soát / Tiền vận hành / Máy chủ thật] |
| Đã sao lưu | [Có / Không] |
| Ngày sao lưu | [YYYY-MM-DD] |
| Phương án khôi phục | [CẦN ĐIỀN] |

## 2. Các kịch bản đã kiểm thử

| ID | Kịch bản | Lệnh | Kết quả mong đợi | Kết quả thực tế | Trạng thái |
|---:|---|---|---|---|---|
| T-001 | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [OK / KO / Một phần] |
| T-002 | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [OK / KO / Một phần] |

## 3. Bảng quan sát

| Lĩnh vực | Yếu tố quan sát | Kết quả | Nhận xét |
|---|---|---|---|
| Chức năng | Chức năng mong đợi | [OK / KO] | [CẦN ĐIỀN] |
| Giao diện | Độ rõ ràng của lệnh | [OK / KO] | [CẦN ĐIỀN] |
| Hiệu năng | Thời gian thực thi | [OK / KO] | [CẦN ĐIỀN] |
| Độ ổn định | Không có sự cố bất ngờ | [OK / KO] | [CẦN ĐIỀN] |
| Lỗi | Thông báo dễ hiểu | [OK / KO] | [CẦN ĐIỀN] |
| Log | Chất lượng và tính hữu ích | [OK / KO] | [CẦN ĐIỀN] |
| Bảo mật | Hành vi an toàn | [OK / KO] | [CẦN ĐIỀN] |
| Tương thích | Hoạt động trên mục tiêu thật | [OK / KO] | [CẦN ĐIỀN] |
| Thẩm mỹ | Độ dễ đọc của đầu ra | [OK / KO] | [CẦN ĐIỀN] |
| Sử dụng thực tế | Độ trơn tru của quy trình làm việc | [OK / KO] | [CẦN ĐIỀN] |

## 4. Nhật ký bất thường

| ID | Ngày | Mức độ nghiêm trọng | Mô tả | Log | Giả thuyết | Bản sửa đề xuất | Trạng thái |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [YYYY-MM-DD] | [Nghiêm trọng / Lớn / Nhỏ / Thẩm mỹ] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Mở / Đã sửa / Đã xác nhận] |
| BUG-002 | [YYYY-MM-DD] | [Nghiêm trọng / Lớn / Nhỏ / Thẩm mỹ] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [Mở / Đã sửa / Đã xác nhận] |

## Xác nhận giai đoạn 6

- [ ] Tất cả kịch bản quan trọng đã được kiểm thử.
- [ ] Các lỗi đã được ghi nhận.
- [ ] Các vấn đề về trải nghiệm sử dụng đã được ghi nhận.
- [ ] Các vấn đề thẩm mỹ đã được ghi nhận.
- [ ] Không bỏ qua lỗi nghiêm trọng gây chặn nào.

**Trạng thái:** [ ] Đang thực hiện / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 7 — Kế hoạch cải tiến, sửa lỗi và lập trình hoàn thiện

**Tác nhân: AI**  
**Mục tiêu:** chuyển các bất thường thành bản sửa có ưu tiên, sau đó áp dụng các thay đổi mã cần thiết.

## 1. Prompt phân tích bất thường

```text
Đây là nhật ký kiểm thử trên môi trường vận hành.

1. Xếp hạng các bất thường theo mức độ nghiêm trọng.
2. Nhóm các bất thường liên quan.
3. Xác định các nguyên nhân có khả năng.
4. Đề xuất một bản sửa tối thiểu cho mỗi bất thường.
5. Chỉ ra các rủi ro hồi quy.
6. Đề xuất các kiểm thử cần bổ sung.
7. Đề xuất cải tiến trải nghiệm sử dụng.
8. Đề xuất cải tiến thẩm mỹ.
9. Chỉ thay đổi những gì cần thiết.
10. Giữ nguyên các hành vi đã được xác nhận.
```

## 2. Ưu tiên các bất thường

| Mức ưu tiên | Loại | Bất thường liên quan | Cách xử lý |
|---|---|---|---|
| P0 | Sự cố sập, mất dữ liệu, lỗ hổng | [BUG-XXX] | Sửa ngay |
| P1 | Tính năng sai | [BUG-XXX] | Sửa trước khi xác nhận cuối cùng |
| P2 | Trải nghiệm người dùng kém | [BUG-XXX] | Sửa nếu hợp lý |
| P3 | Thẩm mỹ, thông báo, định dạng | [BUG-XXX] | Sửa hoặc hoãn |
| P4 | Cải tiến tương lai | [BUG-XXX] | Backlog |

## 3. Các bản sửa đã áp dụng

| ID | Bất thường | Bản sửa | Tệp đã sửa | Kiểm thử đã thêm | Rủi ro hồi quy | Trạng thái |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [CẦN ĐIỀN] | [đường dẫn] | [đường dẫn] | [Thấp / Trung bình / Cao] | [Đã áp dụng / Đã xác nhận] |
| FIX-002 | [BUG-XXX] | [CẦN ĐIỀN] | [đường dẫn] | [đường dẫn] | [Thấp / Trung bình / Cao] | [Đã áp dụng / Đã xác nhận] |

## Xác nhận giai đoạn 7

- [ ] Mỗi bất thường đều có trạng thái rõ ràng.
- [ ] Các bản sửa được áp dụng theo mức ưu tiên.
- [ ] Các kiểm thử không hồi quy đều đạt.
- [ ] Các hành vi đã xác nhận được giữ nguyên.
- [ ] Mỗi bản sửa đều được ghi lại.

**Trạng thái:** [ ] Đang thực hiện / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 8 — Kiểm thử cuối cùng

**Tác nhân: Con người**  
**Mục tiêu:** xác nhận phiên bản ứng viên trước khi hoàn thiện tài liệu và đưa vào vận hành ổn định.

## 1. Kiểm thử xác nhận

| Kiểm thử | Mục tiêu | Lệnh | Kết quả mong đợi | Kết quả thực tế | Trạng thái |
|---|---|---|---|---|---|
| Kịch bản thông thường | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Kịch bản lỗi | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Tùy chọn CLI | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Cấu hình | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Quyền | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Ngắt giữa chừng | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |
| Không hồi quy | [CẦN ĐIỀN] | [lệnh] | [CẦN ĐIỀN] | [CẦN ĐIỀN] | [ ] |

## 2. Danh sách kiểm tra cuối cùng

- [ ] Dự án khởi động đúng.
- [ ] Các lệnh chính hoạt động.
- [ ] Các lỗi dễ hiểu.
- [ ] Log có thể khai thác được.
- [ ] Không có lỗi nghiêm trọng nào.
- [ ] Không phát hiện hồi quy nào.
- [ ] Hiệu năng chấp nhận được.
- [ ] Bảo mật đáp ứng yêu cầu.
- [ ] Phiên bản có thể nhận diện được.
- [ ] Có thể khôi phục về phiên bản trước.

## Xác nhận giai đoạn 8

**Quyết định:** [ ] Phiên bản ứng viên / [ ] Quay lại sửa lỗi  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 9 — Bản nháp tài liệu

**Tác nhân: Con người**  
**Mục tiêu:** viết tài liệu cho phần mềm đúng như cách nó thực sự hoạt động.

## 1. Tài liệu cần soạn

| Tài liệu | Mục tiêu | Trạng thái |
|---|---|---|
| `README.md` | Giới thiệu và bắt đầu nhanh | [ ] |
| `USER_GUIDE.md` | Hướng dẫn sử dụng chi tiết, dễ hiểu | [ ] |
| `TECHNICAL_GUIDE.md` | Kiến trúc và cách hoạt động bên trong | [ ] |
| `DEVELOPER_GUIDE.md` | Môi trường, kiểm thử, quy ước | [ ] |
| `INSTALLATION.md` | Yêu cầu và cài đặt | [ ] |
| `SECURITY.md` | Rủi ro, quyền, thực hành tốt | [ ] |
| `TROUBLESHOOTING.md` | Lỗi thường gặp và cách xử lý | [ ] |
| `CHANGELOG.md` | Lịch sử phiên bản | [ ] |

## 2. Nội dung cần kiểm tra

- [ ] Mỗi lệnh đều được ghi tài liệu.
- [ ] Mỗi tùy chọn đều được ghi tài liệu.
- [ ] Mỗi tệp cấu hình đều được ghi tài liệu.
- [ ] Mỗi phụ thuộc đều được ghi tài liệu.
- [ ] Mỗi lỗi thường gặp đều được giải thích.
- [ ] Các giới hạn đều được nêu rõ.
- [ ] Các ví dụ đều có thể kiểm thử.

## Xác nhận giai đoạn 9

**Trạng thái:** [ ] Bản nháp / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 10 — Định dạng và tài liệu cuối cùng

**Tác nhân: AI**  
**Mục tiêu:** bổ sung, sắp xếp và thống nhất tài liệu mà không bịa ra hành vi không có trong mã.

## 1. Prompt bổ sung tài liệu

```text
Đây là các bản nháp tài liệu.

1. Kiểm tra sự nhất quán với mã thực tế.
2. Phát hiện các chức năng chưa được ghi tài liệu.
3. Phát hiện các tùy chọn CLI chưa được ghi tài liệu.
4. Phát hiện các thông báo lỗi chưa được giải thích.
5. Phát hiện các phụ thuộc còn thiếu.
6. Phát hiện các bước cài đặt còn thiếu.
7. Phát hiện các điểm không nhất quán giữa các tài liệu.
8. Cải thiện cấu trúc và độ dễ đọc.
9. Bổ sung các phần còn thiếu.
10. Không thay đổi hành vi đã mô tả nếu không có bằng chứng trong mã.
```

## 2. Kiểm tra tài liệu

| Hạng mục kiểm tra | Trạng thái | Nhận xét |
|---|---|---|
| Nhất quán với mã | [ ] | [CẦN ĐIỀN] |
| Lệnh đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Tùy chọn đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Mã thoát đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Cấu hình đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Phụ thuộc đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Lỗi thường gặp đã có tài liệu | [ ] | [CẦN ĐIỀN] |
| Ví dụ có thể kiểm thử | [ ] | [CẦN ĐIỀN] |
| Cấu trúc thống nhất | [ ] | [CẦN ĐIỀN] |

## Xác nhận giai đoạn 10

**Trạng thái:** [ ] Bản nháp / [ ] Đã xác nhận  
**Người xác nhận:** [TÊN]  
**Ngày:** [YYYY-MM-DD]

---

# Giai đoạn 11 — Đưa vào vận hành chính thức

**Tác nhân: Con người**  
**Mục tiêu:** triển khai phiên bản đã được xác nhận, ghi tài liệu và kiểm thử.

## 1. Chuẩn bị

- [ ] Phiên bản đã được xác nhận ở giai đoạn 8.
- [ ] Tài liệu cuối cùng đã được xác nhận ở giai đoạn 10.
- [ ] Đã sao lưu môi trường hiện có.
- [ ] Đã có quy trình khôi phục.
- [ ] Đã tạo tag phiên bản.

Lệnh:

```bash
git tag -a v[VERSION] -m "Phiên bản ổn định [VERSION]"
git push origin v[VERSION]
```

## 2. Đóng gói

```bash
python -m build
```

Kiểm tra:

```bash
sha256sum dist/*
```

## 3. Triển khai

| Bước | Lệnh / hành động | Trạng thái | Nhận xét |
|---:|---|---|---|
| 1 | Sao lưu | [ ] | [CẦN ĐIỀN] |
| 2 | Triển khai phiên bản đã gắn tag | [ ] | [CẦN ĐIỀN] |
| 3 | Kiểm tra dịch vụ | [ ] | [CẦN ĐIỀN] |
| 4 | Kiểm tra log | [ ] | [CẦN ĐIỀN] |
| 5 | Kiểm thử lệnh chính | [ ] | [CẦN ĐIỀN] |
| 6 | Ghi lại phiên bản đã triển khai | [ ] | [CẦN ĐIỀN] |

## 4. Kiểm tra sau triển khai

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] Dịch vụ đang hoạt động.
- [ ] Không có lỗi nghiêm trọng nào trong log.
- [ ] Lệnh chính phản hồi.
- [ ] Phiên bản đã triển khai khớp với tag đã xác nhận.
- [ ] Phương án khôi phục đã được ghi lại và có thể kiểm thử.

## Xác nhận cuối cùng

| Trường | Giá trị |
|---|---|
| Phiên bản đã triển khai | [VERSION] |
| Ngày đưa vào vận hành | [YYYY-MM-DD] |
| Môi trường | [CẦN ĐIỀN] |
| Người phụ trách | [TÊN] |
| Đã thử khôi phục | [Có / Không] |
| Trạng thái cuối cùng | [Đang vận hành / Thất bại / Đã khôi phục] |

---

# Lịch sử thay đổi tài liệu

| Ngày | Phiên bản | Tác giả | Thay đổi |
|---|---|---|---|
| [YYYY-MM-DD] | 0.1 | [TÊN] | Tạo mẫu |
| [YYYY-MM-DD] | [VERSION] | [TÊN] | [CẦN ĐIỀN] |
