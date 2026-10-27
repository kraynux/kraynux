# Arsitektur proyek — Clean Architecture

**Bahasa:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Dokumen ini menjelaskan bagaimana proyek diorganisasi, mengapa organisasi ini dipilih, dan apa isi setiap folder. Dokumen ini ditujukan bagi pengunjung yang ingin memahami cara kerja aplikasi maupun bagi pengembang yang ingin berkontribusi atau memeliharanya.

Aplikasi ini mengikuti **Clean Architecture**: inti perangkat lunak diisolasi dari detail teknis, antarmuka pengguna, dan dependensi eksternal. Pemisahan ini membuat proyek lebih mudah dibaca, diuji, dipelihara, dan dikembangkan.

---

## 1. Prinsip umum

Aplikasi dibagi menjadi beberapa lapisan, masing-masing dengan peran yang jelas.

Gagasan utamanya sederhana:

```text
Antarmuka meminta sebuah aksi.
Aplikasi mengorkestrasi aksi tersebut.
Domain menerapkan aturan bisnis.
Port menentukan apa yang dibutuhkan aplikasi.
Infrastruktur menyediakan implementasi konkret.
```

Dengan begitu, logika penting proyek tidak bergantung langsung pada:

- terminal;
- antarmuka grafis;
- basis data;
- jaringan;
- sistem berkas;
- pustaka eksternal;
- alat sistem.

Kemandirian ini memungkinkan sebagian perangkat lunak diganti tanpa menulis ulang seluruh bagian lainnya.

---

## 2. Gambaran umum

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, siklus hidup, dan injeksi dependensi
        ├── core/             Kapabilitas, enum, dan eksepsi lintas lapisan
        ├── domain/           Logika bisnis murni
        ├── application/      Use case: commands dan queries
        ├── infrastructure/   Backend, penyimpanan, ekspor, log, probe sistem…
        ├── ports/            Kontrak Protocol / ABC
        ├── interfaces/       CLI dan TUI
        ├── plugins/          Ekstensi bawaan
        └── shared/           Parsing, jaringan, pemformatan, dan utilitas lintas lapisan
```

---

## 3. Diagram dependensi

Dependensi harus selalu mengalir ke arah yang sama:

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

Dalam praktiknya:

- `interfaces/` boleh memanggil `application/`.
- `application/` boleh memanggil `domain/` dan menggunakan kontrak yang didefinisikan di `ports/`.
- `domain/` tidak bergantung pada `application/`, `infrastructure/`, maupun `interfaces/`.
- `infrastructure/` mengimplementasikan kontrak yang didefinisikan di `ports/`.
- `app/` merakit lapisan-lapisan dan menyediakan dependensi yang dibutuhkan.

Aturan utama:

> Domain tidak pernah mengenal infrastruktur.  
> Infrastruktur mengenal port, tetapi domain tidak mengenal infrastruktur.

---

## 4. Folder `app/`

### Peran

Folder `app/` adalah **titik perakitan** aplikasi.

Isinya:

- proses awal aplikasi;
- siklus hidup;
- container injeksi dependensi;
- pembuatan objek yang dibutuhkan agar aplikasi berjalan;
- pemilihan implementasi konkret;
- inisialisasi konfigurasi;
- penghubungan antarlapisan.

### Contoh tanggung jawab

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Berkas | Peran |
|---|---|
| `bootstrap.py` | Menjalankan aplikasi dan memilih antarmuka yang akan dibuka |
| `container.py` | Membuat dan menghubungkan dependensi |
| `lifecycle.py` | Mengelola proses mulai, berhenti, dan pembersihan |

### Aturan

`app/` tidak berisi logika bisnis.

Ia tidak memutuskan:

- apa itu aturan bisnis;
- bagaimana sebuah data harus dihitung;
- bagaimana sebuah permintaan harus dianalisis;
- bagaimana sebuah berkas harus diekspor.

Ia hanya merakit komponen yang sudah ada.

---

## 5. Folder `core/`

### Peran

Folder `core/` berisi **kosakata lintas lapisan** proyek.

Ia mengelompokkan elemen yang digunakan bersama oleh beberapa lapisan, tetapi pada dasarnya bukan aturan bisnis.

Isinya dapat berupa:

- kapabilitas;
- enumerasi;
- konstanta;
- eksepsi lintas lapisan;
- tipe umum;
- informasi platform;
- definisi tingkat atau status.

### Contoh

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Berkas | Peran |
|---|---|
| `capabilities.py` | Menjelaskan kapabilitas yang tersedia atau dapat diaktifkan |
| `constants.py` | Berisi konstanta proyek |
| `enums.py` | Mendefinisikan status, tipe, atau tingkat yang mungkin |
| `exceptions.py` | Mendefinisikan galat lintas lapisan |

### Aturan

`core/` harus tetap ringan dan stabil.

Ia tidak boleh berisi:

- logika bisnis yang kompleks;
- panggilan jaringan;
- akses disk;
- kode antarmuka pengguna;
- dependensi langsung pada pustaka eksternal.

---

## 6. Folder `domain/`

### Peran

Folder `domain/` adalah **jantung proyek**.

Ia berisi logika bisnis murni: aturan, konsep, dan perhitungan yang benar-benar menentukan apa yang dilakukan aplikasi.

Isinya dapat berupa:

- entitas;
- value object;
- kebijakan (policies);
- aturan bisnis;
- layanan domain;
- perhitungan;
- validasi bisnis;
- model data bisnis.

### Contoh

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Elemen | Peran |
|---|---|
| Entitas | Objek bisnis yang memiliki identitas |
| Value object | Nilai yang tidak dapat diubah dan sudah divalidasi |
| Kebijakan | Aturan bisnis yang dapat digunakan ulang |
| Layanan domain | Logika bisnis yang bukan milik satu entitas saja |

### Aturan ketat

Folder `domain/`:

- tidak mengakses disk;
- tidak melakukan panggilan jaringan;
- tidak menjalankan perintah sistem;
- tidak mengakses basis data;
- tidak mengimpor antarmuka pengguna;
- tidak mengimpor infrastruktur;
- tidak bergantung pada pustaka teknis eksternal jika bisa dihindari.

Domain harus dapat diuji tanpa server, tanpa berkas, tanpa jaringan, dan tanpa antarmuka.

---

## 7. Folder `application/`

### Peran

Folder `application/` mengorkestrasi use case.

Ia menjawab pertanyaan:

> “Apa yang terjadi saat pengguna meminta aksi ini?”

Isinya:

- commands;
- queries;
- use case;
- orkestrator;
- handler aksi;
- koordinasi antara domain dan port.

### Perbedaan commands / queries

| Tipe | Tujuan | Mengubah data |
|---|---|---|
| Command | Menjalankan sebuah aksi | Ya |
| Query | Membaca atau menghitung sebuah informasi | Tidak |

Contoh:

| Command | Query |
|---|---|
| Menerapkan konfigurasi | Membaca konfigurasi saat ini |
| Menjalankan analisis | Mengambil hasil analisis |
| Mengekspor laporan | Menampilkan daftar item yang tersedia |
| Menghapus data | Melihat riwayat |

### Contoh

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Aturan

`application/` tidak berisi:

- tampilan di terminal;
- antarmuka Textual;
- perintah Rich;
- akses langsung ke basis data;
- panggilan langsung ke alat eksternal.

Ia mengoordinasikan, tetapi tidak mengimplementasikan detail teknis.

---

## 8. Folder `ports/`

### Peran

Folder `ports/` mendefinisikan **kontrak** yang diharapkan oleh aplikasi.

Sebuah port menjelaskan **apa yang dibutuhkan aplikasi**, tanpa menentukan cara implementasinya.

Umumnya berisi:

- `Protocol`;
- kelas abstrak `ABC`;
- antarmuka repository;
- antarmuka ekspor;
- antarmuka probe;
- antarmuka layanan eksternal;
- antarmuka penyimpanan.

### Contoh

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Peran |
|---|---|
| `Repository` | Membaca atau menyimpan data |
| `Exporter` | Menghasilkan keluaran dalam format tertentu |
| `Probe` | Mengumpulkan informasi sistem atau jaringan |
| `Storage` | Mengelola backend persistensi |

### Contoh konseptual

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Kontrak ini menyatakan:

> “Aplikasi membutuhkan objek yang mampu mengekspor laporan.”

Kontrak ini tidak menyatakan:

- apakah ekspor dalam format Markdown;
- apakah ekspor dalam format JSON;
- apakah berkas akan ditulis secara lokal;
- apakah ekspor akan dikirim melalui jaringan.

Pilihan-pilihan ini menjadi urusan `infrastructure/`.

### Aturan

Port adalah kontrak, bukan implementasi.

Port tidak boleh berisi:

- logika bisnis yang kompleks;
- akses disk;
- panggilan jaringan;
- implementasi konkret;
- dependensi langsung pada pustaka eksternal.

---

## 9. Folder `infrastructure/`

### Peran

Folder `infrastructure/` berisi **implementasi konkret** dari port.

Inilah lapisan yang berkomunikasi dengan dunia luar.

Isinya dapat berupa:

- akses berkas;
- akses basis data;
- ekspor Markdown, JSON, CSV, atau format lain;
- logging;
- panggilan jaringan;
- probe sistem;
- eksekusi terkendali alat eksternal;
- adaptor untuk pustaka pihak ketiga;
- implementasi repository;
- implementasi penyimpanan.

### Contoh

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

| Elemen | Peran |
|---|---|
| `sqlite_repository.py` | Mengimplementasikan repository dengan SQLite |
| `json_file_repository.py` | Mengimplementasikan repository dengan berkas JSON |
| `markdown_exporter.py` | Mengekspor laporan ke Markdown |
| `json_exporter.py` | Mengekspor laporan ke JSON |
| `process_probe.py` | Mengumpulkan informasi tentang proses |
| `filesystem_probe.py` | Mengumpulkan informasi tentang sistem berkas |
| `structured_logger.py` | Menghasilkan log terstruktur |

### Aturan

`infrastructure/` adalah satu-satunya lapisan yang boleh mengakses secara langsung:

- sistem berkas;
- jaringan;
- SQLite;
- pustaka eksternal;
- alat sistem;
- subproses, bila diperlukan dan terkendali.

Pemusatan ini memudahkan:

- pengujian;
- audit keamanan;
- penggantian backend;
- pembatasan efek samping.

---

## 10. Folder `interfaces/`

### Peran

Folder `interfaces/` berisi titik masuk yang terlihat oleh pengguna.

Ia memisahkan dengan jelas:

- CLI;
- TUI;
- kemungkinan antarmuka web atau API di masa depan.

### Struktur

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

| Antarmuka | Teknologi | Peran |
|---|---|---|
| `cli/` | Rich | Antarmuka baris perintah |
| `tui/` | Textual | Antarmuka interaktif di terminal |

### CLI

CLI adalah antarmuka baris perintah.

CLI memungkinkan:

- menjalankan aplikasi;
- mengeksekusi aksi tertentu;
- menampilkan hasil;
- mengotomatiskan tugas;
- mengintegrasikan alat ke dalam skrip;
- menggunakan aplikasi dari jarak jauh melalui SSH.

### TUI

TUI adalah antarmuka interaktif di terminal.

TUI memungkinkan:

- berpindah antarfitur;
- menampilkan informasi;
- menjalankan aksi;
- melihat hasil;
- menggunakan aplikasi tanpa menghafal semua perintah.

### Aturan

Antarmuka tidak berisi logika bisnis.

Antarmuka:

- menerima maksud pengguna;
- memanggil use case di `application/`;
- menampilkan hasil;
- menerjemahkan galat menjadi pesan yang mudah dipahami.

Antarmuka tidak boleh:

- memanggil infrastruktur secara langsung;
- menjalankan subproses;
- mengakses berkas secara langsung;
- berisi aturan bisnis;
- menduplikasi logika `application/`.

---

## 11. Folder `plugins/`

### Peran

Folder `plugins/` disediakan untuk **ekstensi bawaan**.

Folder ini memungkinkan penambahan fitur tanpa membebani inti proyek.

Sebuah plugin dapat, misalnya:

- menambahkan format ekspor;
- menambahkan probe;
- menambahkan perintah;
- menambahkan layar TUI;
- menambahkan integrasi eksternal;
- menambahkan kapabilitas opsional.

### Prinsip

Sebuah plugin harus mengikuti aturan yang sama dengan bagian proyek lainnya:

- tidak melewati port;
- tidak mengubah domain secara langsung;
- menyediakan fiturnya melalui kontrak yang jelas;
- tetap dapat dinonaktifkan tanpa merusak aplikasi.

### Struktur yang mungkin

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Aturan

Plugin adalah ekstensi, bukan pintu belakang.

Plugin harus mematuhi arsitektur keseluruhan dan tidak boleh menciptakan dependensi melingkar dengan inti proyek.

---

## 12. Folder `shared/`

### Peran

Folder `shared/` berisi utilitas lintas lapisan yang bukan milik domain, aplikasi, maupun infrastruktur.

Ia mengelompokkan fungsi generik yang dapat digunakan ulang.

Isinya dapat berupa:

- parsing;
- utilitas jaringan;
- pemformatan;
- manipulasi teks;
- helper tanggal;
- helper path;
- utilitas validasi generik;
- helper serialisasi.

### Contoh

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Folder | Peran |
|---|---|
| `parsing/` | Analisis teks, JSON, YAML, atau format lain |
| `network/` | Utilitas jaringan generik |
| `formatting/` | Pemformatan nilai, tanggal, ukuran, atau tabel |
| `utils/` | Fungsi utilitas lintas lapisan |

### Aturan

`shared/` tidak boleh menjadi folder serba ada.

Sebuah utilitas hanya masuk ke `shared/` jika ia:

- dapat digunakan ulang;
- generik;
- tidak bergantung pada use case tertentu;
- berguna bagi beberapa lapisan.

---

## 13. Ringkasan tanggung jawab

| Folder | Peran utama | Boleh bergantung pada | Tidak boleh bergantung pada |
|---|---|---|---|
| `app/` | Merakit dan menjalankan aplikasi | Semua lapisan | — |
| `core/` | Kosakata, konstanta, enum, dan eksepsi | `shared/` jika perlu | `infrastructure/`, `interfaces/` |
| `domain/` | Logika bisnis murni | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Mengorkestrasi use case | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Mendefinisikan kontrak | `domain/` jika perlu | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Mengimplementasikan port dan berkomunikasi dengan dunia luar | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Berinteraksi dengan pengguna | `application/`, `core/` | `infrastructure/` secara langsung |
| `plugins/` | Menambahkan ekstensi | Tergantung jenis ekstensi | Melewati arsitektur |
| `shared/` | Utilitas lintas lapisan | Tidak ada lapisan bisnis | Logika bisnis spesifik |

---

## 14. Contoh alur sebuah aksi

Misalkan seorang pengguna meminta ekspor laporan ke Markdown.

```text
1. Pengguna menjalankan perintah CLI.

2. interfaces/cli/
   Menerima perintah dan opsinya.

3. interfaces/cli/
   Memanggil use case yang sesuai di application/.

4. application/
   Memvalidasi maksud dan menyiapkan aksi.

5. application/
   Menggunakan domain untuk menyusun atau memvalidasi laporan.

6. application/
   Meminta ekspor melalui port ReportExporter.

7. infrastructure/
   Menyediakan implementasi MarkdownExporter.

8. infrastructure/
   Menulis berkas Markdown ke disk.

9. interfaces/cli/
   Menampilkan hasil kepada pengguna.
```

Diagram sederhana:

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
Berkas Markdown
```

---

## 15. Mengapa arsitektur ini?

### Keterbacaan

Setiap folder memiliki satu peran, sehingga lebih mudah menemukan tempat untuk menambah atau memperbaiki fitur.

### Kemudahan pengujian

Domain dapat diuji tanpa antarmuka, tanpa basis data, dan tanpa akses jaringan.

### Kemudahan pemeliharaan

Perubahan pada antarmuka, penyimpanan, atau alat eksternal tidak boleh mengharuskan penulisan ulang logika bisnis.

### Keamanan

Akses sensitif — berkas, jaringan, subproses, basis data — dipusatkan di `infrastructure/`. Hal ini memudahkan audit dan pengendalian.

### Kemudahan pengembangan

Anda dapat menambahkan:

- antarmuka baru;
- format ekspor baru;
- backend penyimpanan baru;
- plugin baru;
- probe sistem baru;

tanpa mengubah inti bisnis.

### Portabilitas

Aplikasi dapat berkembang ke lingkungan, sistem, atau mode interaksi lain tanpa terikat pada teknologi tertentu.

---

## 16. Aturan yang perlu diingat

- Domain itu murni.
- Aplikasi mengorkestrasi.
- Port menyatakan kebutuhan.
- Infrastruktur mengimplementasikan.
- Antarmuka menampilkan dan mengumpulkan.
- `app/` merakit.
- `core/` dan `shared/` menyediakan kosakata dan utilitas lintas lapisan.
- Plugin memperluas tanpa melewati arsitektur.

Dalam satu kalimat:

> **Aplikasi memisahkan apa yang dilakukannya, bagaimana ia melakukannya, dan bagaimana pengguna menggunakannya.**
