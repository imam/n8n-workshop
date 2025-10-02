# N8N Tutorial - Day 1 (DRAFT STRUCTURE)

---

## [TO REVIEW] SECTION 1: Introduction & Foundation Theory

### Slides yang ada (KEEP):
- Apa itu N8N? (slide 12-24)
- Target Hari Ini (slide 27-36)

### Slides yang DITAMBAHKAN:
- **[TO REVIEW] Apa itu Automation?**
  - Definisi automation untuk bisnis
  - Contoh manual process vs automated process
  - Business value: time saved, error reduction

- **[TO REVIEW] Apa itu Trigger?**
  - Definisi trigger = "pemicu" workflow
  - 2 jenis trigger:
    - Manual Trigger (Execute Workflow) - klik tombol untuk jalankan
    - Automatic Trigger (Google Forms, Telegram, Calendar) - otomatis jalan saat ada event
  - Kapan pakai manual vs automatic

- **[TO REVIEW] Apa itu Action?**
  - Definisi action = "aksi yang dilakukan" setelah trigger
  - Contoh: kirim email, tambah data ke sheets, buat calendar event
  - 1 workflow bisa punya banyak action

---

## [TO REVIEW] SECTION 2: Workflow & Node Concepts (REORDERED)

### Slides yang ada (KEEP & IMPROVE):
- Apa itu Workflow? (slide 68-76)
- Anatomik Node (slide 79-86)
- Cara Kerja Antar Node (slide 88-96)
- Menggunakan Data dari Node Sebelumnya (slide 99-105)

### Perubahan:
- Pindahkan section ini SEBELUM demo pertama
- Tambahkan visual untuk "Manual Trigger" node

---

## [TO REVIEW] SECTION 3: Prerequisites & Credential Setup (NEW SECTION - MOVED EARLIER)

### Slides yang DITAMBAHKAN:
- **[TO REVIEW] Yang Perlu Disiapkan**
  - Google Account (untuk Sheets, Calendar, Gmail)
  - Spreadsheet kosong untuk latihan
  - N8N account (sudah login)

- **[TO REVIEW] Menghubungkan Google Account**
  - Langkah-langkah OAuth2 connection
  - Screenshot "Account connected" success state
  - Tips: credential bisa dipakai untuk semua workflow

### Slides yang DIPINDAHKAN dari section 5:
- Mengelola Kredensial dengan Aman (slide 154-156)
- Cara Menghubungkan Aplikasi (slide 160-168)

---

## [TO REVIEW] SECTION 4: Demo 1 - Simplest Workflow (NEW SECTION)

### [TO REVIEW] Tugas 1: Manual Trigger + Google Sheets

**Slide: Tujuan Pembelajaran**
- Memahami cara kerja manual trigger
- Membuat workflow pertama dengan 1 action
- Menjalankan workflow dan melihat hasilnya

**Slide: Skenario Bisnis**
- Input manual data ke sistem
- Use case: testing workflow, one-time data entry

**Slide: Workflow Design**
```
Manual Trigger → Google Sheets (Append Row)
```

**Slide: Prerequisites Checklist**
- ✅ Google Sheets credential connected
- ✅ Spreadsheet "Workshop N8N" created
- ✅ Sheet "Angka" dengan header column "Angka"

**Slide: Step-by-Step Tugas 1**
1. Buat workflow baru
2. Tambahkan node "Manual Trigger" (Execute Workflow)
3. Tambahkan node "Google Sheets"
4. Configure Google Sheets:
   - Operation: Append Row
   - Document: Workshop N8N
   - Sheet: Angka
   - Column: Angka
   - Value: 975
5. Connect nodes
6. Klik "Execute Workflow"
7. Cek spreadsheet - angka 975 muncul!

**Slide: Demo Live**
- Instructor jalankan live
- Tunjukkan execution result
- Buka spreadsheet untuk verify

**Slide: Key Takeaways Tugas 1**
- Manual trigger = kontrol penuh kapan workflow jalan
- 1 trigger + 1 action = workflow paling simpel
- Data yang di-input bisa dilihat di execution result

---

## [TO REVIEW] SECTION 5: Demo 2 - Automatic Trigger (NEW SECTION)

### [TO REVIEW] Tugas 2: Google Form → Calendar Event

**Slide: Tujuan Pembelajaran**
- Memahami automatic trigger
- Data mapping antar node
- Workflow yang jalan otomatis tanpa klik tombol

**Slide: Skenario Bisnis**
- Customer isi form registrasi event
- Otomatis create calendar event dengan attendees
- Use case: event registration, meeting scheduling

**Slide: Workflow Design**
```
Google Sheets Trigger (Form Response) → Google Calendar (Create Event)
```

**Slide: Prerequisites Checklist**
- ✅ Google Sheets credential connected
- ✅ Google Calendar credential connected
- ✅ Google Form created & linked to Sheets
- ✅ Form punya field: Name, Email, Event Date

**Slide: Setup Google Form**
1. Buat Google Form baru
2. Tambahkan pertanyaan:
   - Name (Short Answer)
   - Email (Short Answer)
   - Event Date (Date)
3. Klik "Responses" → "Link to Sheets"
4. Form responses akan masuk ke spreadsheet otomatis

**Slide: Step-by-Step Tugas 2**
1. Buat workflow baru
2. Tambahkan trigger "Google Sheets"
   - Event: On Row Added
   - Document: [pilih spreadsheet dari form]
3. Tambahkan action "Google Calendar"
   - Operation: Create Event
4. Configure Calendar Event:
   - Calendar: Primary
   - Start Date: [drag "Event Date" dari input]
   - Summary: [drag "Name" dari input]
5. Additional Fields → Attendees:
   - [drag "Email" dari input]
6. Activate workflow
7. Test: Isi form → Cek calendar!

**Slide: Demo Live - Data Mapping**
- Tunjukkan cara drag field dari input node
- Explain: Email dari form → Attendees di calendar
- Tunjukkan expression preview

**Slide: Demo Live - Testing**
1. Isi Google Form dengan data dummy
2. Wait (automatic trigger check interval ~1 min)
3. Buka Google Calendar
4. Event muncul dengan attendees!

**Slide: Key Takeaways Tugas 2**
- Automatic trigger = no manual click needed
- Data mapping = connect data antar node dengan drag
- Workflow aktif = jalan terus 24/7

---

## [TO REVIEW] SECTION 6: Demo 3 - Multi-Node Workflow (EXISTING, REPOSITIONED)

### Slides yang DIPINDAHKAN & IMPROVED:
- Demo: Workflow Pertama Anda (slide 40-42) → RENAME: "Demo 3: Advanced Multi-Node"
- Demo: Otomatisasi Customer Inquiry (slide 44-50) → Keep as-is
- Live Demo: Dari Pertanyaan ke Penjualan (slide 53-60) → Keep as-is

### Perubahan:
- Posisi: Setelah Tugas 1 & 2, jadi demo "advanced"
- Tambahkan intro slide: "Now you understand basics, let's see complex workflow"
- Emphasize: Ini kombinasi dari konsep yang sudah dipelajari

---

## [TO REVIEW] SECTION 7: Trigger Types Reference (EXISTING, MINOR EDIT)

### Slides yang ada (KEEP):
- Google Sheets Trigger (slide 113-122)
- Telegram Trigger (slide 126-134)
- Google Calendar Trigger (slide 138-145)

### Perubahan:
- Tambahkan intro slide: "Trigger Types You Can Use"
- Tambahkan slide: "Manual Trigger (Execute Workflow)" di awal section

---

## [TO REVIEW] SECTION 8: Execution History & Pinned Data (EXISTING, KEEP)

### Slides yang ada (KEEP):
- Execution History Overview (slide 176-184)
- Apa itu Pinned Data? (slide 204-213)
- Contoh Real: Pin Data dari Order E-commerce (slide 216-242)
- Membuat Pinned Data dari Past Execution (slide 245-251)

### Perubahan:
- Tambahkan contoh execution dari Tugas 1 & 2

---

## [TO REVIEW] SECTION 9: Hands-on Exercise (REVISED)

### [TO REVIEW] Exercise Progression (3 Levels)

**Slide: Waktunya Praktik! 🚀**
- Keep existing slide (slide 187-200)

**[TO REVIEW] Exercise Level 1: Tugas 1 Mandiri**
- Peserta kerjakan Tugas 1 sendiri (15 menit)
- Instructor assist yang kesulitan
- Success criteria: Angka muncul di spreadsheet

**[TO REVIEW] Exercise Level 2: Tugas 2 Mandiri**
- Peserta kerjakan Tugas 2 sendiri (20 menit)
- Instructor assist credential setup
- Success criteria: Calendar event created dari form

**[TO REVIEW] Exercise Level 3: Newsletter Automation (Existing)**
- Keep existing exercise (slide 259-266)
- Now sebagai "advanced challenge"
- Kombinasi: Form trigger + Email + Sheets + Telegram

**Slide: Troubleshooting Tips**
- Credential not connected → Re-authenticate
- Workflow not triggered → Check activation toggle
- Data not showing → Check execution history
- Error di node → Lihat error message di execution

---

## [TO REVIEW] SECTION 10: Closing (EXISTING, KEEP)

### Slides yang ada (KEEP):
- Selamat! Anda Sudah Jadi Automation Expert! 🎉 (slide 269-281)

### Perubahan:
- Update achievements list dengan Tugas 1 & 2

---

## [TO REVIEW] SUMMARY OF CHANGES

### ADDED (New Content):
1. Apa itu Automation slide
2. Apa itu Trigger slide (Manual vs Automatic)
3. Apa itu Action slide
4. Prerequisites & Setup section (moved earlier)
5. Demo 1: Tugas 1 - Manual Trigger + Sheets (full section ~8 slides)
6. Demo 2: Tugas 2 - Form Trigger + Calendar (full section ~10 slides)
7. Exercise Level 1 & 2 (Tugas 1 & 2 mandiri)
8. Troubleshooting Tips slide

### MOVED (Repositioned):
1. Credential section → Earlier (before demos)
2. Multi-node demo → Later (as Demo 3 advanced)
3. Workflow concepts → Before Demo 1

### KEPT (No Changes):
1. Introduction & Target
2. Workflow & Node concepts (improved)
3. Trigger types reference
4. Execution history & Pinned data
5. Closing celebration

### TOTAL ESTIMATED SLIDE COUNT:
- Original: ~70 slides
- New structure: ~95 slides (+25 slides for progressive demos)

---

## [TO REVIEW] TIMING ESTIMATION

- Section 1-2 (Intro + Concepts): 20 menit
- Section 3 (Prerequisites): 10 menit
- Section 4 (Demo 1 + Exercise): 25 menit
- Section 5 (Demo 2 + Exercise): 30 menit
- Section 6 (Demo 3 Advanced): 15 menit
- Section 7-8 (Triggers + History): 15 menit
- Section 9 (Exercise Level 3): 25 menit
- Section 10 (Closing): 5 menit

**Total: ~145 menit (2.5 jam)**

---

## [TO REVIEW] NOTES FOR IMPLEMENTATION

1. **Image Requirements:**
   - Screenshot Manual Trigger node
   - Screenshot Google Sheets append configuration
   - Screenshot Google Form → Sheets linking
   - Screenshot data mapping (drag field)
   - Screenshot Calendar event result
   - Workflow diagram Tugas 1 & 2

2. **Demo Preparation:**
   - Create demo.md for Tugas 1 & 2 instructor guide
   - Prepare dummy data for forms
   - Test credentials setup flow
   - Prepare troubleshooting backup plans

3. **Business Language:**
   - Keep "Manual Trigger" term (N8N-specific)
   - Explain "Execute Workflow" = "klik tombol untuk jalankan"
   - Avoid: polling, webhook, JSON
   - Use: form, spreadsheet, calendar, email

4. **Progressive Complexity Check:**
   - ✅ Tugas 1: 2 nodes (Manual → Sheets)
   - ✅ Tugas 2: 2 nodes (Sheets Trigger → Calendar)
   - ✅ Demo 3: 4+ nodes (Multi-step automation)
   - ✅ Exercise 3: 4+ nodes (Newsletter workflow)
