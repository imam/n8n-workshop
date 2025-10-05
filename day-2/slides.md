# Pelatihan N8N: Day 2
## Transformasi Data & Alur Kerja Lanjutan

---

<!-- SECTION 1: Pembukaan & Konsep Lanjutan -->

## Agenda Pelatihan Day 2

- **Rekapitulasi:** Konsep Day 1 yang sudah dikuasai
- **Pengenalan Konsep Lanjutan:** Data Transformation & Flow Control
- **Tugas 4:** Manipulasi tanggal untuk penjadwalan cerdas
- **Tugas 5:** Alur kerja bercabang dengan node Switch
- **Tugas 6:** Pengenalan AI - Klasifikasi teks cerdas
- **Penutup:** Rekapitulasi & sneak peek Day 3

---

## Rekapitulasi Day 1

### Apa yang Sudah Kita Kuasai?

Kemarin kita telah mempelajari fondasi N8N:

- ✅ **Workflow dasar:** Trigger → Action
- ✅ **Data dinamis:** Menggunakan data dari trigger di action
- ✅ **Multi-step workflow:** Merangkai beberapa aksi berurutan
- ✅ **Active/Inactive:** Mengelola mode workflow

**Sekarang kita siap naik level!** 🚀

---

## Pertanyaan untuk Day 2

### Bagaimana Jika...

**Scenario 1:**
- Kita perlu data **yang berhubungan dengan waktu** relatif dari sekarang?
- *Contoh: "2 jam dari sekarang", "minggu depan", "kemarin"*

**Scenario 2:**
- Workflow harus **memilih jalur berbeda** tergantung kondisi?
- *Contoh: Customer VIP vs reguler dapat treatment berbeda*

**Scenario 3:**
- Kita ingin workflow **membuat keputusan cerdas** secara otomatis?
- *Contoh: Klasifikasi email tanpa aturan manual*

**Hari ini, kita akan menjawab semua pertanyaan ini!**

---

## Dua Tipe Node Lanjutan

### Kategori Node Baru Hari Ini

**1. Data Transformation**
- **Fungsi:** Mengubah, memformat, atau mengolah data
- **Analogi:** Seperti "alat pertukangan" di dalam workflow
- **Contoh Node:** Date & Time, Set, Code, Split, Merge
- **Use Case:** Format tanggal, gabung teks, hitung nilai, clean data

**2. Flow Control**
- **Fungsi:** Mengatur alur atau logika workflow
- **Analogi:** Seperti "rambu lalu lintas" atau "persimpangan jalan"
- **Contoh Node:** Switch, IF, Merge, Wait
- **Use Case:** Branching logic, conditional action, timing control

---

<!-- SECTION 2: Tugas 4 - Data Transformation -->

# Tugas 4: Manipulasi Tanggal untuk Penjadwalan Cerdas

---

## Tugas 4: Manipulasi Data Tanggal

### Tujuan:
Menggunakan node **Date & Time** untuk menjadwalkan event **2 jam setelah pendaftaran** secara otomatis.

### Apa yang Akan Dibuat:
- Trigger: Google Sheets (pendaftar baru)
- Transformation: Hitung waktu "2 jam dari sekarang"
- Action: Buat Google Calendar event dengan waktu yang dihitung

**Skill Baru:** Data Transformation dengan manipulasi tanggal

---

## Konsep: Node Date & Time

### Alat Transformasi Data Tanggal

Node **Date & Time** adalah salah satu "alat" Data Transformation di N8N:

**Fungsi Utama:**
- 📅 Mendapatkan waktu saat ini
- ➕ Menambah atau mengurangi waktu (jam, hari, minggu)
- 🔄 Memformat tanggal ke berbagai format
- 🌍 Konversi timezone

**⚠️ PENTING:** Node ini **bukan untuk menunda eksekusi workflow**, melainkan untuk **memanipulasi nilai data tanggal** yang akan dikirim ke step berikutnya.

---

## Use Case Bisnis: Penjadwalan Otomatis

### Mengapa Manipulasi Tanggal Penting?

**Contoh Real-World:**
1. **Reminder otomatis:** "Kirim reminder 1 hari sebelum meeting"
2. **Follow-up scheduling:** "Schedule follow-up call 3 hari setelah demo"
3. **Deadline calculation:** "Set deadline 2 minggu dari hari ini"
4. **Event planning:** "Buat event 2 jam setelah registrasi"

**Business Value:** Tidak perlu hitung manual, sistem yang konsisten, scalable!

---

## Yuk Kita Coba! (Tugas 4)

### Mari Mengolah Data!

Kita akan buat workflow yang secara otomatis menjadwalkan meeting 2 jam setelah ada pendaftar baru.

**Yang akan kita lakukan:**
- Setup Google Sheets trigger
- Gunakan Date & Time node untuk calculate waktu
- Buat Google Calendar event dengan waktu yang calculated

---

## WAKTUNYA PRAKTIK! (Tugas 4)

### Sekarang Giliran Anda

- Buka dokumen panduan **Tugas 4**
- Ikuti langkah-langkah untuk membuat workflow dengan Date & Time manipulation
- Test dengan menambah pendaftar baru

**Target:** Workflow yang otomatis schedule calendar event 2 jam dari sekarang

---

<!-- SECTION 3: Tugas 5 - Flow Control -->

# Tugas 5: Alur Kerja Bercabang

---

## Tugas 5: Alur Kerja Bercabang dengan Switch

### Tujuan:
Memberikan **perlakuan berbeda** untuk pendaftar "Perusahaan" dan "Individu" menggunakan node Switch.

### Apa yang Akan Dibuat:
- Trigger: Google Sheets (pendaftar dengan field "Tipe")
- Flow Control: Switch node untuk branch logic
- Action Path 1: Email untuk customer perusahaan
- Action Path 2: Email untuk customer individu

**Skill Baru:** Flow Control dengan branching logic

---

## Konsep: Node Switch

### "Rambu Lalu Lintas" Workflow

Node **Switch** adalah flow control utama di N8N:

**Cara Kerja:**
1. Input data masuk ke Switch node
2. Switch **memeriksa nilai data** tertentu
3. Workflow **diarahkan ke jalur berbeda** berdasarkan aturan
4. Setiap jalur bisa punya action berbeda

**Visualisasi:**
```
Input Data → [Switch Node] → Jalur A (Perusahaan)
                          └→ Jalur B (Individu)
```

---

## Use Case Bisnis: Smart Routing

### Mengapa Branching Penting?

**Scenario Business:**

**Customer Segmentation:**
- VIP Customer → Fast track, senior sales, special discount
- Regular Customer → Standard process, junior sales

**Geographic Routing:**
- Jakarta → Tim Jakarta
- Surabaya → Tim Surabaya
- Bali → Tim Bali

**Priority Handling:**
- Urgent order → Same-day processing
- Normal order → 3-day processing

**Business Value:** Personalisasi otomatis, efisiensi resource allocation!

---

## Switch vs IF: Kapan Pakai Yang Mana?

### Perbedaan Kunci

**IF Node:**
- ✅ **2 jalur:** True atau False
- ✅ **Sederhana:** Ya/Tidak decision
- ✅ **Contoh:** "Apakah customer VIP?" → Ya/Tidak

**Switch Node:**
- ✅ **3+ jalur:** A, B, C, D, dst.
- ✅ **Multiple conditions:** Banyak kemungkinan
- ✅ **Contoh:** "Customer dari kota mana?" → Jakarta/Surabaya/Bali/Lainnya

**Tips:** Gunakan IF untuk simple yes/no, Switch untuk multi-way branching!

---

## Yuk Kita Coba! (Tugas 5)

### Waktunya Membuat Keputusan!

Kita akan buat workflow yang memberikan treatment berbeda untuk customer perusahaan vs individu.

**Yang akan kita lakukan:**
- Setup Google Sheets trigger dengan field "Tipe Customer"
- Gunakan Switch node untuk branch berdasarkan tipe
- Buat 2 jalur berbeda dengan email template berbeda

---

## WAKTUNYA PRAKTIK! (Tugas 5)

### Sekarang Giliran Anda

- Buka dokumen panduan **Tugas 5**
- Ikuti langkah-langkah untuk membuat branching workflow
- Test dengan menambah customer berbeda tipe

**Target:** Workflow yang otomatis memberikan treatment berbeda berdasarkan kondisi

---

<!-- SECTION 4: Tugas 6 - AI Introduction -->

# Tugas 6: Klasifikasi Teks Cerdas dengan AI

---

## Tugas 6: Pengenalan AI di N8N

### Tujuan:
Menggunakan **AI** untuk secara otomatis mengkategorikan pesan masuk, menggantikan fungsi Switch dengan cara yang lebih cerdas.

### Apa yang Akan Dibuat:
- Trigger: Google Sheets (pesan customer)
- AI Processing: AI Text Classifier untuk kategorisasi otomatis
- Action: Route ke tim berbeda berdasarkan kategori AI

**Skill Baru:** AI Integration untuk intelligent automation

---

## Konsep: AI di N8N

### Automation + AI = Magic ✨

N8N memungkinkan kita mengintegrasikan **model AI canggih** langsung sebagai node dalam workflow:

**Sebelumnya (Rule-Based):**
- ❌ Buat aturan manual: "Jika kata 'urgent' maka prioritas tinggi"
- ❌ Harus update aturan terus-menerus
- ❌ Tidak paham konteks

**Dengan AI:**
- ✅ AI **memahami konteks** pesan
- ✅ AI **belajar dari contoh** yang kita berikan
- ✅ AI **lebih fleksibel** dan akurat

---

## Node: AI Text Classifier

### "Switch Node yang Cerdas"

**AI Text Classifier** mirip seperti Switch node, tapi jauh lebih pintar:

**Cara Kerja:**
1. Input: Teks yang akan diklasifikasi
2. AI: Membaca dan memahami konteks
3. Output: Kategori yang paling sesuai

**Contoh:**
- Input: "Saya ingin komplain produk rusak!"
- AI Analysis: Sentimen negatif, kategori "Komplain Produk"
- Output: Route ke Customer Service Team

**Keunggulan:** Tidak perlu buat aturan manual untuk setiap kemungkinan!

---

## Setup: Google Gemini API Key

### Cara Mendapatkan API Key

API Key = "Kunci akses" ke layanan AI Google Gemini

**Langkah Mudah:**
1. Buka **aistudio.google.com**
2. Login dengan akun Google
3. Klik **"Get API Key"**
4. Copy API key yang diberikan
5. Simpan di N8N credentials

**💡 Tips:** API key ini gratis untuk penggunaan terbatas, cukup untuk belajar!

---

## Yuk Kita Coba! (Tugas 6)

### Biarkan AI yang Bekerja!

Kita akan buat workflow yang menggunakan AI untuk mengklasifikasikan pesan customer secara otomatis.

**Yang akan kita lakukan:**
- Setup Google Sheets trigger dengan pesan customer
- Setup Google Gemini credentials
- Gunakan AI Text Classifier node
- Route hasil ke action berbeda

---

## WAKTUNYA PRAKTIK! (Tugas 6)

### Sekarang Giliran Anda

- Buka dokumen panduan **Tugas 6**
- Dapatkan API key dari aistudio.google.com
- Ikuti langkah-langkah untuk membuat AI-powered workflow
- Test dengan berbagai jenis pesan

**Target:** Workflow yang otomatis mengklasifikasi teks dengan AI

---

<!-- SECTION 5: Penutup -->

# Rekapitulasi Day 2

---

## Anda Telah Mempelajari:

### Skills Baru Hari Ini

- ✅ **Data Transformation:** Manipulasi tanggal dengan Date & Time node
- ✅ **Flow Control:** Branching logic dengan Switch node
- ✅ **AI Integration:** Klasifikasi teks cerdas dengan AI
- ✅ **Advanced Workflow:** Kombinasi transformation, branching, dan AI

**Workflow Anda sekarang jauh lebih dinamis dan intelligent!** 🎯

---

## Perbandingan: Day 1 vs Day 2

### Evolusi Kemampuan Anda

**Day 1 (Foundation):**
- Workflow linear: Trigger → Action 1 → Action 2
- Data statis atau langsung dari trigger
- Semua customer dapat treatment sama

**Day 2 (Advanced):**
- Workflow bercabang: Berbagai jalur berbeda
- Data transformation: Olah data sebelum digunakan
- AI-powered: Decision making yang cerdas

**Next Level! 🚀**

---

## Sneak Peek: Day 3

### Yang Akan Kita Pelajari Besok

Hari ini kita telah melihat bagaimana **AI bisa "berpikir"** (klasifikasi teks).

**Besok, kita akan melihat bagaimana AI bisa:**
- 🤖 **"Bertindak"** dengan AI Agent
- 🛠️ **"Menggunakan Tools"** untuk akses data & actions
- 🧠 **"Mengingat"** dengan Memory untuk conversation context

**Prepare untuk automation level yang belum pernah ada sebelumnya!**

---

## Q & A

### Ada Pertanyaan?

---

## Terima Kasih!

### Sampai Jumpa Besok!

**Hari ini Anda sudah:**
- Mengolah data dengan transformation
- Membuat keputusan dengan branching
- Mengintegrasikan AI untuk automation cerdas

**Besok kita akan membuat AI Agent yang bisa berinteraksi seperti manusia!**

**Contact:**
[Nama Anda/Perusahaan]
[Email/Social Media]
