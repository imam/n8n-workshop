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
- Menghubungkan aplikasi-aplikasi favorit Anda tanpa perlu coding
- Seperti main puzzle - drag & drop aja!
- Bisa dijalankan sendiri, data tetap aman di tangan Anda

Note:
Bayangkan tidak perlu lagi copy-paste data manual, atau mengecek email satu-satu. N8N bisa bantu otomatisasi semua itu!

---

## Mengapa N8N?

- 🔧 **Tanpa coding** - siapa saja bisa pakai!
- 🔗 **300+ aplikasi** siap dikoneksi (Gmail, Slack, Excel, dll)
- 🏠 **Data aman** - semuanya di kontrol Anda sendiri
- 💰 **Gratis** - hemat budget IT perusahaan
- 🎨 **Mudah dipahami** - seperti flowchart bisnis pada umumnya

![Use Cases](day-1/images/use-cases.png)
<!-- Placeholder: Diagram use cases N8N -->

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

## Sample Workflow Demo

![Sample Workflow](day-1/images/sample-workflow.png)
<!-- Placeholder: Screenshot workflow sederhana yang sudah jadi -->

### Contoh Real Application:
**Form Submission** → **Slack** → **Google Sheets** → **Email Notification**

*Kredensial sudah disetup oleh pengajar*

---

## Live Demo: Slack to Sheets

![Live Demo](day-1/images/live-demo.png)
<!-- Placeholder: Screenshot live demo execution -->

### Flow yang akan kita lihat:
1. **Form Submission** menerima data dari website
2. **Slack** mengirim notifikasi ke channel
3. **Google Sheets** menyimpan data
4. **Email** konfirmasi ke user

**Mari kita lihat workflow ini bekerja!**

---

## Yang Akan Kita Pelajari

![Learning Path](day-1/images/learning-path.png)
<!-- Placeholder: Visual learning path -->

### Setelah demo ini, kita akan explore:
- Cara membuat workflow dari nol
- Berbagai jenis trigger dan kapan menggunakannya
- Setup kredensial untuk integrasi
- Monitor dan debug workflow
- Best practices untuk production

---

<!-- SECTION 3: Workflow Concepts -->
# Memahami Konsep Workflow dan Node

---

## Apa itu Workflow?

![Workflow Concept](day-1/images/workflow-concept.png)
<!-- Placeholder: Diagram konsep workflow dengan panah -->

**Workflow** = Seperti SOP bisnis, tapi dijalankan otomatis oleh komputer

- **Input** → **Process** → **Output**
- Setiap langkah adalah **Node**
- Data mengalir dari satu node ke node lainnya

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

## Jenis-jenis Node

### 🚀 **Trigger Nodes**
Memulai workflow secara otomatis
![Trigger Examples](day-1/images/trigger-examples.png)
<!-- Placeholder: Icon-icon trigger node -->

### ⚙️ **Regular Nodes**
Melakukan aksi atau transformasi data
![Regular Node Examples](day-1/images/regular-examples.png)
<!-- Placeholder: Icon-icon regular node -->

---

## Data Flow

![Data Flow](day-1/images/data-flow.png)
<!-- Placeholder: Diagram aliran data antar node -->

- Data berupa informasi bisnis (nama customer, email, nomor invoice, dll)
- Setiap node dapat:
  - Menerima informasi dari langkah sebelumnya
  - Memproses/mengubah informasi (contoh: format tanggal, hitung total)
  - Meneruskan hasil ke langkah berikutnya

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

## Apa itu Trigger?

![Trigger Concept](day-1/images/trigger-concept.png)
<!-- Placeholder: Diagram trigger sebagai starting point -->

**Trigger** = Node yang memulai eksekusi workflow

- Workflow **HARUS** dimulai dengan trigger
- Trigger menentukan **kapan** workflow dijalankan
- Berbagai jenis trigger untuk berbagai kebutuhan

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

## Trigger Comparison

| Trigger Type | Execution | Use Case | Real-time |
|--------------|-----------|----------|-----------|
| Google Sheets | Data baru | Input tim ke spreadsheet | ✅ |
| Telegram | Pesan baru | Customer service & support | ✅ |
| Google Calendar | Event dimulai | Meeting reminder & prep | ⚠️ |

![Trigger Comparison](day-1/images/trigger-comparison.png)
<!-- Placeholder: Visual comparison chart -->

---

<!-- SECTION 5: Credentials -->
# Menambahkan Kredensial dan Keamanan

---

## Mengapa Kredensial Penting?

![Security Concept](day-1/images/security-concept.png)
<!-- Placeholder: Icon keamanan dan API keys -->

- **API Keys** untuk mengakses layanan external
- **OAuth tokens** untuk aplikasi modern
- **Database credentials** untuk koneksi database
- **Keamanan data** yang terjaga

---

## Menambahkan Kredensial

![Add Credentials](day-1/images/credentials-add.png)
<!-- Placeholder: Screenshot form tambah kredensial -->

### Langkah-langkah:
1. Buka **Credentials** menu
2. Klik **"Create New"**
3. Pilih **tipe kredensial**
4. Isi **informasi required**
5. **Test connection**
6. **Save** kredensial

---

## Jenis-jenis Kredensial

### 🔑 **API Key**
![API Key](day-1/images/cred-api-key.png)
<!-- Placeholder: Form API key credential -->

Simple key-based authentication

### 🔐 **OAuth2**
![OAuth2](day-1/images/cred-oauth2.png)
<!-- Placeholder: OAuth2 flow diagram -->

Secure token-based authentication

---

## Menggunakan Kredensial

![Using Credentials](day-1/images/credentials-usage.png)
<!-- Placeholder: Screenshot node configuration dengan credential -->

- Pilih kredensial dari **dropdown**
- Credentials di-**encrypt** secara otomatis
- Dapat digunakan di **multiple workflows**
- **Reusable** dan **secure**

---

## Best Practices Keamanan

### ✅ Secure Practices:
- Gunakan OAuth2 jika tersedia
- Rotate API keys secara berkala
- Berikan akses minimal yang diperlukan
- Monitor penggunaan credentials

### ❌ Avoid:
- Hardcode credentials di workflow
- Share credentials antar tim tanpa kontrol
- Gunakan admin account untuk automation

![Security Best Practices](day-1/images/security-best-practices.png)
<!-- Placeholder: Security checklist visual -->

---

<!-- SECTION 6: Execution History -->
# Melihat Riwayat Eksekusi

---

## Execution History Overview

![Execution History](day-1/images/execution-history.png)
<!-- Placeholder: Screenshot halaman execution history -->

**Execution History** = Log dari semua workflow yang pernah dijalankan

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

## Debugging Workflow

![Debug Workflow](day-1/images/debug-workflow.png)
<!-- Placeholder: Screenshot detail eksekusi dengan error -->

### Informasi Debug:
- **Error message** yang detail
- **Stack trace** untuk troubleshooting
- **Input/Output data** setiap node
- **Execution time** per node

---

## Viewing Execution Details

![Execution Details](day-1/images/execution-details.png)
<!-- Placeholder: Screenshot detail eksekusi lengkap -->

### Detail Information:
- **Workflow snapshot** saat eksekusi
- **Data flow** antar node
- **Node-by-node** results
- **JSON data** yang diproses

---

## Monitoring Tips

### 📊 **Monitoring Best Practices:**
- Cek execution history secara berkala
- Set up notification untuk failures
- Monitor performance metrics
- Archive old executions

![Monitoring Dashboard](day-1/images/monitoring-tips.png)
<!-- Placeholder: Screenshot monitoring dashboard -->

---

## Common Error Patterns

### 🔍 **Troubleshooting Guide:**

| Error Type | Common Cause | Solution |
|------------|--------------|----------|
| Authentication | Invalid credentials | Update/refresh tokens |
| Timeout | Long-running operations | Optimize or increase timeout |
| Rate Limit | Too many requests | Add delays between calls |
| Data Format | Unexpected JSON structure | Validate input data |

---

<!-- SECTION 7: Hands-on Exercise -->
# Latihan Praktik

---

## Exercise: Workflow Sederhana

![Exercise Overview](day-1/images/exercise-overview.png)
<!-- Placeholder: Diagram workflow yang akan dibuat -->

### Target Workflow:
**Manual Trigger** → **HTTP Request** → **Set Node** → **Webhook Response**

### Objective:
Membuat workflow yang fetch data dari API dan memformat response

---

## Step 1: Setup Trigger

![Step 1](day-1/images/exercise-step1.png)
<!-- Placeholder: Screenshot menambah manual trigger -->

1. Buat workflow baru
2. Tambahkan **Manual Trigger**
3. Konfigurasi trigger settings
4. Test trigger functionality

---

## Step 2: Add HTTP Request

![Step 2](day-1/images/exercise-step2.png)
<!-- Placeholder: Screenshot HTTP Request node configuration -->

1. Tambahkan **HTTP Request** node
2. Set URL: `https://jsonplaceholder.typicode.com/posts/1`
3. Method: **GET**
4. Connect dari Manual Trigger

---

## Step 3: Format Data

![Step 3](day-1/images/exercise-step3.png)
<!-- Placeholder: Screenshot Set node configuration -->

1. Tambahkan **Set** node
2. Format response data
3. Keep only: `title`, `body`, `userId`
4. Rename fields sesuai kebutuhan

---

## Step 4: Test Workflow

![Step 4](day-1/images/exercise-step4.png)
<!-- Placeholder: Screenshot hasil test workflow -->

1. **Execute** workflow
2. Check **execution results**
3. Verify **data flow**
4. Debug jika ada error

---

## Congratulations! 🎉

![Success](day-1/images/exercise-success.png)
<!-- Placeholder: Success celebration image -->

### Anda telah berhasil:
✅ Membuat workflow pertama
✅ Menggunakan multiple nodes
✅ Memahami data flow
✅ Testing dan debugging

---

<!-- FINAL SECTION -->
# Summary & Next Steps

---

## Apa yang Sudah Dipelajari

### 📚 **Day 1 Recap:**
- ✅ Introduction to N8N platform
- ✅ User interface navigation
- ✅ Workflow and node concepts
- ✅ Various trigger types
- ✅ Credentials management
- ✅ Execution history monitoring

![Day 1 Summary](day-1/images/day1-summary.png)
<!-- Placeholder: Visual summary of topics covered -->

---

## Next Steps

### 🚀 **Coming Up:**
- **Day 2**: Advanced node operations
- **Day 3**: Error handling & debugging
- **Day 4**: API integrations
- **Day 5**: Production deployment

### 📖 **Homework:**
- Explore different trigger types
- Create 2-3 simple workflows
- Practice using credentials

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