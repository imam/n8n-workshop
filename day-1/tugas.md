# Tugas Workshop N8N - Day 1

---

## Tugas 1: Jalankan Action Pertama (Single Step Execution)

### Tujuan Pembelajaran
- Memahami cara kerja action di N8N
- Jalankan single action dengan double-click node
- Menjalankan action secara manual tanpa trigger

### Business Scenario
Input manual data ke sistem spreadsheet untuk tracking atau record keeping.

---

### Prerequisites

**1. Google Sheets Credential**
- Buka N8N
- Klik menu "Credentials" di sidebar
- Klik "Add Credential" → Pilih "Google Sheets OAuth2 API"
- Klik "Sign In With Google"
- Pilih Google account Anda
- Allow access untuk N8N
- Success state: Muncul pesan "Account connected"

**2. Persiapan Spreadsheet**
- Buka [sheets.google.com](https://sheets.google.com)
- Buat spreadsheet baru
- Rename menjadi: **"Workshop N8N"**
- Buat sheet baru (tab di bawah) dengan nama: **"Angka"**
- Di sheet "Angka", tambahkan header di cell A1: **"Angka"**

---

### Langkah-Langkah Tugas 1

**Step 1: Buat Workflow Baru**
1. Di N8N, klik tombol "+ New Workflow"
2. Rename workflow menjadi: "Tugas 1 - Add Number"

**Step 2: Tambahkan Node Google Sheets**
1. Klik tombol "+" atau drag dari node panel
2. Search "Google Sheets"
3. Pilih "Google Sheets"

**Step 3: Configure Google Sheets Node**
1. **Credential**: Pilih Google account yang sudah connected
2. **Resource**: Pilih "Sheet"
3. **Operation**: Pilih "Append or Update Row"
4. **Document**: Ketik atau pilih "Workshop N8N"
5. **Sheet**: Pilih "Angka"
6. **Data Mode**: Pilih "Auto-Map Input Data to Columns"
7. **Values to Send**:
   - Klik "Add Field"
   - **Column Name**: Angka
   - **Column Value**: 975

**Step 4: Save Workflow**
1. Klik tombol "Save" di kanan atas
2. Workflow tersimpan

**Step 5: Execute Single Action**
1. **Double-click pada node "Google Sheets"**
2. Node akan execute
3. Tunggu beberapa detik
4. Node akan menunjukkan:
   - ✅ Green checkmark (success)
   - atau ❌ Red X (error)

**Step 6: Verify di Spreadsheet**
1. Buka spreadsheet "Workshop N8N" di Google Sheets
2. Buka sheet "Angka"
3. Cek row baru: Angka **975** muncul di kolom A

---

### Target Success
- ✅ Angka 975 muncul di row baru di spreadsheet
- ✅ Node menunjukkan execution success (green checkmark)
- ✅ Anda paham: "Saya bisa jalankan single action dengan double-click node"

---

### Troubleshooting

**Error: "Credential not connected"**
- Solution: Re-authenticate Google Sheets credential
- Klik credential → Sign In With Google lagi

**Error: "Document not found"**
- Solution: Cek nama spreadsheet
- Pastikan nama persis: "Workshop N8N"

**Error: "Sheet not found"**
- Solution: Cek nama sheet
- Pastikan ada sheet dengan nama: "Angka"

**Data tidak muncul di spreadsheet**
- Cek apakah node menunjukkan success
- Refresh halaman Google Sheets
- Cek configuration: Column name = "Angka"

---

## Tugas 2: Workflow dengan Trigger Otomatis (Connecting Trigger & Action)

### Tujuan Pembelajaran
- Memahami cara kerja trigger
- Menghubungkan trigger dengan action dalam workflow
- Workflow yang jalan otomatis tanpa klik button
- Data mapping: Cara koneksi data dari trigger ke action

### Business Scenario
Customer isi form registrasi event → Otomatis create calendar event dengan attendees. Use case: Event registration, meeting scheduling.

---

### Prerequisites

**1. Google Calendar Credential**
- Buka N8N → Menu "Credentials"
- Klik "Add Credential" → Pilih "Google Calendar OAuth2 API"
- Klik "Sign In With Google"
- Pilih Google account yang sama dengan Sheets
- Allow access untuk N8N
- Success state: "Account connected"

**2. Persiapan Google Form**

**Step 1: Buat Google Form**
1. Buka [forms.google.com](https://forms.google.com)
2. Klik "+ Blank" untuk buat form baru
3. Rename form menjadi: "Event Registration"

**Step 2: Tambahkan Pertanyaan**
1. **Pertanyaan 1**:
   - Question: "Nama Lengkap"
   - Type: Short Answer
   - Toggle "Required" ON

2. **Pertanyaan 2**:
   - Klik "+" untuk tambah pertanyaan
   - Question: "Email"
   - Type: Short Answer
   - Toggle "Required" ON

3. **Pertanyaan 3**:
   - Klik "+" untuk tambah pertanyaan
   - Question: "Tanggal Event"
   - Type: Date
   - Toggle "Required" ON

**Step 3: Link Form to Sheets**
1. Klik tab "Responses" di atas
2. Klik icon Google Sheets (hijau)
3. Pilih "Create a new spreadsheet"
4. Spreadsheet name: "Event Registration (Responses)"
5. Klik "Create"
6. Google otomatis buat spreadsheet baru
7. Setiap form submission → Data masuk ke spreadsheet

---

### Langkah-Langkah Tugas 2

**Step 1: Buat Workflow Baru**
1. Di N8N, klik "+ New Workflow"
2. Rename workflow: "Tugas 2 - Event Registration"

**Step 2: Tambahkan Google Sheets Trigger**
1. Klik tombol "+" atau drag dari panel
2. Search "Google Sheets Trigger"
3. Pilih "Google Sheets Trigger"
4. Configure:
   - **Credential**: Pilih Google account
   - **Trigger On**: Pilih "Row Added"
   - **Document**: Pilih spreadsheet "Event Registration (Responses)"
   - **Sheet**: Pilih "Form Responses 1"

**Step 3: Test Trigger - Generate Sample Data**
1. Klik button "Listen for Test Event" di node
2. Buka Google Form di tab lain
3. Isi form dengan data dummy:
   - Nama Lengkap: "John Doe"
   - Email: "john@example.com"
   - Tanggal Event: Pilih tanggal besok
4. Submit form
5. Kembali ke N8N
6. Data akan muncul di Sheets Trigger node
7. Klik "Use This Event" (atau node otomatis dapat data)

**Step 4: Tambahkan Google Calendar Node**
1. Klik "+" di sebelah kanan Sheets Trigger node
2. Search "Google Calendar"
3. Pilih "Google Calendar"
4. Configure:
   - **Credential**: Pilih Google account
   - **Resource**: Pilih "Event"
   - **Operation**: Pilih "Create"
   - **Calendar**: Pilih "Primary"

**Step 5: Data Mapping - Connect Trigger Data to Calendar**

**Start Date:**
1. Klik field "Start"
2. Dari panel kanan, cari field "Tanggal Event" dari Sheets Trigger
3. Drag field "Tanggal Event" ke field "Start"
4. N8N otomatis isi expression

**Event Summary:**
1. Klik field "Summary"
2. Drag field "Nama Lengkap" dari Sheets Trigger
3. Expression: `{{ $json["Nama Lengkap"] }}`

**Attendees:**
1. Scroll ke "Additional Fields"
2. Klik "Add Field" → Pilih "Attendees"
3. Klik pada field "Attendees"
4. Drag field "Email" dari Sheets Trigger
5. Expression: `{{ $json["Email"] }}`

**Step 6: Activate Workflow**
1. Klik toggle switch "Inactive" di kanan atas
2. Toggle berubah jadi "Active"
3. Workflow sekarang jalan otomatis 24/7

**Step 7: Test Workflow**
1. Buka Google Form di tab baru
2. Isi form dengan data real:
   - Nama Lengkap: "Workshop Test"
   - Email: (email Anda sendiri)
   - Tanggal Event: Pilih tanggal minggu depan
3. Submit form
4. **Tunggu 1-2 menit** (trigger check interval)
5. Buka Google Calendar
6. Event "Workshop Test" muncul!
7. Check attendees: Email Anda ada di list

---

### Target Success
- ✅ Form submission masuk ke spreadsheet
- ✅ Calendar event created otomatis
- ✅ Attendees email muncul di event
- ✅ Anda paham: "Workflow jalan otomatis tanpa klik button!"

---

### Troubleshooting

**Form not connected to Sheets**
- Solution: Check "Responses" tab di Google Form
- Klik icon Sheets lagi → "Link to Sheets"

**Trigger not firing**
- Solution: Check workflow is activated (toggle ON)
- Wait 1-2 minutes (automatic trigger check interval)
- Check execution history di sidebar

**Calendar event not created**
- Solution: Check data mapping
- Pastikan field names match persis (case-sensitive)
- Check execution history untuk lihat error

**Error "required field missing"**
- Solution: Check all required fields filled:
  - Start date
  - Summary
  - Calendar
- Check data mapping expressions

**Error "Invalid date format"**
- Solution: Pastikan Google Form question type = "Date"
- Bukan "Short Answer" untuk tanggal

---

### Data Mapping Explained

**Apa itu Data Mapping?**
- Trigger dapat data dari form (Nama, Email, Tanggal)
- Action butuh data untuk create event (Summary, Attendees, Start)
- Data Mapping = Koneksikan data dari trigger ke action

**Visual Flow:**
```
Google Form
    ↓
Sheets Trigger (dapat data):
    - Nama Lengkap: "John Doe"
    - Email: "john@example.com"
    - Tanggal Event: "2025-10-10"
    ↓
Data Mapping (drag & drop)
    ↓
Google Calendar Action (kirim data):
    - Summary: {{ Nama Lengkap }} → "John Doe"
    - Attendees: {{ Email }} → "john@example.com"
    - Start: {{ Tanggal Event }} → "2025-10-10"
    ↓
Calendar Event Created!
```

**Key Concept:**
- Drag field dari trigger → Otomatis jadi expression
- Expression format: `{{ $json["Field Name"] }}`
- Data mengalir dari trigger ke action

---

## Tugas 3 (Optional - Advanced Challenge)

### Challenge: Gabungkan Multiple Actions

Sekarang Anda sudah paham trigger dan action, coba buat workflow dengan **multiple actions**:

### Option 1: Customer Support Automation
**Trigger:** Google Form (customer complaint)
**Actions:**
1. Google Sheets - Log complaint
2. Gmail - Send acknowledgment email
3. Telegram - Notify support team

### Option 2: Lead Management
**Trigger:** Google Form (lead registration)
**Actions:**
1. Google Sheets - Save lead data
2. Gmail - Send welcome email
3. Google Calendar - Schedule follow-up call

### Option 3: Event Registration Complete
**Trigger:** Google Form (event registration)
**Actions:**
1. Gmail - Send confirmation email
2. Google Calendar - Create event
3. Telegram - Notify organizer

---

### Tips untuk Tugas 3

**Start Simple:**
- Mulai dengan trigger + 1 action
- Test dulu sebelum tambah action berikutnya
- Tambah action satu per satu

**Data Mapping:**
- Semua action bisa akses data dari trigger
- Drag field yang sama ke multiple actions

**Testing:**
- Activate workflow
- Test dengan data real
- Check semua actions berhasil
- Check execution history untuk debug

---

## Summary - What You Learned

### Tugas 1: Single Action
- ✅ Action = Aksi yang dilakukan N8N
- ✅ Double-click node = Execute single step
- ✅ Focus pada action dulu, bukan workflow

### Tugas 2: Trigger + Action Workflow
- ✅ Trigger = Pemicu otomatis
- ✅ Workflow = Connecting trigger to action
- ✅ Data mapping = Koneksi data antar node
- ✅ Active workflow = Jalan 24/7

### Next Steps
- Eksplorasi 300+ nodes yang tersedia
- Buat automation untuk bisnis Anda
- Day 2: Advanced workflows, conditional logic, AI integration!

---

**Selamat! Anda sudah menguasai fundamentals N8N automation! 🎉**
