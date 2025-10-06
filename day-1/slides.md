# Otomatisasi Fundamental dengan N8N
## Membangun Alur Kerja Cerdas untuk Bisnis Anda

---

<!-- SECTION 1: Pengenalan & Konsep Dasar -->

## Agenda Pelatihan

- **Pengenalan:** Konsep inti otomatisasi, alur kerja (workflow), dan langkah (step)
- **Tugas 1:** Workflow pertama dengan Trigger Manually
- **Tugas 2:** Otomatisasi berbasis event & data dinamis
- **Tugas 3:** Multi-step workflow
- **Penutup:** Rekapitulasi & Q&A

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

## Dari Skenario ke Solusi N8N

### Bagaimana Cara Kerjanya?

Ingat skenario tadi: **"Customer isi form → Data masuk spreadsheet → Tim dapat notifikasi"**

Di N8N, kita memecahnya menjadi:
- 📍 **"Customer isi form"** = **Trigger** (pemicu yang memulai)
- ⚙️ **"Data masuk spreadsheet + notifikasi"** = **Action** (tindakan yang dijalankan)
- 🔗 **Trigger + Action** = **Workflow** (alur kerja lengkap)

---

## Konsep Inti: Trigger & Action

### Definisi yang Perlu Dipahami

- **Trigger (Pemicu):**
  - Step pertama yang memulai workflow
  - Menjawab pertanyaan: **"KAPAN workflow berjalan?"**
  - *Contoh: Setiap kali ada baris baru di Google Sheets*

- **Action (Tindakan):**
  - Step-step berikutnya setelah trigger
  - Menjawab pertanyaan: **"APA yang dilakukan sistem?"**
  - *Contoh: Kirim email, buat event calendar, simpan ke database*

---

## Prinsip Utama N8N

### Aturan Emas Otomatisasi

> **"Selama Trigger-nya ada di N8N dan Action-nya ada di N8N, kita bisa mengotomasikannya."**

Artinya:
- ✅ Jika aplikasi Anda punya trigger di N8N (Google Sheets, Telegram, Calendar)
- ✅ Dan tindakan yang Anda inginkan ada di N8N (Gmail, Slack, Database)
- ✅ **Maka Anda bisa menghubungkannya!**

**N8N punya 300+ integrasi aplikasi** - peluang otomasi hampir tak terbatas!

---

<!-- SECTION 2: Tugas 1 - Workflow Pertama -->

# Tugas 1: Kemenangan Pertama Anda

---

## Tugas 1: Workflow Pertama Anda

### Tujuan:
Memahami cara kerja workflow dan step dengan membuat otomatisasi sederhana: **menambahkan data ke Google Sheets dengan satu klik**.

### Apa yang Akan Dibuat:
- Trigger: **Trigger Manually** (klik tombol)
- Action: Tambah baris baru ke Google Sheets

---

## Konsep: Trigger Manually

### Trigger Paling Sederhana

**"Trigger Manually"** adalah cara paling dasar untuk menjalankan workflow:
- 👆 Workflow **hanya berjalan** saat Anda klik tombol **"Test workflow"**
- 🧪 **Sempurna untuk pengujian** dan belajar
- 🎯 **Cocok untuk tugas on-demand** yang tidak perlu otomatis

**Kapan menggunakannya:**
- Saat belajar membuat workflow pertama kali
- Testing workflow sebelum menggunakan trigger otomatis
- Proses yang memang butuh konfirmasi manual

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

## Berbagai Jenis Trigger di N8N

### Trigger Bisa Beragam!

Sekarang kita naik level dari "Trigger Manually". N8N punya banyak jenis trigger:

**📅 Schedule Trigger**
- Workflow berjalan berdasarkan jadwal (setiap jam, harian, mingguan)
- *Contoh: Kirim laporan otomatis setiap Senin pagi*

**🌐 Webhook Trigger**
- Workflow dipicu saat ada request HTTP dari aplikasi lain
- *Contoh: Ada pembayaran masuk dari Stripe*

**📊 App Event Triggers**
- Workflow dipicu oleh kejadian di aplikasi tertentu
- *Contoh: Google Sheets (baris baru), Gmail (email masuk), Telegram (pesan baru)*

---

## Berbagai Jenis Action di N8N

### Action = Yang Bisa Kita Lakukan

Setelah trigger, N8N bisa melakukan banyak action:

**📧 Komunikasi**
- Kirim email (Gmail, Outlook)
- Kirim pesan (Slack, Telegram, WhatsApp)

**📝 Data Management**
- Tambah/update data di Google Sheets, Airtable, Database
- Buat file di Google Drive, Dropbox

**📅 Scheduling**
- Buat/update event di Google Calendar
- Buat task di Asana, Trello

**🔗 Integration**
- Update CRM (HubSpot, Salesforce)
- Kirim data ke aplikasi lain via API

---

## Konsep Kunci: Data Dinamis

### Data yang Mengalir Antar Step

Di Tugas 2, kita akan menggunakan **Data Dinamis**:
- ❌ **Bukan** data statis yang kita ketik manual
- ✅ **Tapi** data asli dari trigger (nama, email, nomor telepon)
- 🔄 Data mengalir dari **Trigger** → **Action**

**Contoh:**
- Trigger dapat: `Nama: "Budi", Email: "budi@email.com"`
- Action gunakan: "Halo **Budi**, terima kasih sudah mendaftar di **budi@email.com**"

---

## Active vs Inactive Workflow

### Dua Mode Workflow

Setiap workflow di N8N punya 2 mode:

**🔴 Inactive (Mode Edit/Testing):**
- Workflow **TIDAK mendengarkan** trigger otomatis
- Hanya berjalan saat Anda klik tombol **"Test workflow"**
- **Gunakan saat:** Membuat, mengedit, atau testing workflow
- **Aman** untuk melakukan perubahan

**🟢 Active (Mode Production):**
- Workflow **terus mendengarkan** triggernya
- Berjalan **otomatis** saat ada event
- **Gunakan saat:** Workflow sudah siap dan tested
- **PENTING:** Workflow Tugas 2 & 3 harus **Active** agar berjalan otomatis!

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

<!-- SECTION 5: Penutup -->

## Rekapitulasi

### Anda Telah Mempelajari:

- ✅ Konsep fundamental **Workflow, Step, Trigger & Action**
- ✅ Prinsip utama: **"Jika Trigger & Action ada di N8N, bisa diotomatisasi"**
- ✅ Membuat workflow dengan **Trigger Manually** dan **App Event Triggers**
- ✅ Menggunakan **Data Dinamis** antar nodes
- ✅ Merangkai **Multi-Step Action** dalam satu workflow
- ✅ Mengenal berbagai jenis **Trigger** dan **Action** yang tersedia

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
