# N8N Tutorial - Day 1

## Pengenalan N8N untuk Automation

---

<!-- SECTION 1: Introduction -->
# Introduction N8N

---

## Apa itu N8N?

![N8N Logo](day-1/images/n8n-logo.png)
<!-- Placeholder: Logo N8N -->

- **N8N** adalah tool untuk otomatisasi pekerjaan bisnis Anda
- Menghubungkan 300+ aplikasi favorit Anda tanpa perlu coding
- Seperti main puzzle - drag & drop aja!
- Bisa dijalankan sendiri, data tetap aman di tangan Anda

Note:
Bayangkan tidak perlu lagi copy-paste data manual, atau mengecek email satu-satu. N8N bisa bantu otomatisasi semua itu!

---

## Target Hari Ini

Setelah sesi ini, peserta dapat:

- ✅ Mengenal cara kerja N8N untuk bisnis
- ✅ Membuat otomatisasi pertama Anda
- ✅ Menggunakan berbagai cara memulai otomatisasi
- ✅ Mengelola koneksi ke aplikasi favorit
- ✅ Memantau dan mengecek hasil otomatisasi

---

<!-- SECTION 2: Demo Workflow -->
# Demo: Workflow Pertama Anda

---

## Demo: Otomatisasi Customer Inquiry

![Customer Inquiry Workflow](day-1/images/customer-inquiry-workflow.png)
<!-- Placeholder: Screenshot workflow customer inquiry -->

### Skenario Bisnis:
**Customer Bertanya** → **Respon Otomatis** → **Simpan Lead** → **Notifikasi Tim**

*Seperti punya asisten virtual 24/7 untuk bisnis Anda*

---

## Live Demo: Dari Pertanyaan ke Penjualan

![Live Demo](day-1/images/live-demo-business.png)
<!-- Placeholder: Screenshot demo bisnis real -->

### Yang Terjadi Otomatis:
1. **Customer isi form kontak** di website Anda
2. **Email welcome** langsung terkirim ke customer
3. **Data tersimpan** di Google Sheets untuk follow-up
4. **Tim sales dapat notifikasi** di Slack ada lead baru

---

<!-- SECTION 3: Workflow Concepts -->
# Memahami Konsep Workflow dan Node

---

## Apa itu Workflow?

![Workflow Concept](day-1/images/workflow-concept.png)
<!-- Placeholder: Diagram konsep workflow dengan panah -->

**Workflow** = Seperti SOP bisnis, tapi dijalankan otomatis oleh komputer. Input yang kita masukkan akan diproses, dan dapat menghasilkan output.

### Contoh Sederhana: Proses Order Kopi Online
1. **Input**: Customer pesan kopi via WhatsApp
2. **Proses**: Catat pesanan → Cek stok → Hitung total
3. **Output**: Konfirmasi ke customer + notifikasi ke barista

**Tanpa N8N**: Manual copy-paste, buka tutup aplikasi berkali-kali
**Dengan N8N**: Sekali setup, semua otomatis 24/7!

---

## Anatomik Node

![Node Anatomy](day-1/images/node-anatomy.png)
<!-- Placeholder: Screenshot node dengan label bagian-bagiannya -->

### Komponen Node:
- **Input Connection** - Menerima data
- **Node Icon & Name** - Identifikasi node
- **Output Connection** - Mengirim data
- **Status Indicator** - Status eksekusi
---

## Cara Kerja Antar Node

![Data Flow Between Nodes](day-1/images/data-flow-nodes.png)
<!-- Placeholder: Diagram aliran data antar node -->

### Prinsip Dasar:
📨 **Node 1** → Kirim data → **Node 2** → Proses → **Node 3**

### Contoh Nyata:
1. **Google Sheets** (ambil data customer baru)
2. **Gmail** (terima data nama & email, kirim welcome email)
3. **Slack** (terima data dari Gmail, kirim notifikasi ke tim)

**Setiap node = Seperti orang di assembly line. Terima hasil kerja sebelumnya, lakukan tugasnya, teruskan ke yang berikutnya.**

---

## Menggunakan Data dari Node Sebelumnya

![Field Drag Drop](day-1/images/field-drag-drop.png)
<!-- Placeholder: Screenshot drag and drop field di N8N -->

### Cara Mudah Ambil Data:
1. **Lihat panel kiri** - Daftar field dari node sebelumnya
2. **Drag & drop** field yang dibutuhkan ke field yang mau diisi
3. **Auto-complete** - N8N otomatis isi dengan format yang benar

### Contoh Praktis:
- **Google Sheets** punya field: `nama`, `email`, `perusahaan`
- **Gmail node** butuh email → Drag `email` dari Sheets
- **Slack node** butuh nama → Drag `nama` dari Sheets

### Kalau Butuh Data dari Beberapa Node Sebelumnya:
💡 **Tips**: Gunakan node **Merge** untuk gabungkan data dari multiple sources!

---

<!-- SECTION 4: Triggers -->
# Memahami Berbagai Trigger pada N8N

---

## Google Sheets Trigger

![Google Sheets Trigger](day-1/images/trigger-googlesheets.png)
<!-- Placeholder: Screenshot Google Sheets trigger node -->

- **Otomatis jalan** saat ada baris baru di spreadsheet
- Monitor perubahan data secara real-time
- Langsung proses data yang baru masuk
- Cocok untuk input data tim

```
Use case: Tim sales input lead baru di Google Sheets, langsung kirim welcome email dan masuk ke CRM
```

---

## Telegram Trigger

![Telegram Trigger](day-1/images/trigger-telegram.png)
<!-- Placeholder: Screenshot Telegram trigger configuration -->

- **Otomatis jalan** saat ada pesan baru di grup/channel
- Monitor chat grup atau channel tertentu
- Bisa filter berdasarkan keyword atau mention
- Langsung respon pesan masuk

```
Use case: Customer service terima komplain di grup Telegram, langsung buat ticket dan notify manager
```

---

## Google Calendar Trigger

![Google Calendar Trigger](day-1/images/trigger-calendar.png)
<!-- Placeholder: Screenshot Google Calendar trigger configuration -->

- **Otomatis jalan** saat ada event baru atau dimulai
- Monitor calendar pribadi atau tim
- Bisa diatur berapa menit sebelum event
- Integrase dengan jadwal meeting

```
Use case: 15 menit sebelum meeting, kirim reminder ke semua peserta dan siapkan Zoom link
```

---

<!-- SECTION 5: Credentials -->
# Menghubungkan Aplikasi Favorit Anda

---

## Mengelola Kredensial dengan Aman

![Credential Management](day-1/images/credential-management.png)
<!-- Placeholder: Screenshot credential management interface -->

**Kredensial** = "Kunci akses" untuk menghubungkan N8N dengan aplikasi Anda

---

## Cara Menghubungkan Aplikasi

![Connect Apps](day-1/images/connect-apps.png)
<!-- Placeholder: Screenshot simple connection flow -->

### Langkah Mudah:
1. Pilih **aplikasi** yang mau dihubungkan
2. Klik **"Login & Connect"**
3. Masukkan **username/password** seperti biasa
4. **Izinkan akses** untuk N8N
5. **Selesai!** Aplikasi sudah terhubung

---

<!-- SECTION 6: Execution History -->
# Melihat Riwayat Eksekusi

---

## Execution History Overview

![Execution History](day-1/images/execution-history.png)
<!-- Placeholder: Screenshot halaman execution history -->

**Execution History** = Sejarah dari semua workflow yang pernah dijalankan

- **Status** eksekusi (Success/Failed/Running)
- **Timestamp** kapan dijalankan
- **Duration** berapa lama eksekusi
- **Data** yang diproses

---

## Status Eksekusi

![Execution Status](day-1/images/execution-status.png)
<!-- Placeholder: Icon status yang berbeda -->

### Status Types:
- ✅ **Success** - Workflow berhasil
- ❌ **Failed** - Ada error
- ⏳ **Running** - Sedang berjalan
- ⏸️ **Waiting** - Menunggu input
- ⏹️ **Canceled** - Dibatalkan manual

---

## Waktunya Praktik! 🚀

![Practice Time](day-1/images/practice-time.png)
<!-- Placeholder: Gambar orang menggunakan laptop dengan semangat -->

### Sekarang Giliran Anda!
Setelah memahami konsep dasar N8N, saatnya **hands-on experience**:

- 💼 **Build automation nyata** untuk bisnis Anda
- 🔗 **Connect aplikasi favorit** yang sudah Anda pakai
- ⚡ **Rasakan langsung** efisiensi automation
- 🎯 **Lihat hasil** dalam hitungan menit

**Tips**: Jangan takut eksperimen - N8N aman untuk dicoba!

Note:
Pastikan semua peserta siap dengan laptop dan akses internet. Berikan motivasi bahwa mereka akan membuat sesuatu yang berguna untuk pekerjaan mereka.

---

## Apa itu Pinned Data?

![Pinned Data Concept](day-1/images/pinned-data-concept.png)
<!-- Placeholder: Screenshot pinned data di N8N -->

**Pinned Data** = Data sample yang "disematkan" ke node untuk testing

### Mengapa Penting?
- 🧪 **Test workflow** tanpa trigger real
- 🔍 **Debug masalah** dengan data yang sama
- ⚡ **Kembangkan lebih cepat** tanpa tunggu data asli
- 📝 **Dokumentasi** - contoh data untuk tim lain

---

## Contoh Real: Pin Data dari API External

![API Node Pinning](day-1/images/api-node-pinning.png)
<!-- Placeholder: Screenshot HTTP Request node dengan pinned data -->

### Skenario Bisnis:
Workflow Anda pakai **HTTP Request** untuk cek stok produk dari supplier → **Rate limit 100 requests/hour** 🚫

### Masalah Tanpa Pinned Data:
❌ Test workflow = Habis rate limit cepat
❌ Debug error = Tunggu 1 jam untuk test lagi
❌ Demo ke klien = Error quota exceeded!

### Solusi dengan Pinned Data:
✅ **Call API sekali** → Pin responsnya
✅ **Test node lain** pakai data yang di-pin
✅ **Save API quota** + develop lebih cepat!

### Contoh Workflow:
1. **Google Sheets** (list produk) → 2. **HTTP Request** (cek stok supplier) → 3. **Pin hasil API** → 4. **Gmail/Slack** (test gratis!)

---

## Membuat Pinned Data dari Past Execution

![Past Execution to Pinned](day-1/images/past-execution-pinned.png)
<!-- Placeholder: Screenshot langkah-langkah membuat pinned data -->

### Langkah Mudah:
1. **Buka Execution History** - Pilih eksekusi yang berhasil
2. **Klik node** yang datanya mau di-pin
3. **Klik "Pin Data"** - Button di panel samping
4. **Konfirmasi** - Data otomatis tersimpan sebagai sample

### Kapan Gunakan?
✅ **Workflow sudah jalan sekali** - Ada data real yang bisa dipin
✅ **Mau modifikasi workflow** - Test perubahan dengan data sama
✅ **Demo ke tim** - Pakai data asli tanpa trigger ulang
✅ **Training** - Belajar dengan data real yang sudah proven

### Use Case: Debug Bug yang Terjadi
🐛 **Masalah**: Workflow error di production dengan data customer tertentu

**Langkah Debug**:
1. **Cari execution yang error** di history
2. **Pin data dari node yang bermasalah**
3. **Modify workflow** untuk fix bug
4. **Test dengan pinned data** - reproduksi exact same error
5. **Verify fix** tanpa tunggu data real lagi

**Pro Tip**: Pin data di beberapa node untuk test skenario berbeda!

---

<!-- SECTION 7: Hands-on Exercise -->
# Latihan: Buat Automation Pertama Anda

---

## Exercise: Automation Newsletter Signup

![Exercise Overview](day-1/images/business-exercise-overview.png)
<!-- Placeholder: Diagram workflow newsletter signup -->

### Target Automation:
**Customer Daftar Newsletter** → **Kirim Welcome Email** → **Simpan ke Database** → **Notifikasi Tim**

### Business Value:
Otomatisasi proses newsletter signup tanpa perlu copy-paste manual

---

## Step 1: Setup Customer Form

![Step 1](day-1/images/exercise-step1-form.png)
<!-- Placeholder: Screenshot form trigger setup -->

1. Buat workflow baru
2. Tambahkan **Form Trigger**
3. Setup form fields: Nama, Email, Perusahaan
4. Test dengan data sample

---

## Step 2: Kirim Welcome Email

![Step 2](day-1/images/exercise-step2-email.png)
<!-- Placeholder: Screenshot Gmail node configuration -->

1. Tambahkan **Gmail** node
2. Setup email template welcome
3. Gunakan data dari form (nama, email)
4. Test kirim email

---

## Step 3: Simpan ke Database

![Step 3](day-1/images/exercise-step3-sheets.png)
<!-- Placeholder: Screenshot Google Sheets node -->

1. Tambahkan **Google Sheets** node
2. Pilih spreadsheet "Newsletter Subscribers"
3. Map data: Nama → Kolom A, Email → Kolom B
4. Test simpan data

---

## Step 4: Notifikasi Tim

![Step 4](day-1/images/exercise-step4-slack.png)
<!-- Placeholder: Screenshot Slack notification -->

1. Tambahkan **Slack** node
2. Pilih channel #marketing
3. Buat pesan: "New subscriber: [Nama] from [Perusahaan]"
4. Test dan lihat notifikasi

---

## Selamat! Anda Sudah Jadi Automation Expert! 🎉

![Business Success](day-1/images/business-success.png)
<!-- Placeholder: Business success celebration -->

### Anda telah berhasil:
✅ Mengotomatisasi proses bisnis pertama
✅ Menghemat waktu tim dengan automation
✅ Menghubungkan beberapa aplikasi sekaligus
✅ Membuat sistem yang bekerja 24/7 untuk bisnis Anda

**Bayangkan berapa jam per minggu yang bisa dihemat dengan automation ini!**

---