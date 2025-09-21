# N8N Tutorial - Day 2

## Menguasai Node dan Data Flow untuk Automation Bisnis

---

<!-- SECTION 1: Introduction -->
# Selamat Datang di Day 2!

---

## Target Day 2

![Day 2 Goals](day-2/images/day2-goals.png)
<!-- Placeholder: Day 2 learning objectives -->

### Setelah sesi ini, Anda akan bisa:
🎯 **Memahami alur data** - Bagaimana informasi mengalir antar aplikasi
🔀 **Membuat percabangan** - Satu input, banyak aksi berbeda
🧰 **Menggunakan node populer** - Tools yang paling sering dipakai bisnis
🤖 **Sneak peek AI** - Automation yang "pintar" dengan LLM

### Dampak Bisnis:
💰 Automation yang lebih complex = lebih banyak waktu & uang yang dihemat!

---

<!-- SECTION 2: Data Flow -->
# Memahami Alur Data dalam Automation

---

## Apa itu Data Flow?

![Data Flow Concept](day-2/images/data-flow-concept.png)
<!-- Placeholder: Visual data flow diagram -->

**Data Flow** = Bagaimana informasi berpindah dari satu langkah ke langkah berikutnya

### Analogi Sederhana:
🚛 **Seperti sistem logistik** - Paket masuk → Cek alamat → Pilih jalur delivery → Kirim ke tujuan
📧 **Contoh**: Email masuk → AI analisa prioritas → Route berdasarkan urgensi → Aksi yang tepat

**Kunci Penting**: Data yang sama bisa menghasilkan jalur berbeda tergantung isinya!

---

## Contoh Nyata: Lead Processing

![Lead Processing Flow](day-2/images/lead-processing-flow.png)
<!-- Placeholder: Screenshot workflow lead processing -->

### Skenario Bisnis:
1. **Customer isi form** → Data: Nama, Email, Perusahaan, Kebutuhan
2. **Scoring otomatis** → Data: Score 1-10 berdasarkan kriteria
3. **Routing berdasarkan score** → Data: High/Medium/Low priority
4. **Assignment ke sales** → Data: Sales person yang tepat
5. **Follow-up reminder** → Data: Jadwal kontak ulang

**Setiap langkah menerima, memproses, dan meneruskan data!**

---

## Konsep Branching dalam Data Flow

![Branching in Data Flow](day-2/images/branching-in-dataflow.png)
<!-- Placeholder: Visual branching concept dalam konteks data flow -->

### Mengapa Branching Penting?
📊 **Data yang sama** bisa memerlukan **aksi yang berbeda**
🔀 **Contoh**: Email urgent vs email biasa membutuhkan response time berbeda

### Skenario Bisnis:
- **Customer VIP** → Fast track processing
- **Customer biasa** → Standard processing
- **High value order** → Manager approval
- **Small order** → Auto approval

**Branching = Smart decision making berdasarkan data content!**

---

## IF Node: Decision Maker

![IF Node](day-2/images/if-node.png)
<!-- Placeholder: Screenshot IF node configuration -->

### Cara Kerja IF Node:
1. **Input data** masuk
2. **Cek kondisi** - Apakah sesuai kriteria?
3. **True path** - Jika ya, lakukan ini
4. **False path** - Jika tidak, lakukan itu

### Contoh Kondisi Bisnis:
✅ **Email berisi kata "urgent"** → True
✅ **Order value > 1,000,000** → True
✅ **Customer dari Jakarta** → True
✅ **Jam kerja (9-17)** → True

---

## Switch Node: Multiple Paths

![Switch Node](day-2/images/switch-node.png)
<!-- Placeholder: Screenshot Switch node dengan multiple output -->

### Kapan Pakai Switch Node?

**IF Node** = 2 pilihan (Ya/Tidak)
**Switch Node** = 3+ pilihan (A/B/C/D)

### Contoh Kasus Bisnis:
📊 **Lead Scoring**:
- Score 80-100 → Hot Lead (assign senior sales)
- Score 60-79 → Warm Lead (assign junior sales)
- Score 40-59 → Cold Lead (email nurturing)
- Score <40 → Archive

🌍 **Geographic Routing**:
- Jakarta → Tim Jakarta
- Surabaya → Tim Surabaya
- Bali → Tim Bali
- Others → Tim Pusat

---

## Contoh Nyata: Customer Support Routing

![Support Routing](day-2/images/support-routing.png)
<!-- Placeholder: Rule-based support routing workflow -->

### Workflow: Tiket Support Otomatis

1. **Customer kirim email** ke support@company.com
2. **Text Parser** - Extract keywords dari subject & content
3. **Switch Node** berdasarkan keywords:
   - Contains "billing/invoice" → Finance team
   - Contains "technical/bug" → Tech team
   - Contains "urgent/asap" → Escalate ke manager
   - Default → General support
4. **Gmail Node** - Generate auto-reply template
5. **Airtable** - Create ticket dengan kategori
6. **Slack** - Notify team dengan ticket summary

**Hasil**: Support ticket terorganisir otomatis tanpa manual sorting!

---

## Praktik Langsung: Build Branching Workflow

![Branching Exercise](day-2/images/branching-exercise.png)
<!-- Placeholder: Rule-based branching exercise workflow -->

### Latihan: Lead Qualification dengan Rules

**Skenario**: Otomatisasi proses kualifikasi lead dari website

**Langkah demi langkah**:
1. **Form Trigger** - Lead dari contact form
2. **Function Node** - Calculate lead score berdasarkan:
   - Company size (1-3 points)
   - Budget range (1-3 points)
   - Timeline urgency (1-3 points)
3. **Switch Node** berdasarkan total score:
   - Score 7-9 → Senior sales + prioritas tinggi
   - Score 4-6 → Junior sales
   - Score 1-3 → Email nurturing campaign

**Nilai Bisnis**: Logic scoring yang konsisten, sales fokus ke lead terbaik!

---

## Data Transformation

![Data Transformation](day-2/images/data-transformation.png)
<!-- Placeholder: Before/after data transformation -->

### Mengapa Perlu Transform Data?

**Masalah Umum:**
- Aplikasi A pakai format "John Doe", aplikasi B butuh "Doe, John"
- Tanggal dari form: "01/15/2024", CRM butuh: "2024-01-15"
- Nomor telepon: "+62-21-1234567", WhatsApp butuh: "6221234567"

**Solusi N8N:**
🔧 Node khusus untuk mengubah format data
✂️ Ambil sebagian data yang dibutuhkan saja
➕ Gabungkan data dari beberapa sumber

---

## Praktik Langsung: Trace Data Flow

![Trace Data Exercise](day-2/images/trace-data-exercise.png)
<!-- Placeholder: Step-by-step data tracing -->

### Latihan Sederhana:
1. **Buat workflow baru**
2. **Google Sheets trigger** - Baris baru di spreadsheet "Customers"
3. **Lihat data** - Klik node, cek tab Data
4. **Transform data** - Gabungkan nama depan + belakang
5. **Gmail node** - Kirim email dengan data yang sudah diformat

**Target**: Memahami bagaimana data berubah di setiap langkah

---

<!-- SECTION 3: Popular Nodes -->
# Node Populer untuk Automation Bisnis

---

## Kategori Node untuk Bisnis

![Node Categories](day-2/images/node-categories-business.png)
<!-- Placeholder: Kategorisasi node untuk business use case -->

### 📧 **Node Komunikasi**
Gmail, Slack, Telegram, WhatsApp Business

### 📊 **Node Data & Storage**
Google Sheets, Airtable, MySQL, Notion

### 🔗 **Node Integrasi**
Zapier, Webhook, HTTP Request, API calls

### 🤖 **Node AI & Processing**
OpenAI, Claude, Text processing, Image analysis

### ⏰ **Node Scheduling & Logic**
Cron, IF, Switch, Wait, Merge

---

## Node Komunikasi

**Node komunikasi** adalah jantung automation bisnis modern. Node-node ini menghubungkan sistem internal Anda dengan platform komunikasi yang digunakan setiap hari oleh tim dan customer.

### Mengapa Penting untuk Bisnis?
✅ **Respon otomatis** - Tidak ada customer yang menunggu lama
✅ **Koordinasi tim** - Semua orang dapat info yang sama
✅ **Scaling communication** - Handle 100x lebih banyak interaksi
✅ **Consistency** - Pesan yang seragam dan professional

![Communication Nodes](day-2/images/communication-nodes.png)
<!-- Placeholder: Screenshots of communication nodes -->

### Gmail Node
**Contoh Penggunaan**:
- Kirim welcome email ke customer baru
- Auto-reply untuk pertanyaan umum
- Forward email urgent ke management
- Campaign email massal

**Nilai Bisnis**: Email automation 24/7, response time lebih cepat

### Slack Node
**Contoh Penggunaan**:
- Notifikasi tim tentang order/lead baru
- Alert untuk masalah sistem atau deadline
- Share laporan harian otomatis
- Buat channel untuk project baru

**Nilai Bisnis**: Koordinasi tim real-time, tidak ada yang terlewat

---

### Telegram Node
**Contoh Penggunaan**:
- Bot customer service untuk pertanyaan dasar
- Update status order ke customer
- Alert internal untuk masalah urgent
- Broadcast pengumuman ke subscriber

**Nilai Bisnis**: Komunikasi instan, mengurangi manual customer service

### WhatsApp Business Node
**Contoh Penggunaan**:
- Kirim konfirmasi order
- Reminder appointment
- Survey feedback customer
- Update produk & promosi

**Nilai Bisnis**: High open rate, engagement customer langsung

---

## Node Data & Storage

**Node data & storage** adalah fondasi dari automation yang powerful. Node-node ini mengelola, menyimpan, dan mengorganisir informasi bisnis Anda secara otomatis.

### Peran Krusial dalam Bisnis:
📊 **Central data hub** - Satu tempat untuk semua informasi bisnis
🔄 **Real-time sync** - Data selalu update di semua sistem
📈 **Business intelligence** - Data tersruktur untuk decision making
🔒 **Data security** - Backup otomatis dan access control

**Pilihan Platform**: Dari yang sederhana (Sheets) hingga enterprise (Database)

![Data Storage Nodes](day-2/images/data-storage-nodes.png)
<!-- Placeholder: Screenshots of data nodes -->

### Google Sheets Node
**Contoh Penggunaan**:
- Manajemen database customer
- Tracking sales pipeline
- Monitor inventory
- Generate laporan

**Tips Konfigurasi**:
- Gunakan header kolom yang jelas
- Setup data validation
- Buat sheet terpisah untuk keperluan berbeda
- Backup rutin untuk hindari kehilangan data

---

### Airtable Node
**Contoh Penggunaan**:
- CRM dengan custom field
- Project management dengan attachment
- Event planning dengan linked record
- Katalog produk dengan gambar

**Mengapa Pilih Airtable**:
- Lebih powerful dari Sheets
- Database relationship
- Multiple view (calendar, kanban, gallery)
- Lebih baik untuk struktur data kompleks

### Notion Node
**Contoh Penggunaan**:
- Automation knowledge base
- Integrasi task management
- Update dokumentasi
- Maintenance team wiki

---

## Node Processing & Logic

**Node processing & logic** adalah "otak" dari automation Anda. Node-node ini memproses, menganalisa, dan membuat keputusan berdasarkan data bisnis yang mengalir.

### Fungsi Vital untuk Automation:
🧠 **Smart decision making** - Automation yang bisa "berpikir"
⚡ **Data transformation** - Ubah format data sesuai kebutuhan
⏱️ **Timing control** - Atur kapan aksi harus dilakukan
🔗 **Data integration** - Gabungkan info dari berbagai sumber

**Kunci Sukses**: Node ini yang membuat automation Anda flexibel dan intelligent!

![Processing Nodes](day-2/images/processing-nodes.png)
<!-- Placeholder: Screenshots of processing nodes -->

### Set Node
**Tujuan**: Transform dan clean data

**Real Use Case 1 - E-commerce Order Processing**:
- Input: Order dari toko online dengan format "Rp 150,000"
- Transform: Ubah ke angka 150000 untuk calculation
- Output: Data siap untuk inventory dan accounting system

**Real Use Case 2 - Customer Data Cleanup**:
- Input: Form dengan "Ph: +62-21-1234567" dan "Email: JOHN@GMAIL.COM"
- Transform: Format jadi "6221234567" dan "john@gmail.com"
- Output: Data konsisten untuk CRM dan WhatsApp automation

**Kasus Nyata 3 - Metrik Media Sosial**:
- Input: Data engagement dari berbagai platform
- Transform: Hitung ROI, tingkat pertumbuhan, dan rata-rata engagement
- Output: Metrik siap dashboard untuk laporan bulanan

### Function Node
**Tujuan**: Pemrosesan data kustom dengan JavaScript

**Kasus Nyata 1 - Kalkulator Komisi Sales**:
- Input: Jumlah penjualan = 10,000,000, Tier sales = "Senior"
- Proses: JIKA tier Senior MAKA komisi 8% KALAU TIDAK 5%
- Output: Komisi = 800,000 + perhitungan bonus

**Kasus Nyata 2 - Generator Nomor Invoice Pintar**:
- Input: Tanggal + tipe customer + urutan
- Proses: "INV-" + "2024" + "B2B" + nomor otomatis naik
- Output: "INV-2024B2B-00127" untuk pelacakan dan akuntansi

**Kasus Nyata 3 - Penilaian Risiko Customer**:
- Input: Riwayat pembayaran, frekuensi order, jumlah komplain
- Proses: Algoritma berbobot untuk penilaian risiko
- Output: Skor risiko 1-10 untuk limit kredit dan syarat pembayaran

---

### Wait Node
**Tujuan**: Tambah jeda antar aksi

**Kasus Nyata 1 - Campaign Nurturing Customer**:
- Pemicu: Lead baru mendaftar
- Tunggu: 24 jam setelah email selamat datang
- Aksi: Kirim konten edukasi + penawaran khusus
- Dampak Bisnis: Tingkat konversi lebih tinggi dengan timing yang tepat

**Kasus Nyata 2 - Automation Follow-up Pembayaran**:
- Pemicu: Invoice dikirim
- Tunggu: 7 hari jika belum ada pembayaran
- Aksi: Kirim pengingat sopan dengan link pembayaran
- Dampak Bisnis: Pengumpulan lebih cepat tanpa pelacakan manual

**Kasus Nyata 3 - Urutan Permintaan Review**:
- Pemicu: Pesanan diterima (dari sistem pelacakan)
- Tunggu: 3 hari untuk pengalaman customer
- Aksi: Kirim permintaan review dengan insentif
- Dampak Bisnis: Review lebih autentik dengan timing yang tepat

### Merge Node
**Tujuan**: Gabungkan data dari berbagai sumber

**Kasus Nyata 1 - Profil Customer 360°**:
- Input A: Data customer dari CRM (info kontak, preferensi)
- Input B: Riwayat pembelian dari platform e-commerce
- Input C: Tiket support dari sistem help desk
- Output: Profil customer lengkap untuk layanan personal

**Kasus Nyata 2 - Performa Campaign Marketing**:
- Input A: Metrik email (buka, tingkat klik)
- Input B: Engagement media sosial
- Input C: Data konversi website
- Output: Dashboard marketing terpadu dengan perhitungan ROI

**Kasus Nyata 3 - Automation Laporan Keuangan**:
- Input A: Data penjualan dari berbagai toko
- Input B: Data pengeluaran dari sistem akuntansi
- Input C: Biaya inventory dari manajemen gudang
- Output: Laporan P&L bulanan otomatis dengan analisis trend

**Tips Penting**: Merge node sangat berguna untuk integrasi data dari berbagai sistem menjadi satu workflow yang powerful!

---

## Praktik Langsung: Eksplorasi Node

![Node Exercise](day-2/images/node-exploration-exercise.png)
<!-- Placeholder: Node exploration workflow -->

### Latihan: Multi-Node Customer Onboarding

**Skenario Bisnis**: Comprehensive new customer automation

**Langkah Workflow**:
1. **Google Sheets Trigger** - Customer baru di spreadsheet
2. **Set Node** - Format data customer (nama, email, phone)
3. **IF Node** - Cek apakah field "Company" ada isinya
   - **True**: Customer dari perusahaan → Route ke B2B sales
   - **False**: Customer individual → Route ke B2C sales
4. **Gmail Node** - Kirim welcome email sesuai tipe customer
5. **Wait Node** - Tunggu 1 hari
6. **Slack Node** - Notifikasi sales tim dengan kategori yang tepat
7. **Airtable Node** - Tambah ke CRM dengan tag B2B/B2C
8. **Merge Node** - Gabungkan dengan data historis lainnya

**Nilai Bisnis**: Onboarding otomatis dengan smart routing, setiap customer dapat treatment yang tepat!

### Mengapa IF Condition Ini Lebih Baik?
✅ **Sederhana** - Cek field kosong atau ada isi
✅ **Business-relevant** - B2B vs B2C adalah kategorisasi yang penting untuk bisnis
✅ **Actionable** - Hasil langsung menentukan sales flow yang berbeda
✅ **No regex needed** - Beginner-friendly logic

---

<!-- SECTION 4: AI Sneak Peek -->
# Sneak Peek: AI untuk Automation Pintar

---

## Automation + AI = Magic ✨

![AI Magic](day-2/images/ai-magic.png)
<!-- Placeholder: AI magic concept -->

### Sebelumnya:
❌ **Manual** - Cek email satu-satu
❌ **Rule-based** - "Jika kata 'urgent' maka..."

### Dengan AI:
✅ **Otomatis baca email** - AI pahami maksud customer
✅ **Smart categorization** - AI tentukan kategori dan prioritas
✅ **Natural response** - AI tulis reply yang tepat

---

## Contoh: AI Email Validation

![AI Email Validation](day-2/images/ai-email-validation.png)
<!-- Placeholder: AI email validation example -->

### Daripada IF Node Rumit:
```
IF email contains "@gmail.com" OR "@yahoo.com"
THEN personal email
ELSE business email
```

### Pakai AI Node:
```
Prompt: "Analisa email ini apakah business atau personal email: {email_address}"
Response: "Business email dari perusahaan teknologi"
```

**Lebih akurat, lebih fleksibel!**

---

## AI dalam Customer Support

![AI Support](day-2/images/ai-support-example.png)
<!-- Placeholder: AI customer support workflow -->

### Workflow w/ LLM yang Seru:
1. **Customer kirim email** ke support@company.com
2. **AI Node** - Analisa email:
   - Kategori (billing/teknis/umum)
   - Urgensi (tinggi/sedang/rendah)
   - Sentimen (senang/kesal/netral)
3. **Smart routing** berdasarkan AI analysis
4. **AI generate reply** - Draft response otomatis

**Result**: Support 10x lebih pintar dan cepat!

---

<!-- SECTION 5: Hands-on Practice -->
# Latihan Comprehensive: E-commerce Order Processing

---

## Overview Latihan

![Ecommerce Exercise](day-2/images/ecommerce-exercise-overview.png)
<!-- Placeholder: Complete ecommerce workflow diagram -->

### Skenario Bisnis:
**Otomatisasi Komprehensif Order Processing untuk Online Store**

### Proses Manual Saat Ini:
1. Order masuk via email
2. Manual data entry ke spreadsheet
3. Manual check stock
4. Manual assign ke fulfillment team
5. Manual customer notification
6. Manual tracking update

**Kendala**: Lambat, error-prone, tidak scalable

---

## Target Smart Automation Workflow

![Target Workflow](day-2/images/target-smart-workflow.png)
<!-- Placeholder: AI-enhanced workflow diagram -->

### Proses Otomatis dengan AI:
1. **Email Trigger** - Order confirmation email
2. **AI Extraction** - Parse order detail dengan OpenAI
3. **Data Validation** - AI check kelengkapan & format
4. **Stock Check** - Query inventory database
5. **AI Smart Routing** - Assign berdasarkan AI analysis
6. **AI Customer Communication** - Personalized updates
7. **Team Notification** - Tim relevan dapat notifikasi dengan AI summary
8. **Tracking Setup** - Buat tracking record

**Dampak Bisnis**: 95% lebih cepat processing, AI-powered, zero manual error!

---