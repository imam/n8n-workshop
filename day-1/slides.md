# N8N Tutorial - Day 1

## Pengenalan N8N untuk Automation

---

<!-- SECTION 1: Introduction -->
# Introduction N8N

---

## Apa itu N8N?

![N8N Logo](day-1/images/n8n-logo.png)
<!-- Placeholder: Logo N8N -->

- **N8N** adalah platform automation workflow yang open-source<br>
- Memungkinkan integrasi antar aplikasi tanpa coding<br>
- Visual workflow builder<br>
- Self-hosted solution

Note:
N8N memungkinkan kita untuk mengotomatisasi tugas-tugas repetitif dengan cara yang visual dan mudah dipahami.

---

## Mengapa N8N?

- 🔧 **No-code/Low-code** approach<br>
- 🔗 **300+ integrations** tersedia<br>
- 🏠 **Self-hosted** - kontrol penuh atas data<br>
- 💰 **Open source** - gratis untuk digunakan<br>
- 🎨 **Visual interface** - mudah dipahami

![Use Cases](day-1/images/use-cases.png)
<!-- Placeholder: Diagram use cases N8N -->

---

## Target Hari Ini

Setelah sesi ini, peserta dapat:

- ✅ Memahami interface N8N<br>

- ✅ Membuat workflow sederhana<br>

- ✅ Menggunakan berbagai trigger

- ✅ Mengelola kredensial

- ✅ Memonitor eksekusi workflow

---

<!-- SECTION 2: User Interface -->
# Berkenalan dengan User Interface

---

## Dashboard Overview

![N8N Dashboard](day-1/images/ui-dashboard.png)
<!-- Placeholder: Screenshot dashboard utama N8N -->

- **Workflows** - Daftar semua workflow
- **Executions** - Riwayat eksekusi
- **Credentials** - Manajemen kredensial
- **Settings** - Konfigurasi sistem

---

## Canvas Workspace

![Canvas Workspace](day-1/images/ui-canvas.png)
<!-- Placeholder: Screenshot canvas editor dengan workflow sample -->

### Area Utama:
- **Canvas** - Area untuk membangun workflow<br>
- **Node Panel** - Panel node di sebelah kiri<br>
- **Properties Panel** - Konfigurasi node di sebelah kanan<br>
- **Toolbar** - Tools untuk mengelola workflow

---

## Node Panel

![Node Panel](day-1/images/ui-node-panel.png)
<!-- Placeholder: Screenshot node panel dengan kategori -->

### Kategori Node:
- **Triggers** - Memulai workflow<br>
- **Regular Nodes** - Aksi dan transformasi<br>
- **Core Nodes** - Fungsi dasar<br>
- **App Nodes** - Integrasi aplikasi

---

## Navigation Tips

- **Zoom**: Mouse wheel atau tombol zoom
- **Pan**: Drag canvas dengan mouse
- **Select**: Click node untuk memilih
- **Connect**: Drag dari output ke input node
- **Delete**: Select node lalu tekan Delete

![Navigation Demo](day-1/images/ui-navigation.png)
<!-- Placeholder: Screenshot menunjukkan cara navigasi -->

---

<!-- SECTION 3: Workflow Concepts -->
# Memahami Konsep Workflow dan Node

---

## Apa itu Workflow?

![Workflow Concept](day-1/images/workflow-concept.png)
<!-- Placeholder: Diagram konsep workflow dengan panah -->

**Workflow** = Serangkaian langkah otomatis yang saling terhubung

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

- Data berupa **JSON objects**
- Setiap node dapat:
  - Menerima data dari node sebelumnya
  - Memproses/mentransformasi data
  - Meneruskan hasil ke node berikutnya

---

## Best Practices

### ✅ Do's:
- Beri nama workflow yang deskriptif
- Gunakan komentar untuk dokumentasi
- Test workflow secara bertahap
- Kelompokkan node yang serupa

### ❌ Don'ts:
- Jangan buat workflow terlalu kompleks
- Hindari loop tak terbatas
- Jangan hardcode sensitive data

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

## Manual Trigger

![Manual Trigger](day-1/images/trigger-manual.png)
<!-- Placeholder: Screenshot manual trigger node -->

- **Triggered manually** oleh user
- Bagus untuk testing dan development
- Eksekusi on-demand
- Default trigger untuk workflow baru

```
Use case: Testing workflow baru
```

---

## Webhook Trigger

![Webhook Trigger](day-1/images/trigger-webhook.png)
<!-- Placeholder: Screenshot webhook trigger configuration -->

- Menerima **HTTP requests** dari aplikasi lain
- Real-time execution
- Mendukung GET, POST, PUT, DELETE
- Dapat menerima data dari request

```
Use case: Integrasi dengan aplikasi external
```

---

## Schedule Trigger (Cron)

![Schedule Trigger](day-1/images/trigger-schedule.png)
<!-- Placeholder: Screenshot cron trigger dengan schedule -->

- Eksekusi berdasarkan **jadwal waktu**
- Menggunakan cron expression
- Interval atau waktu spesifik
- Otomatis dan recurring

```
Examples:
- Setiap hari jam 9 pagi
- Setiap Senin jam 8 pagi
- Setiap 30 menit
```

---

## Polling Trigger

![Polling Trigger](day-1/images/trigger-polling.png)
<!-- Placeholder: Screenshot polling trigger dari aplikasi -->

- **Cek perubahan** secara berkala
- Monitoring API endpoints
- Deteksi data baru
- Configurable interval

```
Use case: Monitor new emails, files, database records
```

---

## Trigger Comparison

| Trigger Type | Execution | Use Case | Real-time |
|--------------|-----------|----------|-----------|
| Manual | On-demand | Testing | ❌ |
| Webhook | HTTP request | API integration | ✅ |
| Schedule | Time-based | Recurring tasks | ❌ |
| Polling | Interval check | Monitor changes | ⚠️ |

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