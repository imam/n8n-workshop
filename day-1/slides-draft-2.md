# N8N Tutorial - Day 1 (DRAFT STRUCTURE V2)

**Konsep Baru: Action First, Trigger Later**

---

## [TO REVIEW] SECTION 1: Introduction - Apa itu Automation?

### [TO REVIEW] Apa itu Automation?
- Definisi automation untuk bisnis
- Contoh manual process vs automated process
- Business value: time saved, error reduction
- Automation = Menjalankan action secara otomatis

**Example slide content:**
- Manual: Copy data dari email → Paste ke spreadsheet → Kirim notifikasi
- Automated: Semua jalan sendiri tanpa copy-paste

---

## [TO REVIEW] SECTION 2: Introduction - Apa itu N8N?

### [TO REVIEW] Apa itu N8N?
- N8N adalah tool untuk automation
- Bisa connect 300+ aplikasi
- Drag & drop, no coding needed
- Self-hosted, data aman

### [TO REVIEW] Kenapa N8N untuk Automation?
- Selama action yang ingin dikerjakan ada di N8N, maka kita bisa lakukan automation
- Contoh action: Kirim email, tambah data ke sheets, buat calendar event, kirim message
- N8N punya 300+ action yang bisa dipilih

---

## [TO REVIEW] SECTION 3: Runthrough Available Actions

### [TO REVIEW] Action-Action yang Tersedia di N8N

**Slide: Popular Actions for Business**
- **Google Sheets**: Tambah row, update data, baca data
- **Gmail**: Kirim email, baca inbox
- **Google Calendar**: Buat event, update event
- **Telegram**: Kirim message ke grup/channel
- **WhatsApp**: Kirim message ke contact
- **Dan 300+ action lainnya**

**Slide: Cara Kerja Action**
- Action = Aksi yang dilakukan oleh N8N
- 1 action = 1 tugas spesifik (contoh: tambah row ke sheets)
- Multiple action bisa digabungkan jadi workflow

**Visual:**
```
[Action 1: Add Row] → [Action 2: Send Email] → [Action 3: Notify Telegram]
```

---

## [TO REVIEW] SECTION 4: Demo & Tugas 1 - Action Pertama (Single Step)

### [TO REVIEW] Tugas 1: Jalankan Action Pertama

**Learning Objective:**
- Memahami cara kerja action di N8N
- Jalankan single action dengan double-click node
- Menjalankan action secara manual (tanpa trigger)

**Business Scenario:**
- Input manual data ke sistem
- Jalankan action saat kita mau (controlled)

**Single Node Execution:**
```
[Double-click Node] → [Google Sheets: Add Row] → Execute!
```

**Prerequisites Checklist:**
- ✅ Google Sheets credential connected (OAuth2 - Sign In With Google)
  - Success state: "Account connected"
- ✅ Spreadsheet "Workshop N8N" created di sheets.google.com
- ✅ Sheet baru dengan judul "Angka"
- ✅ Header column "Angka"

**Step-by-Step Tugas 1:**
1. Buat workflow baru di N8N
2. Tambahkan node "Google Sheets"
3. Configure Google Sheets:
   - Credential: Pilih Google account yang sudah connected
   - Operation: "Append or Update Row"
   - Document: "Workshop N8N"
   - Sheet: "Angka"
   - Data Mode: "Auto-Map Input Data to Columns"
   - Values to Send:
     - Column: "Angka"
     - Value: 975
4. Save workflow
5. **Double-click pada node "Google Sheets"** untuk execute single step
6. Cek spreadsheet - angka 975 muncul di row baru!

**Demo Live:**
- Instructor jalankan step-by-step
- Tunjukkan cara double-click node untuk execute
- Tunjukkan execution result di node (success/error)
- Buka spreadsheet untuk verify data masuk
- Emphasize: Ini action yang jalan pas kita double-click node (single step)

**Key Takeaways Tugas 1:**
- Action = Aksi yang dilakukan N8N (contoh: tambah data ke sheets)
- Double-click node = Execute single action (tidak perlu trigger)
- Data yang di-input bisa dilihat di execution result di node
- **Single step execution - fokus pada action dulu, bukan workflow**

---

## [TO REVIEW] SECTION 5: Praktik Mandiri Tugas 1

**Slide: Waktunya Praktik! 🚀**

**Exercise:**
- Peserta kerjakan Tugas 1 sendiri (20 menit)
- Instructor keliling assist yang kesulitan
- Troubleshooting:
  - Credential not connected → Re-authenticate
  - Error di node → Lihat error message di execution result
  - Data tidak muncul → Cek configuration spreadsheet name & sheet name

**Success Criteria:**
- ✅ Angka 975 muncul di row baru di spreadsheet
- ✅ Node menunjukkan execution success (green checkmark)
- ✅ Peserta paham: "Saya bisa jalankan single action dengan double-click node"

---

## [TO REVIEW] SECTION 6: Introduction - Apa itu Trigger?

### [TO REVIEW] Konsep Trigger

**Slide: Dari Manual ke Otomatis**
- Tugas 1: Kita klik "Execute Workflow" → Action jalan
- Pertanyaan: Gimana kalau kita mau action jalan **otomatis** tanpa klik button?
- Jawaban: Pakai **Trigger**!

**Slide: Apa itu Trigger?**
- Trigger = Pemicu yang bikin action jalan otomatis
- Selama trigger ada di N8N, maka kita bisa koneksikan automation
- Workflow yang punya trigger = Jalan otomatis 24/7

**Slide: Contoh Trigger**
- **Google Forms**: Pas ada orang isi form → Action jalan otomatis
- **Google Sheets**: Pas ada row baru di spreadsheet → Action jalan otomatis
- **Google Calendar**: Pas ada event baru/dimulai → Action jalan otomatis
- **Telegram**: Pas ada message masuk → Action jalan otomatis
- **Schedule**: Pas jam tertentu (setiap hari jam 9 pagi) → Action jalan otomatis

**Visual:**
```
Tugas 1 (Manual):
[Klik Execute Button] → [Action: Add Row]

Dengan Trigger (Otomatis):
[Trigger: Form Submitted] → [Action: Add Row]
```

---

## [TO REVIEW] SECTION 7: Runthrough Available Triggers

### [TO REVIEW] Trigger-Trigger yang Tersedia di N8N

**Slide: Popular Triggers for Business**

**Google Sheets Trigger:**
- Otomatis jalan saat ada baris baru
- Monitor perubahan data real-time
- Use case: Tim sales input lead baru di sheets → Otomatis kirim welcome email

**Google Forms Trigger (via Sheets):**
- Form response masuk ke sheets → Otomatis trigger workflow
- Use case: Customer isi form kontak → Otomatis buat calendar event & notify tim

**Telegram Trigger:**
- Otomatis jalan saat ada pesan baru
- Monitor chat grup/channel
- Use case: Customer komplain di grup → Otomatis buat ticket & notify manager

**Google Calendar Trigger:**
- Otomatis jalan saat ada event baru atau dimulai
- Use case: Meeting dicancel → Otomatis notify semua peserta

**Schedule Trigger:**
- Otomatis jalan di waktu tertentu
- Use case: Setiap hari jam 9 pagi → Kirim summary report

---

## [TO REVIEW] SECTION 8: Demo & Tugas 2 - Trigger Pertama

### [TO REVIEW] Tugas 2: Workflow dengan Trigger Otomatis

**Learning Objective:**
- Memahami cara kerja trigger
- Menghubungkan trigger dengan action
- Workflow yang jalan otomatis tanpa klik button
- **Data mapping**: Cara koneksi data dari trigger ke action

**Business Scenario:**
- Customer isi form registrasi event
- Otomatis create calendar event dengan attendees
- Use case: Event registration, meeting scheduling

**Workflow Design:**
```
[Trigger: Google Sheets - New Row] → [Action: Google Calendar - Create Event]
```

**Prerequisites Checklist:**
- ✅ Google Sheets credential connected
- ✅ Google Calendar credential connected
- ✅ Google Form created dengan field:
  - Name (Short Answer)
  - Email (Short Answer)
  - Event Date (Date)
- ✅ Form connected ke Google Sheets ("Link to Sheets")

**Slide: Setup Google Form (Pre-Demo)**

1. Buat Google Form baru
2. Tambahkan pertanyaan:
   - **Name** (Short Answer)
   - **Email** (Short Answer)
   - **Event Date** (Date)
3. Klik tab "Responses" → "Link to Sheets"
4. Google otomatis buat spreadsheet baru untuk menyimpan responses
5. Setiap kali ada orang isi form → Data masuk ke spreadsheet

**Step-by-Step Tugas 2:**

1. Buat workflow baru
2. Tambahkan node "Google Sheets Trigger"
   - Credential: Pilih Google account
   - Trigger On: "Row Added"
   - Document: Pilih spreadsheet dari form (biasanya nama "Form Responses...")
   - Sheet: "Form Responses 1"
3. **PENTING**: Klik "Listen for Test Event" atau jalankan sekali untuk ambil sample data
   - Isi form sekali untuk generate test data
   - Data akan muncul di node
4. Tambahkan node "Google Calendar"
   - Connect dari Google Sheets Trigger
   - Credential: Pilih Google account
   - Operation: "Create Event"
5. Configure Calendar Event:
   - Calendar: "Primary"
   - Start Date: **Drag field "Event Date" dari Sheets Trigger**
   - End Date: (Opsional, bisa sama dengan Start Date)
   - Summary: **Drag field "Name" dari Sheets Trigger**
   - Additional Fields → Attendees:
     - **Drag field "Email" dari Sheets Trigger**
6. **Activate workflow** (toggle switch di kanan atas)
7. Test: Isi Google Form dengan data dummy
8. Wait ~1-2 menit (trigger check interval)
9. Buka Google Calendar → Event muncul dengan attendees!

**Slide: Demo Live - Data Mapping Explained**

**Apa itu Data Mapping?**
- Trigger dapat data (Name, Email, Event Date)
- Action butuh data (Summary, Attendees, Start Date)
- Data Mapping = Koneksikan data dari trigger ke action

**Cara Data Mapping:**
- Klik field di Calendar node (contoh: Summary)
- Drag field "Name" dari Sheets Trigger node
- N8N otomatis isi expression: `{{ $json.Name }}`
- Artinya: Ambil data "Name" dari trigger, masukkan ke "Summary" di calendar

**Visual:**
```
Sheets Trigger Output:
- Name: "John Doe"
- Email: "john@example.com"
- Event Date: "2025-10-15"

↓ Data Mapping ↓

Calendar Action Input:
- Summary: {{ $json.Name }} → "John Doe"
- Attendees: {{ $json.Email }} → "john@example.com"
- Start Date: {{ $json["Event Date"] }} → "2025-10-15"
```

**Slide: Demo Live - Testing**

1. Instructor isi Google Form dengan data:
   - Name: "Workshop N8N"
   - Email: "participant@example.com"
   - Event Date: "2025-10-10"
2. Tunjukkan data masuk ke spreadsheet
3. Wait (explain: automatic trigger check every 1-2 minutes)
4. Buka Google Calendar
5. Event "Workshop N8N" muncul dengan attendees!

**Key Takeaways Tugas 2:**
- Trigger = Pemicu otomatis, bikin action jalan tanpa klik button
- Data mapping = Koneksi data dari trigger ke action dengan drag-drop
- Workflow aktif (toggle ON) = Jalan terus 24/7
- **Ini automation penuh: Form submitted → Calendar event created (no manual work!)**

---

## [TO REVIEW] SECTION 9: Praktik Mandiri Tugas 2

**Slide: Waktunya Praktik! 🚀**

**Exercise:**
- Peserta kerjakan Tugas 2 sendiri (30 menit)
- Instructor assist credential setup & data mapping
- Troubleshooting:
  - Form not connected to Sheets → Check "Link to Sheets"
  - Trigger not firing → Check workflow is activated (toggle ON)
  - Calendar event not created → Check data mapping (field names match)
  - Error "required field missing" → Check all required fields filled

**Success Criteria:**
- ✅ Form submission masuk ke spreadsheet
- ✅ Calendar event created otomatis
- ✅ Attendees email muncul di event
- ✅ Peserta paham: "Workflow jalan otomatis tanpa klik button!"

---

## [TO REVIEW] SECTION 10: Workflow Concepts (Post-Practice)

**Slide: Apa itu Workflow?**

Sekarang kita sudah praktik, mari kita definisikan:

- **Workflow** = Rangkaian action yang berjalan otomatis
- **Node** = Setiap kotak di workflow (trigger atau action)
- **Connection** = Garis yang hubungkan node satu ke node lain

**Contoh dari Tugas 2:**
- Node 1: Google Sheets Trigger (pemicu)
- Node 2: Google Calendar Action (aksi)
- Connection: Data mengalir dari Node 1 ke Node 2

**Slide: Cara Kerja Antar Node**

- Setiap node terima data dari node sebelumnya
- Node proses data sesuai konfigurasi
- Node kirim hasil ke node berikutnya
- Seperti assembly line di pabrik

**Visual:**
```
Sheets Trigger → Calendar Action → Email Action → Slack Notification
     ↓                ↓                 ↓                ↓
  (data row)    (create event)    (send email)    (notify team)
```

---

## [TO REVIEW] SECTION 11: Execution History & Debugging

**Slide: Execution History Overview**

- **Execution History** = Riwayat semua workflow yang pernah jalan
- Bisa lihat:
  - Status (Success/Failed/Running)
  - Timestamp (kapan dijalankan)
  - Duration (berapa lama)
  - Data yang diproses

**Slide: Cara Lihat Execution History**

1. Klik tab "Executions" di sidebar
2. Pilih execution yang mau dilihat
3. Klik node untuk lihat input/output data
4. Kalau error, bisa lihat error message

**Slide: Debugging Workflow**

- Workflow gagal? Cek execution history
- Klik node yang error → Lihat error message
- Common errors:
  - Credential expired → Re-authenticate
  - Required field missing → Lengkapi configuration
  - Invalid data format → Cek data mapping

---

## [TO REVIEW] SECTION 12: Credential Management

**Slide: Mengelola Kredensial dengan Aman**

- Kredensial = "Kunci akses" untuk connect N8N dengan aplikasi
- N8N simpan credential secara aman (encrypted)
- 1 credential bisa dipakai untuk banyak workflow

**Slide: Cara Connect Aplikasi**

1. Pilih node yang mau dipakai (contoh: Gmail)
2. Klik "Credential" → "Create New"
3. Pilih authentication method (biasanya OAuth2)
4. Klik "Sign In With Google" (atau service lain)
5. Allow access untuk N8N
6. Success: "Account connected"

---

## [TO REVIEW] SECTION 13: Tips & Best Practices

**Slide: Tips Membuat Workflow**

- **Start simple**: Mulai dari 1 trigger + 1 action dulu
- **Test frequently**: Test setiap kali tambah node baru
- **Use meaningful names**: Kasih nama workflow yang jelas
- **Document your workflow**: Tambah notes di node kalau perlu

**Slide: Common Mistakes to Avoid**

- Lupa activate workflow (toggle masih OFF)
- Credential expired, tidak di-refresh
- Data mapping salah (typo di field name)
- Tidak test dulu sebelum activate

---

## [TO REVIEW] SECTION 14: Brainstorming - Tugas 3 (Optional Advanced)

**Slide: Challenge - Gabungkan Action & Trigger**

Sekarang kamu sudah paham action & trigger, coba buat workflow:

**Tugas 3 Ideas:**

**Option 1: Customer Support Automation**
- Trigger: Google Form (customer complaint)
- Action 1: Google Sheets (log complaint)
- Action 2: Gmail (send acknowledgment email)
- Action 3: Telegram (notify support team)

**Option 2: Lead Management**
- Trigger: Google Form (lead registration)
- Action 1: Google Sheets (save lead data)
- Action 2: Gmail (send welcome email)
- Action 3: Google Calendar (schedule follow-up call)

**Option 3: Event Registration**
- Trigger: Google Form (event registration)
- Action 1: Gmail (send confirmation email)
- Action 2: Google Calendar (create event)
- Action 3: Telegram (notify organizer)

---

## [TO REVIEW] SECTION 15: Closing

**Slide: Selamat! Anda Sudah Jadi Automation Expert! 🎉**

### Anda telah berhasil:

✅ Memahami konsep automation & N8N

✅ Menjalankan action pertama (Tugas 1)

✅ Membuat workflow dengan trigger otomatis (Tugas 2)

✅ Data mapping antar node

✅ Membuat sistem yang bekerja 24/7

**Bayangkan berapa jam per minggu yang bisa dihemat dengan automation ini!**

**Slide: Next Steps**

- Eksplorasi 300+ nodes yang tersedia
- Buat automation untuk bisnis Anda sendiri
- Join N8N community untuk belajar lebih lanjut
- Day 2: Advanced workflows, conditional logic, AI integration!

---

## [TO REVIEW] SUMMARY OF STRUCTURE

### Learning Flow:
1. **Automation concept** → Intro N8N → Available actions
2. **Tugas 1**: Execute workflow button + Action (manual)
3. **Practice Tugas 1**
4. **Trigger concept** → Available triggers
5. **Tugas 2**: Trigger + Action (automatic) + Data mapping
6. **Practice Tugas 2**
7. **Workflow concepts** (post-practice, easier to understand)
8. **Execution history & debugging**
9. **Credential management**
10. **Tips & Tugas 3** (optional advanced)
11. **Closing**

### Estimated Slide Count:
- Section 1-3 (Intro + Actions): ~15 slides
- Section 4-5 (Tugas 1 + Practice): ~10 slides
- Section 6-7 (Triggers intro): ~10 slides
- Section 8-9 (Tugas 2 + Practice): ~15 slides
- Section 10-12 (Concepts + History): ~10 slides
- Section 13-15 (Tips + Closing): ~8 slides

**Total: ~68 slides**

### Estimated Timing:
- Section 1-3: 15 menit (intro + action overview)
- Section 4: 15 menit (Tugas 1 demo)
- Section 5: 20 menit (Practice Tugas 1)
- Section 6-7: 10 menit (Trigger intro)
- Section 8: 20 menit (Tugas 2 demo + data mapping)
- Section 9: 30 menit (Practice Tugas 2)
- Section 10-12: 15 menit (Concepts + execution)
- Section 13-15: 10 menit (Tips + closing)

**Total: ~145 menit (2.5 jam)**

---

## [TO REVIEW] KEY DIFFERENCES FROM PREVIOUS DRAFT

### Major Changes:
1. **Action-first approach**: Introduce action before trigger
2. **No "trigger" term until after Tugas 1**: Let them experience action first
3. **Simpler progression**: Manual button → Automatic trigger
4. **Post-practice concepts**: Teach workflow theory AFTER hands-on
5. **Separate file for tasks**: Consider creating `tugas.md`

### Removed:
- Early workflow theory (moved to post-practice)
- Complex multi-node demo early on
- Pinned data section (too advanced for Day 1)

### Added:
- "Runthrough available actions" section
- "Runthrough available triggers" section
- Detailed data mapping explanation
- Execute workflow button as "manual trigger"

---

## [TO REVIEW] NOTES FOR IMPLEMENTATION

**Separate Files to Create:**
1. **tugas.md**: Detailed task instructions for Tugas 1, 2, 3
2. **demo.md**: Instructor guide for live demos
3. **slides.md**: Actual reveal.js slides based on this structure

**Image Requirements:**
- Screenshot: Execute Workflow button
- Screenshot: Google Sheets node configuration
- Screenshot: Data mapping (drag field from trigger)
- Screenshot: Workflow activated toggle
- Diagram: Manual vs Automatic workflow visual
- Screenshot: Execution history view

**Language Considerations:**
- "Execute Workflow" button dijelaskan sebagai "tombol untuk jalankan workflow manual"
- Avoid: webhook, polling, JSON, expression (kecuali saat data mapping, jelaskan sederhana)
- Use: form, spreadsheet, calendar, drag-drop, klik button
