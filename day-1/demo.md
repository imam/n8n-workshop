# Day-1 Demo Instructor Guide

## Overview
Panduan ini berisi 3 workflow demo yang dirancang untuk target audience business professionals yang belum pernah coding. Setiap workflow memiliki tingkat kompleksitas berbeda untuk tujuan pembelajaran yang spesifik.

---

## Workflow 1: Minor Complexity - "Customer Support Automation" [DRAFT]

### Business Scenario
**Problem**: Customer service team kewalahan dengan pertanyaan yang masuk via website contact form
**Solution**: Otomatisasi capture dan routing pertanyaan customer dari form submission

### Workflow Design (4 nodes)
```
Google Forms (New Submission) → Google Sheets (Log) → Gmail (Auto Reply) → Slack (Notify Team)
```

### **[DRAFT]** Wow Factor Elements:
- **Multiple outputs** dari satu input terstruktur
- **Real-time notifications** ke berbagai platform
- **Automatic logging** untuk reporting
- **Instant auto-reply** ke customer dengan data personal

### **[DRAFT]** Instructor Setup TODO:
- [ ] Create Google Form dengan fields: Nama, Email, Pertanyaan, Kategori
- [ ] Setup Google Sheets untuk log customer inquiries
- [ ] Test Gmail auto-reply dengan merge fields dari form
- [ ] Configure Slack notification dengan customer details
- [ ] Prepare sample form submissions untuk demo

### **[DRAFT]** Expected Demo Flow:
1. Show customer mengisi Google Form (live demo atau prepared)
2. Demonstrate data otomatis tersimpan di Google Sheets dengan struktur
3. Show personalized auto-reply email terkirim ke customer
4. Show notifikasi tim di Slack dengan customer details
5. Highlight business value: "Tidak ada inquiry yang terlewat, respon instan ke customer"

---

## Workflow 2: Basic Notification - "New Lead Alert" [DRAFT]

### Business Scenario
**Problem**: Sales team kesulitan tracking perubahan status lead secara real-time
**Solution**: Otomatisasi notifikasi untuk lead baru DAN update status existing lead

### Workflow Design (2 nodes)
```
Google Sheets Trigger → Slack (Notify Sales Team)
```

### **[DRAFT]** Learning Objectives:
- Memahami trigger yang responsif terhadap berbagai perubahan data
- Menghubungkan dua aplikasi berbeda
- Melihat data flow dinamis dari multiple scenarios

### **[DRAFT]** Instructor Setup TODO:
- [ ] Create shared Google Sheet "Lead Database" dengan kolom: Nama, Email, Status, Source
- [ ] Test Slack channel notification dengan dynamic content
- [ ] Prepare sample lead data dengan berbagai status
- [ ] Setup demo untuk 2 trigger scenarios

### **[DRAFT]** Enhanced Demo Flow:
Instruktur demonstrasikan **2 skenario trigger**:

**Skenario 1: New Lead**
1. Tambahkan baris baru di Google Sheets (Lead baru)
2. Lihat notifikasi "New Lead Added" di Slack

**Skenario 2: Status Update**
1. Update kolom "Status" dari "Cold" ke "Hot" pada existing lead
2. Lihat notifikasi "Lead Status Changed" di Slack

**Key Learning**: Satu workflow bisa handle multiple types of changes!

---

## Workflow 3: Advanced - "Otomatisasi Follow-Up Pasca-Meeting" [DRAFT]

### Business Scenario
**Problem**: Sales team lupa follow-up setelah meeting dengan prospek, dan status di database tidak ter-update
**Solution**: Otomatisasi follow-up email dan update database status setelah meeting selesai

### Workflow Design (4 nodes)
```
Google Calendar Trigger → Google Sheets (Search Row) → Gmail (Send Follow-up) → Google Sheets (Update Row)
```

### **[DRAFT]** Advanced Learning Concepts:
- **Data Search**: Mencari row berdasarkan meeting attendee
- **Conditional Processing**: Kirim follow-up hanya untuk meeting tertentu
- **Data Update**: Update status database setelah action completed
- **Full Automation Cycle**: Dari trigger sampai database update

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Google Calendar dengan meeting yang include email attendee
- [ ] Create Google Sheets "Prospek Database" dengan kolom: Email, Nama, Status, Last Contact
- [ ] Configure Gmail follow-up template dengan personal touch
- [ ] Test pencarian row berdasarkan attendee email
- [ ] Test update status menjadi "Followed Up" after email sent

### **[DRAFT]** "Aha! Moment" Demo Flow:
1. **Show Meeting End**: Tunjukkan meeting di Google Calendar yang baru selesai
2. **Data Search in Action**: Lihat N8N mencari attendee di Google Sheets database
3. **Personalized Follow-up**: Email follow-up otomatis terkirim dengan data dari sheets
4. **Database Update**: **MOMENT PUNCAK** - Status di Google Sheets berubah otomatis menjadi "Followed Up"
5. **Business Impact**: "Sales tidak pernah lupa follow-up, database selalu update"

---

## **[DRAFT]** Pre-Workshop Setup Checklist

### Credentials & Permissions:
- [ ] Gmail account dengan app password
- [ ] Google Forms access (same Google account)
- [ ] Slack workspace dan bot permissions
- [ ] Google Sheets API access
- [ ] Google Calendar API access

### Test Data Preparation:
- [ ] Google Form dengan sample customer inquiries (5-10 variations)
- [ ] Lead database dengan realistic business data dan status variety
- [ ] Calendar events dengan attendee emails yang match database
- [ ] Prospek database dengan email yang match calendar attendees
- [ ] Backup sample data kalau live demo gagal

### Technical Setup:
- [ ] N8N instance ready dengan semua nodes installed
- [ ] Internet connection stable
- [ ] Backup presentation slides
- [ ] Screen sharing setup tested

---

## **[DRAFT]** Demo Presentation Flow

### Opening (5 mins):
- Business pain points introduction
- "Before N8N vs After N8N" comparison
- Set expectation: "Anda akan lihat automation bekerja live"

### Workflow Demo 1 (8 mins):
- Show Google Forms to multi-platform automation
- Highlight structured data flow dan multiple integrations
- Emphasis pada immediate customer response value

### Workflow Demo 2 (7 mins):
- Demonstrate dynamic trigger concepts (new vs update)
- Show real-time notification scenarios
- Connect konsep ke business operations

### Workflow Demo 3 (10 mins):
- Advanced data search and update demonstration
- Build ke "Aha! moment" dengan database update
- Showcase full automation cycle untuk business impact

---

## **[DRAFT]** Troubleshooting Common Issues

### Technical Issues:
- **API rate limits**: Use pinned data untuk backup demo
- **Connection failures**: Have screenshots ready
- **Slow internet**: Pre-record critical demo parts

### Audience Engagement:
- **"Too technical"**: Always relate back to business impact
- **"Too simple"**: Show expansion possibilities
- **"Won't work for my business"**: Prepare industry-specific examples

### Q&A Preparation:
- Security concerns → Self-hosted explanation
- Cost questions → ROI calculation examples
- Scalability → Enterprise features overview

---

## **[DRAFT]** Success Metrics

### Immediate (During Workshop):
- [ ] Students complete basic workflow
- [ ] At least 80% understand trigger concepts
- [ ] Active participation dalam expansion exercises

### Follow-up (Post Workshop):
- [ ] Students implement workflow untuk actual business use case
- [ ] Requests untuk advanced workshops
- [ ] Business adoption rate tracking