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
1. **Klik field** yang mau diisi (contoh: email di Gmail node)
2. **Lihat panel kanan** - Daftar field dari node sebelumnya
3. **Drag & drop** field yang dibutuhkan
4. **Auto-complete** - N8N otomatis isi dengan format yang benar

### Contoh Praktis:
- **Google Sheets** punya field: `nama`, `email`, `perusahaan`
- **Gmail node** butuh email → Drag `email` dari Sheets
- **Slack node** butuh nama → Drag `nama` dari Sheets

### Kalau Butuh Data dari Beberapa Node Sebelumnya:
💡 **Tips**: Gunakan node **Merge** untuk gabungkan data dari multiple sources!

---

## Jenis-jenis Node

### 🚀 **Trigger Nodes**
Node paling awal yang mentrigger seluruh workflow
![Trigger Examples](day-1/images/trigger-examples.png)
<!-- Placeholder: Icon-icon trigger node -->

### ⚙️ **Regular Nodes**
Node yang memproses data
![Regular Node Examples](day-1/images/regular-examples.png)
<!-- Placeholder: Icon-icon regular node -->

---

## Best Practices

### ✅ Do's:
- Beri nama workflow yang jelas (contoh: "Customer Onboarding Process")
- Tambahkan catatan untuk tim lain yang akan menggunakan
- Test dengan data sampel sebelum go-live
- Kelompokkan workflow berdasarkan departemen

### ❌ Don'ts:
- Jangan buat workflow terlalu rumit - bagi jadi beberapa workflow kecil
- Hindari workflow yang berjalan terus-menerus tanpa henti
- Jangan masukkan password atau API key langsung di workflow

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

### Jenis Kredensial:
🔑 **OAuth** - Login sekali, akses selamanya (Google, Slack)
🔐 **API Key** - Kode rahasia dari aplikasi (seperti password)
📧 **Email/Password** - Login biasa seperti di browser

### Best Practices Keamanan:
✅ **Jangan share kredensial** dengan tim lain
✅ **Gunakan akun khusus** untuk automation (bukan personal)
✅ **Review akses berkala** - Cabut yang tidak perlu
✅ **Backup credential penting** ke tempat aman

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

## Contoh Real: Pin Data dari AI Node

![AI Node Pinning](day-1/images/ai-node-pinning.png)
<!-- Placeholder: Screenshot AI node dengan pinned data -->

### Skenario Bisnis:
Workflow Anda pakai **OpenAI node** untuk analisa customer feedback → **$0.01 per request** 💸

### Masalah Tanpa Pinned Data:
❌ Test workflow = Bayar AI berkali-kali
❌ Debug error = Buang-buang budget AI
❌ Demo ke boss = Mahal!

### Solusi dengan Pinned Data:
✅ **Run AI sekali** → Pin hasilnya
✅ **Test node lain** pakai data yang di-pin
✅ **Save money** + develop lebih cepat!

### Contoh Workflow:
1. **Form** (customer feedback) → 2. **OpenAI** (analisa sentiment) → 3. **Pin hasil AI** → 4. **Gmail/Slack** (test gratis!)

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

<!-- FINAL SECTION -->
# Summary & Next Steps

---

## Apa yang Sudah Dipelajari

### 📚 **Apa yang Sudah Dikuasai:**
- ✅ Memahami kekuatan automation untuk bisnis
- ✅ Mengenal cara kerja N8N untuk efisiensi
- ✅ Membuat automation pertama yang real
- ✅ Menghubungkan aplikasi favorit bisnis
- ✅ Monitoring automation berjalan dengan baik

![Day 1 Summary](day-1/images/day1-summary.png)
<!-- Placeholder: Visual summary of topics covered -->

---

## Next Steps

### 🚀 **Selanjutnya:**
- **Day 2**: Automation yang lebih kompleks untuk proses bisnis
- **Day 3**: Mengatasi masalah dan optimasi automation
- **Day 4**: Integrasi dengan lebih banyak aplikasi bisnis
- **Day 5**: Deploy automation untuk operasional harian

### 📝 **Tugas Rumah:**
- Pikirkan 3 proses manual di bisnis Anda yang bisa diotomatisasi
- Coba buat 1-2 automation sederhana untuk kebutuhan pribadi
- Diskusikan dengan tim tentang potensi automation

---

## Resources

### 📚 **Documentation:**
- [N8N Official Docs](https://docs.n8n.io)
- [Community Forum](https://community.n8n.io)
- [GitHub Repository](https://github.com/n8n-io/n8n)

### 🎯 **Practice Platforms:**
- [N8N Cloud](https://n8n.cloud) - Free tier
- [Self-hosted setup](https://docs.n8n.io/getting-started/installation/)

![Resources](day-1/images/resources.png)
<!-- Placeholder: Resource links and QR codes -->

---

# Terima Kasih!

## Q&A Session

![Q&A](day-1/images/qa-session.png)
<!-- Placeholder: Q&A session image -->

### Contact Information:
- **Email**: [your-email@domain.com]
- **Slack**: #n8n-tutorial
- **Office Hours**: [Schedule info]

---