# N8N Tutorial - Day 2

## Menguasai Node dan Data Flow untuk Automation Bisnis

---

<!-- SECTION 1: Introduction -->
# Selamat Datang di Day 2!

---

## Recap Day 1

![Day 1 Recap](day-2/images/day1-recap.png)
<!-- Placeholder: Visual summary day 1 -->

### Yang Sudah Kita Kuasai:
✅ **Dasar N8N** - Tool automation tanpa coding
✅ **Trigger sederhana** - Google Sheets, Telegram, Calendar
✅ **Koneksi aplikasi** - Menghubungkan tools favorit
✅ **Automation pertama** - Newsletter signup otomatis

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
🏭 **Seperti pabrik** - Bahan mentah masuk, diproses, jadi produk jadi
📧 **Contoh**: Email masuk → Ekstrak info penting → Simpan ke database → Kirim notifikasi

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

## Melihat Data di N8N

![View Data N8N](day-2/images/view-data-n8n.png)
<!-- Placeholder: Screenshot data view dalam N8N -->

### Cara Mudah Lihat Data:
1. **Klik node** yang sudah dijalankan
2. **Tab "Data"** - Lihat input dan output
3. **Format JSON** - Struktur data yang rapi
4. **Preview** - Data dalam bentuk tabel

### Tips untuk Non-Technical:
- Fokus pada **nilai** bukan struktur
- Cari **field yang Anda butuhkan** (nama, email, dll)
- **Copy data** untuk testing node selanjutnya

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

<!-- SECTION 3: AI Sneak Peek -->
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

<!-- SECTION 4: Branching -->
# Branching: Satu Input, Banyak Aksi

---

## Apa itu Branching?

![Branching Concept](day-2/images/branching-concept.png)
<!-- Placeholder: Visual branching diagram -->

**Branching** = Membuat keputusan otomatis berdasarkan data

### Analogi Bisnis:
🚦 **Seperti traffic light** - Berdasarkan kondisi, ambil jalur yang berbeda
📋 **Seperti SOP** - "Jika customer VIP, lakukan A. Jika customer biasa, lakukan B"

### Contoh Nyata:
- **Lead score tinggi** → Langsung assign ke senior sales
- **Lead score rendah** → Masuk ke nurturing campaign
- **Komplain urgent** → Langsung ke manager
- **Komplain biasa** → Ke customer service

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

## Contoh Nyata: Customer Support Routing w/ AI

![Support Routing](day-2/images/support-routing-ai.png)
<!-- Placeholder: AI-powered support routing workflow -->

### Workflow: Tiket Support Otomatis dengan AI

1. **Customer kirim email** ke support@company.com
2. **AI Node** - Analisa subject & content secara smart
3. **Switch Node** berdasarkan AI result:
   - "billing" → Finance team
   - "technical" → Tech team
   - "urgent" → Escalate ke manager
4. **AI generate auto-reply** yang personal
5. **Create ticket** dengan AI insights
6. **Notify team** dengan summary AI

**Hasil**: Support ticket terorganisir pintar tanpa manual sorting!

---

## Praktik Langsung: Build Smart Workflow

![Smart Exercise](day-2/images/smart-branching-exercise.png)
<!-- Placeholder: AI-enhanced exercise workflow -->

### Latihan: Lead Qualification dengan AI

**Skenario**: Otomatisasi proses kualifikasi lead dari website

**Langkah demi langkah**:
1. **Form Trigger** - Lead dari contact form
2. **AI Node** - Analisa lead quality dari data yang diberikan
3. **Switch Node** berdasarkan AI score:
   - Score tinggi → Senior sales + prioritas
   - Score sedang → Junior sales
   - Score rendah → Email nurturing

**Nilai Bisnis**: AI yang tentukan kualitas lead, sales fokus ke yang terbaik!

---

<!-- SECTION 5: Popular Nodes -->
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

![Processing Nodes](day-2/images/processing-nodes.png)
<!-- Placeholder: Screenshots of processing nodes -->

### Set Node
**Tujuan**: Transform dan clean data
**Contoh Penggunaan**:
- Rename field untuk konsistensi
- Calculate nilai baru (total, persentase)
- Format tanggal dan nomor telepon
- Hapus field data yang tidak perlu

### Function Node
**Tujuan**: Custom data processing dengan JavaScript
**Contoh Bisnis**:
- Hitung komisi berdasarkan sales tier
- Generate nomor order unik
- Parse dan clean imported data
- Implementasi custom business logic

---

### Wait Node
**Tujuan**: Tambah delay antar aksi
**Contoh Penggunaan**:
- Tunggu 24 jam sebelum kirim follow-up email
- Delay antar API call untuk hindari rate limit
- Pause workflow untuk manual approval
- Schedule aksi hanya untuk jam kerja

### Merge Node
**Tujuan**: Gabungkan data dari multiple source
**Contoh Penggunaan**:
- Merge data customer dengan order history
- Combine social media metrics
- Join data dari departemen berbeda
- Buat comprehensive report

**Tips Penting**: Merge node sangat berguna untuk integrase data dari berbagai sistem menjadi satu workflow yang powerful!

---

## Praktik Langsung: Eksplorasi Node

![Node Exercise](day-2/images/node-exploration-exercise.png)
<!-- Placeholder: Node exploration workflow -->

### Latihan: Multi-Node Customer Onboarding dengan AI

**Skenario Bisnis**: Comprehensive new customer automation

**Langkah Workflow**:
1. **Google Sheets Trigger** - Customer baru di spreadsheet
2. **Set Node** - Format data customer (nama, email, phone)
3. **AI Node** - Validasi email dan profiling customer
4. **Gmail Node** - Kirim personalized welcome email
5. **Wait Node** - Tunggu 1 hari
6. **Slack Node** - Notifikasi sales tim tentang customer baru
7. **Airtable Node** - Tambah ke CRM dengan enriched data
8. **Merge Node** - Gabungkan dengan data historis lainnya

**Dampak Bisnis**: Onboarding seamless dengan AI insights, tidak ada customer yang terlewat!

---

<!-- SECTION 6: Hands-on Practice -->
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

<!-- SECTION 7: Summary -->
# Ringkasan & Langkah Selanjutnya

---

## Apa yang Sudah Dikuasai Hari Ini

![Day 2 Achievements](day-2/images/day2-achievements.png)
<!-- Placeholder: Visual summary of achievements -->

### 🎯 **Core Skill yang Diperoleh:**
✅ **Data Flow Mastery** - Memahami bagaimana data mengalir dan bertransformasi
✅ **Branching Logic** - Membuat keputusan otomatis berdasarkan kondisi bisnis
✅ **Node Expertise** - Menguasai node populer untuk automation sehari-hari
✅ **AI Sneak Peek** - Mengenal potensi AI untuk automation pintar
✅ **Complex Workflow** - Membangun automation end-to-end untuk proses bisnis nyata

### 💼 **Dampak Bisnis:**
- Automation lebih sophisticated dan fleksibel
- Proses bisnis yang kompleks bisa diotomatisasi
- AI memberikan sneak peek automation "pintar" dan adaptif
- ROI automation meningkat significantly

---

## Aplikasi Dunia Nyata

![Real World Apps](day-2/images/real-world-applications.png)
<!-- Placeholder: Various business applications -->

### Yang Bisa Anda Terapkan Sekarang:

🏢 **Sales & Marketing**:
- Lead qualification otomatis dengan AI scoring
- Personalized email campaign berdasarkan behavior
- Social media content generation dan scheduling
- Customer journey automation dengan branching logic

📊 **Operations**:
- Inventory management dengan predictive alert
- Order processing end-to-end automation
- Customer support dengan AI-powered routing
- Report generation dan distribution otomatis

💰 **Finance**:
- Invoice processing dengan data extraction
- Expense categorization menggunakan AI
- Payment reconciliation automation
- Financial reporting dengan insight generation

---

## Langkah Selanjutnya & Tugas Rumah

![Homework](day-2/images/homework-assignments.png)
<!-- Placeholder: Homework visual -->

### 📝 **Tugas Rumah:**

**Level 1 - Praktik Core Skill:**
- Buat 1 workflow dengan minimal 3 node berbeda
- Implementasi 1 branching logic untuk use case bisnis Anda
- Test data flow dengan tracing dari input ke output

**Level 2 - Terapkan ke Bisnis:**
- Identifikasi 1 proses bisnis yang bisa pakai branching
- Design workflow dengan merge node untuk gabungkan data
- Hitung potential time saving dari automation yang dibuat

**Level 3 - Explore AI:**
- Coba 1 simple AI integration (email classification)
- Bandingkan result AI vs manual rule
- Think of 3 use case AI untuk bisnis Anda

---

## Persiapan Day 3

![Day 3 Preview](day-2/images/day3-preview.png)
<!-- Placeholder: Day 3 preview topics -->

### 🚀 **Yang Akan Dipelajari di Day 3:**

**Error Handling & Debugging**:
- Mengatasi automation yang "stuck" atau error
- Best practice untuk reliability dan monitoring
- Notification system untuk automation failure

**Performance Optimization**:
- Membuat automation yang cepat dan efficient
- Rate limiting dan resource management
- Scaling automation untuk volume tinggi

**AI Deep Dive**:
- Implementasi lengkap AI dalam workflow
- Advanced prompt engineering untuk bisnis
- AI monitoring dan quality control

---

# Terima Kasih!

## Sesi Q&A

![QA Session](day-2/images/qa-session-day2.png)
<!-- Placeholder: Q&A session image -->

### Topik Diskusi:
- Challenge dengan complex data flow
- Pertanyaan tentang AI integration untuk bisnis
- Ide automation spesifik untuk industri Anda
- Technical troubleshooting dan best practice

### Kontak & Dukungan:
- **Email**: [instructor-email@domain.com]
- **Slack**: #n8n-tutorial-day2
- **Office Hour**: [Schedule untuk individual help]
- **Homework Submission**: [Platform/method]

**Ingat**: Mulai sederhana, kemudian tambah kompleksitas. AI adalah tool untuk enhance automation, bukan replace understanding!

---