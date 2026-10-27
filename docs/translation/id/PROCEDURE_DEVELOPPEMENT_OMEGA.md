# Prosedur pengembangan — [PROJECT_NAME]

**Bahasa:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Kolom | Nilai |
|---|---|
| Proyek | [PROJECT_NAME] |
| Versi target | [TARGET_VERSION] |
| Penanggung jawab | [NAMA] |
| Tanggal dibuat | [YYYY-MM-DD] |
| Pembaruan terakhir | [YYYY-MM-DD] |
| Status umum | Draf / Sedang berjalan / Divalidasi / Dalam produksi |
| Lingkungan target | [Linux / Debian / Server / Workstation] |
| Bahasa utama | [Python / Bash / Lua / Lainnya] |
| Repositori | [URL_ATAU_PATH] |

## Aturan lintas fase

- [ ] Tidak ada kode yang ditulis sebelum rencana final divalidasi.
- [ ] Setiap keputusan penting didokumentasikan.
- [ ] Setiap anomali dicatat.
- [ ] Setiap perbaikan diuji.
- [ ] Setiap perubahan perilaku didokumentasikan.
- [ ] Pencadangan dilakukan sebelum setiap intervensi di produksi.
- [ ] AI menganalisis dan mengusulkan; manusia memutuskan, memvalidasi, dan menerapkan.
- [ ] Kode tetap selaras dengan dokumentasi final.

## Pemantauan global fase

| Fase | Pelaku | Hasil utama | Status | Tanggal validasi |
|---:|---|---|---|---|
| 1 | Manusia | Kebutuhan dan perancangan | [ ] | [YYYY-MM-DD] |
| 2 | Manusia | Draf arsitektur dan rencana awal | [ ] | [YYYY-MM-DD] |
| 3 | AI | Analisis, efek samping, rencana final | [ ] | [YYYY-MM-DD] |
| 4 | Manusia | Inti proyek dikodekan | [ ] | [YYYY-MM-DD] |
| 5 | AI | Audit kode, perbaikan, dan pengujian | [ ] | [YYYY-MM-DD] |
| 6 | Manusia | Pengujian nyata di produksi | [ ] | [YYYY-MM-DD] |
| 7 | AI | Rencana perbaikan dan pengodean final | [ ] | [YYYY-MM-DD] |
| 8 | Manusia | Pengujian final | [ ] | [YYYY-MM-DD] |
| 9 | Manusia | Draf dokumentasi | [ ] | [YYYY-MM-DD] |
| 10 | AI | Dokumentasi final | [ ] | [YYYY-MM-DD] |
| 11 | Manusia | Peluncuran ke produksi | [ ] | [YYYY-MM-DD] |

---

# Fase 1 — Refleksi, kebutuhan, penggunaan, dan perancangan

**Pelaku: Manusia**  
**Tujuan:** menetapkan masalah, pengguna, penggunaan nyata, batasan, dan cakupan proyek.

## 1. Masalah awal

- Masalah yang diidentifikasi: [PERLU DIISI]
- Situasi saat ini: [PERLU DIISI]
- Akibat dari masalah: [PERLU DIISI]
- Tujuan proyek: [PERLU DIISI]

## 2. Pengguna sasaran

| Pengguna | Kebutuhan utama | Tingkat teknis | Penggunaan yang direncanakan |
|---|---|---|---|
| [Pengguna 1] | [PERLU DIISI] | [Pemula / Teknis / Ahli] | [PERLU DIISI] |
| [Pengguna 2] | [PERLU DIISI] | [Pemula / Teknis / Ahli] | [PERLU DIISI] |

## 3. Skenario penggunaan

### Skenario normal

- Konteks: [PERLU DIISI]
- Tindakan pengguna: [PERLU DIISI]
- Hasil yang diharapkan: [PERLU DIISI]

### Skenario batas

- Konteks: [PERLU DIISI]
- Tindakan pengguna: [PERLU DIISI]
- Hasil yang diharapkan: [PERLU DIISI]

### Skenario galat

- Konteks: [PERLU DIISI]
- Tindakan pengguna: [PERLU DIISI]
- Hasil yang diharapkan: [PERLU DIISI]

### Skenario terlarang atau berbahaya

- Konteks: [PERLU DIISI]
- Perilaku yang diharapkan: [Penolakan / Peringatan / Pemblokiran / Pencatatan log]
- Alasan: [PERLU DIISI]

## 4. Fitur

### Wajib

- [ ] [Fitur 1]
- [ ] [Fitur 2]
- [ ] [Fitur 3]

### Berguna tetapi dapat ditunda

- [ ] [Fitur 1]
- [ ] [Fitur 2]

### Opsional

- [ ] [Fitur 1]

### Dikecualikan

- [ ] [Fitur yang dikecualikan]
- Alasan: [PERLU DIISI]

## 5. Batasan

| Bidang | Batasan | Prioritas |
|---|---|---|
| Sistem | [Linux / Debian / Versi] | [Tinggi / Sedang / Rendah] |
| Bahasa | [Python / Bash / Lua] | [Tinggi / Sedang / Rendah] |
| Dependensi | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Kinerja | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Keamanan | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Kompatibilitas | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Pemeliharaan | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Penerapan | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |

## 6. Risiko yang diidentifikasi

| Risiko | Dampak | Probabilitas | Langkah pencegahan |
|---|---|---|---|
| [Risiko 1] | [Rendah / Sedang / Tinggi] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] |
| [Risiko 2] | [Rendah / Sedang / Tinggi] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] |

## 7. Keputusan yang diambil

| ID | Keputusan | Alasan | Tanggal |
|---:|---|---|---|
| D-001 | [PERLU DIISI] | [PERLU DIISI] | [YYYY-MM-DD] |
| D-002 | [PERLU DIISI] | [PERLU DIISI] | [YYYY-MM-DD] |

## 8. Pertanyaan terbuka

- [ ] [Pertanyaan 1]
- [ ] [Pertanyaan 2]

## Validasi fase 1

- [ ] Masalah dirumuskan dengan jelas.
- [ ] Pengguna telah diidentifikasi.
- [ ] Skenario penggunaan utama telah dijelaskan.
- [ ] Fitur wajib telah didaftarkan.
- [ ] Cakupan proyek dinyatakan secara eksplisit.
- [ ] Batasan teknis telah diketahui.
- [ ] Risiko utama telah diidentifikasi.

**Status:** [ ] Draf / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 2 — Draf, komponen utama, dan rencana pengembangan

**Pelaku: Manusia**  
**Tujuan:** mengubah kebutuhan menjadi arsitektur logis dan rencana pengembangan yang dapat dijalankan.

## 1. Komponen utama

| Komponen | Tanggung jawab | Tidak boleh | Prioritas |
|---|---|---|---|
| Antarmuka / CLI | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Inti bisnis | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Konfigurasi | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Model data | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Layanan | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Penyimpanan | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Ekspor | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Log | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Keamanan | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| Pengujian | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |

## 2. Alur utama

```text
[Masukan pengguna]
    → [Antarmuka]
    → [Validasi]
    → [Inti bisnis]
    → [Layanan / Modul]
    → [Hasil]
    → [Keluaran / Penyimpanan / Log]
```

## 3. Modul yang direncanakan

| Modul | Peran | Dependensi | Prioritas |
|---|---|---|---|
| [module_1] | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| [module_2] | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |
| [module_3] | [PERLU DIISI] | [PERLU DIISI] | [Tinggi / Sedang / Rendah] |

## 4. Struktur direktori awal

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

## 5. Dependensi yang direncanakan

| Dependensi | Penggunaan | Versi minimum | Alasan |
|---|---|---|---|
| [Dependensi 1] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| [Dependensi 2] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |

## 6. Pembagian pengembangan

| Fase | Isi | Prioritas | Perkiraan |
|---:|---|---|---|
| 1 | Dasar: struktur, konfigurasi, galat, log | [Tinggi / Sedang] | [Durasi] |
| 2 | Model dan kontrak | [Tinggi / Sedang] | [Durasi] |
| 3 | Inti bisnis | [Tinggi / Sedang] | [Durasi] |
| 4 | Antarmuka / CLI | [Tinggi / Sedang] | [Durasi] |
| 5 | Penyimpanan / ekspor | [Tinggi / Sedang] | [Durasi] |
| 6 | Pengujian | [Tinggi / Sedang] | [Durasi] |
| 7 | Dokumentasi dan pengemasan | [Tinggi / Sedang] | [Durasi] |

## Validasi fase 2

- [ ] Komponen utama telah diidentifikasi.
- [ ] Setiap modul memiliki tanggung jawab yang jelas.
- [ ] Alur utama telah dijelaskan.
- [ ] Struktur direktori awal telah ditetapkan.
- [ ] Dependensi utama telah diidentifikasi.
- [ ] Urutan pengembangan telah ditetapkan.
- [ ] Belum ada pengembangan yang dimulai.

**Status:** [ ] Draf / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 3 — Analisis AI, efek samping, dan rencana final

**Pelaku: AI**  
**Tujuan:** menganalisis dokumen yang dibuat manusia, mengidentifikasi risiko, dan menghasilkan rencana final yang dapat dijalankan.

## 1. Dokumen yang dianalisis

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Dokumen lain]

## 2. Prompt analisis AI

```text
Analisis proyek ini tanpa menulis kode.

1. Deteksi inkonsistensi.
2. Deteksi fungsi yang hilang.
3. Deteksi tanggung jawab yang salah tempat.
4. Identifikasi kemungkinan efek samping.
5. Identifikasi kasus kegagalan.
6. Identifikasi risiko keamanan.
7. Identifikasi masalah kompatibilitas.
8. Usulkan struktur proyek yang lebih kokoh.
9. Usulkan rencana pengembangan final.
10. Tunjukkan poin-poin yang harus tetap menjadi keputusan manusia.
```

## 3. Inkonsistensi yang terdeteksi

| ID | Deskripsi | Dampak | Usulan | Keputusan manusia |
|---:|---|---|---|---|
| A-001 | [PERLU DIISI] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] | [Diterima / Ditolak / Ditunda] |
| A-002 | [PERLU DIISI] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] | [Diterima / Ditolak / Ditunda] |

## 4. Efek samping yang diidentifikasi

| ID | Efek samping | Pemicu | Dampak | Pencegahan | Status |
|---:|---|---|---|---|---|
| SE-001 | [PERLU DIISI] | [PERLU DIISI] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] | [Terbuka / Ditangani / Diterima] |
| SE-002 | [PERLU DIISI] | [PERLU DIISI] | [Rendah / Sedang / Tinggi] | [PERLU DIISI] | [Terbuka / Ditangani / Diterima] |

## 5. Kasus kegagalan yang perlu diantisipasi

| Kasus | Perilaku yang diharapkan | Pesan / log yang diharapkan | Pengujian terkait |
|---|---|---|---|
| Berkas tidak ada | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| Izin ditolak | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| Jaringan tidak tersedia | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| Masukan tidak valid | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| Interupsi oleh pengguna | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |
| Data rusak | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] |

## 6. Risiko keamanan

| Risiko | Skenario | Langkah | Prioritas |
|---|---|---|---|
| [Risiko 1] | [PERLU DIISI] | [PERLU DIISI] | [P0 / P1 / P2] |
| [Risiko 2] | [PERLU DIISI] | [PERLU DIISI] | [P0 / P1 / P2] |

## 7. Rencana pengembangan final

| Fase | Tujuan | Hasil | Kriteria penyelesaian | Dependensi |
|---:|---|---|---|---|
| 1 | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [Tidak ada] |
| 2 | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [Fase 1] |
| 3 | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [Fase 2] |

## Validasi fase 3

- [ ] Inkonsistensi telah ditangani atau didokumentasikan.
- [ ] Efek samping telah diidentifikasi.
- [ ] Kasus kegagalan telah diantisipasi.
- [ ] Risiko keamanan telah ditangani.
- [ ] Rencana final telah divalidasi oleh manusia.
- [ ] Keputusan final telah dicatat.

**Status:** [ ] Draf / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 4 — Pengodean inti proyek

**Pelaku: Manusia**  
**Tujuan:** mengembangkan inti fungsional tanpa menambahkan fitur di luar cakupan.

## 1. Cakupan pengodean

- [ ] Struktur proyek
- [ ] Lingkungan virtual
- [ ] Dependensi
- [ ] Konfigurasi
- [ ] Model data
- [ ] Eksepsi
- [ ] Logging
- [ ] Layanan bisnis
- [ ] Inti bisnis
- [ ] Pengujian unit
- [ ] CLI / antarmuka
- [ ] Integrasi

## 2. Urutan implementasi

| Urutan | Elemen | Berkas / modul | Status | Commit |
|---:|---|---|---|---|
| 1 | [Elemen] | [path] | [ ] | [hash] |
| 2 | [Elemen] | [path] | [ ] | [hash] |
| 3 | [Elemen] | [path] | [ ] | [hash] |

## 3. Aturan commit

- Satu commit = satu niat.
- Jangan mencampur fitur, perbaikan, dan refaktor.
- Pesan yang disarankan:

```text
[type]: [deskripsi singkat]

[type] = feat, fix, refactor, test, docs, chore
```

Contoh:

```text
feat: tambahkan pemuatan dan validasi konfigurasi
```

## 4. Pengujian awal

| Pengujian | Tujuan | Perintah | Hasil yang diharapkan | Status |
|---|---|---|---|---|
| [Pengujian 1] | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [ ] |
| [Pengujian 2] | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [ ] |

## Validasi fase 4

- [ ] Inti bisnis berfungsi.
- [ ] Masukan utama divalidasi.
- [ ] Galat utama ditangani.
- [ ] Pengujian unit lulus.
- [ ] Proyek dapat berjalan dalam mode dasar.
- [ ] Tidak ada fitur di luar cakupan yang ditambahkan.

**Status:** [ ] Sedang berjalan / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 5 — Analisis kode, perbaikan, dan pengujian oleh AI

**Pelaku: AI**  
**Tujuan:** mendeteksi cacat, efek samping, dan risiko sebelum pengujian nyata.

## 1. Prompt audit AI

```text
Analisis kode tanpa menulis ulang seluruhnya.

1. Periksa kesesuaian dengan rencana pengembangan.
2. Deteksi bug yang mungkin terjadi.
3. Deteksi efek samping.
4. Deteksi kebocoran sumber daya.
5. Deteksi galat yang tidak ditangani.
6. Deteksi masukan yang tidak divalidasi.
7. Deteksi masalah keamanan.
8. Deteksi masalah kinerja.
9. Deteksi kode mati.
10. Deteksi tanggung jawab yang salah tempat.
11. Usulkan perbaikan yang terarah.
12. Usulkan pengujian yang belum ada.
```

## 2. Hasil audit

| ID | Berkas / fungsi | Temuan | Tingkat keparahan | Perbaikan yang diusulkan | Status |
|---:|---|---|---|---|---|
| C-001 | [path] | [PERLU DIISI] | [Kritis / Mayor / Minor] | [PERLU DIISI] | [Terbuka / Diperbaiki / Divalidasi] |
| C-002 | [path] | [PERLU DIISI] | [Kritis / Mayor / Minor] | [PERLU DIISI] | [Terbuka / Diperbaiki / Divalidasi] |

## 3. Pengujian yang ditambahkan

| Pengujian | Tujuan | Berkas pengujian | Status |
|---|---|---|---|
| [Pengujian 1] | [PERLU DIISI] | [path] | [ ] |
| [Pengujian 2] | [PERLU DIISI] | [path] | [ ] |

## Validasi fase 5

- [ ] Bug kritis telah diperbaiki.
- [ ] Efek samping telah ditangani atau didokumentasikan.
- [ ] Pengujian unit lulus.
- [ ] Pengujian integrasi lulus.
- [ ] Kode sesuai dengan rencana final.
- [ ] Perbaikan diterapkan secara bertahap.

**Status:** [ ] Sedang berjalan / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 6 — Studi nyata dan pengujian di produksi

**Pelaku: Manusia**  
**Tujuan:** memvalidasi perangkat lunak dalam kondisi nyata dan mencatat semua anomali.

## 1. Lingkungan pengujian

| Elemen | Nilai |
|---|---|
| Mesin | [PERLU DIISI] |
| Sistem | [PERLU DIISI] |
| Versi perangkat lunak | [PERLU DIISI] |
| Lingkungan | [Produksi terkendali / Praproduksi / Server nyata] |
| Pencadangan dilakukan | [Ya / Tidak] |
| Tanggal pencadangan | [YYYY-MM-DD] |
| Metode rollback | [PERLU DIISI] |

## 2. Skenario yang diuji

| ID | Skenario | Perintah | Hasil yang diharapkan | Hasil yang diperoleh | Status |
|---:|---|---|---|---|---|
| T-001 | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [OK / KO / Sebagian] |
| T-002 | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [OK / KO / Sebagian] |

## 3. Kisi pengamatan

| Bidang | Elemen yang diamati | Hasil | Komentar |
|---|---|---|---|
| Fungsional | Fungsi yang diharapkan | [OK / KO] | [PERLU DIISI] |
| Antarmuka | Kejelasan perintah | [OK / KO] | [PERLU DIISI] |
| Kinerja | Waktu eksekusi | [OK / KO] | [PERLU DIISI] |
| Stabilitas | Tidak ada crash tak terduga | [OK / KO] | [PERLU DIISI] |
| Galat | Kejelasan pesan | [OK / KO] | [PERLU DIISI] |
| Log | Kualitas dan kegunaan | [OK / KO] | [PERLU DIISI] |
| Keamanan | Perilaku yang aman | [OK / KO] | [PERLU DIISI] |
| Kompatibilitas | Berjalan di target nyata | [OK / KO] | [PERLU DIISI] |
| Estetika | Keterbacaan keluaran | [OK / KO] | [PERLU DIISI] |
| Penggunaan nyata | Kelancaran alur kerja | [OK / KO] | [PERLU DIISI] |

## 4. Log anomali

| ID | Tanggal | Tingkat keparahan | Deskripsi | Log | Hipotesis | Perbaikan yang diusulkan | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [YYYY-MM-DD] | [Kritis / Mayor / Minor / Estetika] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [Terbuka / Diperbaiki / Divalidasi] |
| BUG-002 | [YYYY-MM-DD] | [Kritis / Mayor / Minor / Estetika] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [PERLU DIISI] | [Terbuka / Diperbaiki / Divalidasi] |

## Validasi fase 6

- [ ] Semua skenario kritis telah diuji.
- [ ] Bug telah dicatat.
- [ ] Masalah ergonomi telah dicatat.
- [ ] Masalah estetika telah dicatat.
- [ ] Tidak ada bug kritis yang memblokir yang diabaikan.

**Status:** [ ] Sedang berjalan / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 7 — Rencana peningkatan, perbaikan, dan pengodean final

**Pelaku: AI**  
**Tujuan:** mengubah anomali menjadi perbaikan berprioritas, lalu menerapkan perubahan kode yang diperlukan.

## 1. Prompt analisis anomali

```text
Berikut log pengujian di produksi.

1. Urutkan anomali berdasarkan tingkat keparahan.
2. Kelompokkan anomali yang saling terkait.
3. Identifikasi kemungkinan penyebabnya.
4. Usulkan perbaikan minimal untuk setiap anomali.
5. Tunjukkan risiko regresi.
6. Usulkan pengujian yang perlu ditambahkan.
7. Usulkan peningkatan ergonomi.
8. Usulkan peningkatan estetika.
9. Ubah hanya yang diperlukan.
10. Pertahankan perilaku yang sudah divalidasi.
```

## 2. Prioritas anomali

| Prioritas | Jenis | Anomali terkait | Penanganan |
|---|---|---|---|
| P0 | Crash, kehilangan data, kerentanan | [BUG-XXX] | Perbaikan segera |
| P1 | Fitur tidak benar | [BUG-XXX] | Perbaikan sebelum validasi final |
| P2 | Pengalaman pengguna buruk | [BUG-XXX] | Perbaikan jika wajar |
| P3 | Estetika, pesan, format | [BUG-XXX] | Perbaikan atau penundaan |
| P4 | Peningkatan di masa depan | [BUG-XXX] | Backlog |

## 3. Perbaikan yang diterapkan

| ID | Anomali | Perbaikan | Berkas yang diubah | Pengujian yang ditambahkan | Risiko regresi | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [PERLU DIISI] | [path] | [path] | [Rendah / Sedang / Tinggi] | [Diterapkan / Divalidasi] |
| FIX-002 | [BUG-XXX] | [PERLU DIISI] | [path] | [path] | [Rendah / Sedang / Tinggi] | [Diterapkan / Divalidasi] |

## Validasi fase 7

- [ ] Setiap anomali memiliki status yang jelas.
- [ ] Perbaikan diterapkan sesuai prioritas.
- [ ] Pengujian non-regresi lulus.
- [ ] Perilaku yang divalidasi tetap dipertahankan.
- [ ] Setiap perbaikan didokumentasikan.

**Status:** [ ] Sedang berjalan / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 8 — Pengujian final

**Pelaku: Manusia**  
**Tujuan:** memvalidasi versi kandidat sebelum dokumentasi final dan peluncuran stabil ke produksi.

## 1. Pengujian validasi

| Pengujian | Tujuan | Perintah | Hasil yang diharapkan | Hasil yang diperoleh | Status |
|---|---|---|---|---|---|
| Skenario normal | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Skenario galat | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Opsi CLI | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Konfigurasi | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Izin | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Interupsi | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |
| Non-regresi | [PERLU DIISI] | [perintah] | [PERLU DIISI] | [PERLU DIISI] | [ ] |

## 2. Daftar periksa final

- [ ] Proyek berjalan dengan benar.
- [ ] Perintah utama berfungsi.
- [ ] Galat mudah dipahami.
- [ ] Log dapat dimanfaatkan.
- [ ] Tidak ada bug kritis.
- [ ] Tidak ada regresi yang terdeteksi.
- [ ] Kinerja dapat diterima.
- [ ] Keamanan sesuai persyaratan.
- [ ] Versi dapat diidentifikasi.
- [ ] Rollback dimungkinkan.

## Validasi fase 8

**Keputusan:** [ ] Versi kandidat / [ ] Kembali ke perbaikan  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 9 — Draf dokumentasi

**Pelaku: Manusia**  
**Tujuan:** mendokumentasikan perangkat lunak sebagaimana ia benar-benar berfungsi.

## 1. Dokumen yang harus dibuat

| Dokumen | Tujuan | Status |
|---|---|---|
| `README.md` | Pengenalan dan memulai cepat | [ ] |
| `USER_GUIDE.md` | Panduan penggunaan rinci dan mudah dipahami | [ ] |
| `TECHNICAL_GUIDE.md` | Arsitektur dan cara kerja internal | [ ] |
| `DEVELOPER_GUIDE.md` | Lingkungan, pengujian, konvensi | [ ] |
| `INSTALLATION.md` | Prasyarat dan instalasi | [ ] |
| `SECURITY.md` | Risiko, izin, praktik terbaik | [ ] |
| `TROUBLESHOOTING.md` | Galat umum dan solusinya | [ ] |
| `CHANGELOG.md` | Riwayat versi | [ ] |

## 2. Isi yang perlu diperiksa

- [ ] Setiap perintah didokumentasikan.
- [ ] Setiap opsi didokumentasikan.
- [ ] Setiap berkas konfigurasi didokumentasikan.
- [ ] Setiap dependensi didokumentasikan.
- [ ] Setiap galat umum dijelaskan.
- [ ] Batasan dinyatakan secara eksplisit.
- [ ] Contoh dapat diuji.

## Validasi fase 9

**Status:** [ ] Draf / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 10 — Penataan dan dokumentasi final

**Pelaku: AI**  
**Tujuan:** melengkapi, menyusun, dan menyelaraskan dokumentasi tanpa mengarang perilaku yang tidak ada di kode.

## 1. Prompt pelengkapan dokumentasi

```text
Berikut draf dokumentasi.

1. Periksa konsistensi dengan kode yang sebenarnya.
2. Deteksi fungsi yang tidak terdokumentasi.
3. Deteksi opsi CLI yang tidak terdokumentasi.
4. Deteksi pesan galat yang tidak dijelaskan.
5. Deteksi dependensi yang hilang.
6. Deteksi langkah instalasi yang hilang.
7. Deteksi inkonsistensi antardokumen.
8. Tingkatkan struktur dan keterbacaan.
9. Lengkapi bagian yang hilang.
10. Jangan mengubah perilaku yang dijelaskan tanpa bukti di kode.
```

## 2. Pemeriksaan dokumentasi

| Pemeriksaan | Status | Komentar |
|---|---|---|
| Konsistensi dengan kode | [ ] | [PERLU DIISI] |
| Perintah terdokumentasi | [ ] | [PERLU DIISI] |
| Opsi terdokumentasi | [ ] | [PERLU DIISI] |
| Kode keluar terdokumentasi | [ ] | [PERLU DIISI] |
| Konfigurasi terdokumentasi | [ ] | [PERLU DIISI] |
| Dependensi terdokumentasi | [ ] | [PERLU DIISI] |
| Galat umum terdokumentasi | [ ] | [PERLU DIISI] |
| Contoh dapat diuji | [ ] | [PERLU DIISI] |
| Struktur yang selaras | [ ] | [PERLU DIISI] |

## Validasi fase 10

**Status:** [ ] Draf / [ ] Divalidasi  
**Divalidasi oleh:** [NAMA]  
**Tanggal:** [YYYY-MM-DD]

---

# Fase 11 — Peluncuran final ke produksi

**Pelaku: Manusia**  
**Tujuan:** menerapkan versi yang telah divalidasi, didokumentasikan, dan diuji.

## 1. Persiapan

- [ ] Versi divalidasi pada fase 8.
- [ ] Dokumentasi final divalidasi pada fase 10.
- [ ] Pencadangan lingkungan yang ada telah dilakukan.
- [ ] Prosedur rollback tersedia.
- [ ] Tag versi telah dibuat.

Perintah:

```bash
git tag -a v[VERSION] -m "Versi stabil [VERSION]"
git push origin v[VERSION]
```

## 2. Pengemasan

```bash
python -m build
```

Verifikasi:

```bash
sha256sum dist/*
```

## 3. Penerapan

| Langkah | Perintah / tindakan | Status | Komentar |
|---:|---|---|---|
| 1 | Pencadangan | [ ] | [PERLU DIISI] |
| 2 | Terapkan versi yang diberi tag | [ ] | [PERLU DIISI] |
| 3 | Periksa layanan | [ ] | [PERLU DIISI] |
| 4 | Periksa log | [ ] | [PERLU DIISI] |
| 5 | Uji perintah utama | [ ] | [PERLU DIISI] |
| 6 | Dokumentasikan versi yang diterapkan | [ ] | [PERLU DIISI] |

## 4. Pemeriksaan pascapenerapan

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] Layanan aktif.
- [ ] Tidak ada galat kritis di log.
- [ ] Perintah utama merespons.
- [ ] Versi yang diterapkan sesuai dengan tag yang divalidasi.
- [ ] Rollback terdokumentasi dan dapat diuji.

## Validasi final

| Kolom | Nilai |
|---|---|
| Versi yang diterapkan | [VERSION] |
| Tanggal peluncuran produksi | [YYYY-MM-DD] |
| Lingkungan | [PERLU DIISI] |
| Penanggung jawab | [NAMA] |
| Rollback diuji | [Ya / Tidak] |
| Status final | [Dalam produksi / Gagal / Rollback] |

---

# Riwayat perubahan dokumen

| Tanggal | Versi | Penulis | Perubahan |
|---|---|---|---|
| [YYYY-MM-DD] | 0.1 | [NAMA] | Pembuatan templat |
| [YYYY-MM-DD] | [VERSION] | [NAMA] | [PERLU DIISI] |
