# Otomatisasi Fundamental dengan N8N
## Membangun Alur Kerja Cerdas untuk Bisnis Anda

---

<!-- SECTION 1: Pengenalan & Konsep Dasar -->

## Agenda Pelatihan

- **Pengenalan:** Konsep inti otomatisasi, alur kerja (workflow), dan langkah (step)
- **Demo & Praktik (Tugas 1):** Trigger Manual
- **Demo & Praktik (Tugas 2):** Trigger Otomatis & Data Dinamis
- **Demo & Praktik (Tugas 3):** Merangkai Beberapa Aksi
- **Manajemen Workflow:** Cara mengelola & memonitor alur kerja Anda
- **Tantangan & Penutup**

---

## Masalah: Tugas Manual yang Melelahkan

### Pernah Mengalami Ini?

Setiap hari, tim Anda menghabiskan waktu untuk tugas repetitif:

- **Marketing:** Menyalin data lead dari form ke CRM
- **Sales:** Mengirim email follow-up satu per satu
- **Finance:** Membuat laporan mingguan dari spreadsheet
- **Operations:** Memberi notifikasi manual saat ada order baru

---

## Solusi: Otomatisasi Alur Kerja (Workflow)

### Bagaimana Jika Sistem Bisa Melakukannya untuk Anda?

Dengan otomatisasi, kita merancang sebuah **Workflow**, yaitu serangkaian langkah yang kita "ajarkan" kepada komputer untuk dieksekusi secara otomatis.

Ini memungkinkan tim Anda untuk fokus pada pekerjaan yang lebih strategis.

---

## Anatomi Sebuah Workflow

### Workflow = Serangkaian Langkah (Step)

- **Workflow:**
  - Keseluruhan alur kerja dari awal hingga akhir
  - Seperti resep masakan yang lengkap

- **Step (atau Node):**
  - Satu blok bangunan tunggal di dalam workflow
  - Setiap step memiliki satu tugas spesifik
  - Seperti satu instruksi dalam resep: "potong bawang", "tumis bumbu"

---

## Konsep Inti: Trigger & Action

### Setiap Workflow Dimulai dengan Trigger

- **Trigger (Pemicu):**
  - **Step pertama** yang memulai sebuah workflow
  - Seperti alarm yang membangunkan sistem
  - *Contoh: "Setiap kali ada baris baru di Google Sheets"*

- **Action (Tindakan):**
  - **Step-step berikutnya** yang dieksekusi setelah workflow dipicu
  - Pekerjaan yang dilakukan sistem
  - *Contoh: "Buat undangan di Google Calendar"*

---

<!-- SECTION 2: Tugas 1 - Workflow Pertama -->

# Tugas 1: Kemenangan Pertama Anda

---

## Tugas 1: Workflow Pertama Anda

### Tujuan:
Memahami cara kerja workflow dan step dengan membuat otomatisasi sederhana: **menambahkan data ke Google Sheets dengan satu klik**.

### Apa yang Akan Dibuat:
- Trigger: Manual (klik tombol)
- Action: Tambah baris baru ke Google Sheets

---

## Konsep Kunci: Eksekusi Workflow & Step

- **Execute Workflow:**
  - Menjalankan **seluruh rangkaian step** dalam workflow
  - Dari Trigger hingga Action terakhir
  - Seperti menjalankan resep masakan dari awal sampai selesai

- **Execute Step (Single Step):**
  - Menjalankan **hanya satu step** yang kita pilih
  - Berguna untuk menguji logika di tengah-tengah workflow
  - Tidak perlu menjalankan semuanya

---

## Yuk Kita Coba! (Tugas 1)

### Saatnya Action!

Mari kita buat workflow pertama bersama-sama dari awal hingga akhir.

**Yang akan kita lakukan:**
- Menambah node baru
- Menghubungkan antar node
- Konfigurasi setiap node
- Menjalankan workflow

---

## WAKTUNYA PRAKTIK! (Tugas 1)

### Sekarang Giliran Anda

- Buka dokumen panduan **Tugas 1**
- Ikuti langkah-langkah yang sama seperti yang didemonstrasikan untuk membangun workflow pertama Anda
- Jangan ragu bertanya jika ada kendala!

**Target:** Workflow yang bisa menambah data ke Google Sheets dengan satu klik

---

<!-- SECTION 3: Tugas 2 - Workflow Otomatis -->

# Tugas 2: Workflow yang Berjalan Sendiri

---

## Tugas 2: Otomatisasi Cerdas Berbasis Event

### Tujuan:
Membuat workflow yang berjalan **secara otomatis** setiap kali ada pendaftar baru, dan menggunakan data pendaftar untuk membuat undangan kalender.

### Apa yang Akan Dibuat:
- Trigger: Google Sheets (otomatis saat ada baris baru)
- Action: Buat event di Google Calendar dengan data dari pendaftar

---

## Konsep Kunci: Trigger Otomatis & Data Dinamis

- **Trigger Otomatis:**
  - Workflow "mendengarkan" kejadian di aplikasi lain
  - Berjalan sendiri tanpa perlu kita suruh
  - Seperti alarm pintar yang tahu kapan harus berbunyi

- **Data Dinamis:**
  - Tidak lagi menggunakan data statis
  - Menggunakan `Nama` dan `Email` asli dari pendaftar
  - Data mengalir dari step ke step

---

## Yuk Kita Coba! (Tugas 2)

### Naik Level!

Mari kita buat workflow pendaftaran otomatis bersama-sama.

**Yang akan kita lakukan:**
- Setup Google Sheets trigger
- Mengambil data dari trigger
- Menggunakan data dinamis di Google Calendar
- Handle jika trigger tidak tersedia

---

## WAKTUNYA PRAKTIK! (Tugas 2)

### Mari Kita Otomatisasi!

- Buka dokumen panduan **Tugas 2**
- Tiru langkah-langkah demo untuk membangun workflow pendaftaran otomatis Anda
- Test dengan menambah baris baru di Google Sheets

**Target:** Workflow yang otomatis membuat event calendar saat ada pendaftar baru

---

<!-- SECTION 4: Tugas 3 - Multi-Step Workflow -->

# Tugas 3: Merangkai Beberapa Aksi

---

## Tugas 3: Multi-Step Workflow

### Tujuan:
Membuat satu trigger memicu **serangkaian tindakan berurutan**.

Setelah membuat undangan kalender, sistem juga akan mengirim notifikasi email internal.

### Apa yang Akan Dibuat:
- Trigger: Google Sheets (dari Tugas 2)
- Action 1: Buat event di Google Calendar
- Action 2: Kirim email notifikasi ke tim

---

## Konsep Kunci: Merangkai Aksi (Chaining Actions)

### `Trigger → Action 1 → Action 2 → ...`

Di N8N, kita bisa merangkai step aksi sebanyak yang kita butuhkan.

Output dari step sebelumnya bisa digunakan sebagai input untuk step berikutnya, menciptakan alur kerja yang kompleks dan powerful.

**Contoh Nyata:**
- Pendaftar baru → Buat calendar event → Kirim email → Update CRM → Notif Telegram

---

## Yuk Kita Coba! (Tugas 3)

### Rangkai Logikanya!

Mari kita tambahkan step notifikasi email ke workflow yang sudah ada.

**Yang akan kita lakukan:**
- Menduplikasi workflow (best practice!)
- Menambah node ke workflow existing
- Menghubungkan multiple nodes
- Menggunakan data dari multiple sources

---

## WAKTUNYA PRAKTIK! (Tugas 3)

### Tambahkan Step Baru!

- Buka dokumen panduan **Tugas 3**
- Ikuti langkah-langkahnya untuk menambahkan aksi notifikasi email pada workflow Anda
- Test end-to-end: Sheets → Calendar → Email

**Target:** Workflow lengkap dengan 2 actions yang berjalan berurutan

---

<!-- SECTION 5: Manajemen Workflow -->

# Mengelola Workflow Anda

---

## Mengelola Workflow Anda

### Membangun itu satu hal, mengelola adalah hal lain.

Mari pelajari beberapa praktik terbaik untuk menjaga workflow kita tetap andal dan terorganisir.

---

## Active vs. Inactive

- **Inactive (Mode Edit/Uji Coba):**
  - Workflow HANYA berjalan jika ditekan "Execute Workflow"
  - Aman untuk membangun dan melakukan perubahan
  - Trigger tidak mendengarkan event

- **Active (Mode Produksi):**
  - Workflow "mendengarkan" triggernya secara terus-menerus
  - Berjalan otomatis saat ada event
  - **Penting:** Workflow berbasis event seperti Tugas 2 & 3 **harus Active** agar bisa berjalan otomatis!

---

## Memonitor & Debug: Tab Executions

### Di mana kita bisa melihat riwayat?

Tab **Executions** adalah log aktivitas workflow Anda.

- ✅ **Success (Hijau):** Workflow berjalan lancar
- ❌ **Error (Merah):** Terjadi masalah. Klik untuk melihat detailnya
- ⏳ **Running (Biru):** Sedang berjalan
- ⏸️ **Waiting (Kuning):** Menunggu input/event

**Tips:** Selalu cek Executions untuk debugging!

---

## Praktik Terbaik: Duplikasi & Download

### Protect Your Work!

- **Duplicate:**
  - Cara aman untuk mencoba ide baru tanpa merusak workflow yang sudah berfungsi
  - Seperti "Save As" di Word
  - Gunakan sebelum melakukan perubahan besar

- **Download:**
  - Menyimpan workflow sebagai file JSON untuk backup atau berbagi dengan tim
  - Version control sederhana
  - Import kembali kapan saja

---

<!-- SECTION 6: Penutup & Tantangan -->

# Tantangan Terakhir

---

## Tantangan Terakhir: Bereksplorasi!

### Sekarang Giliran Anda!

**Tugas:** Duplikasi workflow Tugas 3 dan tambahkan **satu Step Aksi lagi** setelah node Gmail.

**Tujuan:** Mendorong Anda untuk menjelajahi berbagai node yang tersedia dan berkreasi.

**Saran Node:**
- Telegram (kirim notif ke grup)
- Slack (posting ke channel)
- Airtable (simpan record)
- HTTP Request (webhook ke sistem lain)

---

## Rekapitulasi

### Anda Telah Mempelajari:

- ✅ Konsep fundamental **Workflow, Step, Trigger & Action**
- ✅ Cara **mengeksekusi** keseluruhan workflow atau satu step
- ✅ Membuat workflow dengan trigger **Manual** dan **Otomatis**
- ✅ Menggunakan **Data Dinamis** antar nodes
- ✅ Merangkai **Multi-Step Action** dalam satu workflow
- ✅ Dasar-dasar **Manajemen Workflow** (Active/Inactive, Executions, Duplicate)

**Anda sekarang punya skill untuk mengotomatisasi proses bisnis!**

---

## Q & A

### Ada Pertanyaan?

---

## Terima Kasih!

### Selamat Mengotomatisasi!

**Next Steps:**
- Eksplorasi 300+ nodes yang tersedia
- Gabung N8N Community untuk inspirasi
- Mulai otomatisasi proses di pekerjaan Anda

**Contact:**
[Nama Anda/Perusahaan]
[Email/Social Media]
