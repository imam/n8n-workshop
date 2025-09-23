# Day-1 Demo Instructor Guide

## Overview
Panduan ini berisi 3 workflow demo yang dirancang untuk target audience business professionals yang belum pernah coding. Setiap workflow memiliki tingkat kompleksitas berbeda untuk tujuan pembelajaran yang spesifik.

---

## Workflow 1: Minor Complexity - "Customer Support Automation" [DRAFT]

### Business Scenario
**Problem**: Customer service team kewalahan dengan pertanyaan yang masuk via berbagai channel
**Solution**: Otomatisasi capture dan routing pertanyaan customer

### Workflow Design (4 nodes)
```
Telegram Trigger → Google Sheets (Log) → Gmail (Auto Reply) → Slack (Notify Team)
```

### **[DRAFT]** Wow Factor Elements:
- **Multiple outputs** dari satu input
- **Real-time notifications** ke berbagai platform
- **Automatic logging** untuk reporting
- **Instant auto-reply** ke customer

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Telegram bot untuk demo
- [ ] Prepare sample customer messages
- [ ] Test Gmail, Slack, Google Sheets connections
- [ ] Create auto-reply email template

### **[DRAFT]** Expected Demo Flow:
1. Show incoming customer message di Telegram
2. Demonstrate data tersimpan di Google Sheets
3. Show auto-reply email terkirim ke customer
4. Show notifikasi tim di Slack
5. Highlight business value: "Tim support jadi lebih efisien"

---

## Workflow 2: Basic Notification - "New Lead Alert" [DRAFT]

### Business Scenario
**Problem**: Sales team kesulitan tracking lead baru
**Solution**: Otomatisasi notifikasi lead pertama

### Workflow Design (2 nodes)
```
Google Sheets Trigger → Slack (Notify Sales Team)
```

### **[DRAFT]** Learning Objectives:
- Memahami trigger sederhana
- Menghubungkan dua aplikasi berbeda
- Melihat data flow dasar

### **[DRAFT]** Instructor Setup TODO:
- [ ] Create shared Google Sheet "Lead Database"
- [ ] Test Slack channel notification
- [ ] Prepare sample lead data for demo

### **[DRAFT]** Hands-on Exploration:
Instruktur bisa demonstrasikan:
1. Input data manual di Google Sheets
2. Lihat notifikasi otomatis di Slack
3. Diskusikan potensi business value

---

## Workflow 3: Simple Automation - "Calendar Reminder" [DRAFT]

### Business Scenario
**Problem**: Sering lupa kirim reminder meeting
**Solution**: Otomatisasi pengingat sederhana

### Workflow Design (2 nodes)
```
Google Calendar Trigger → Gmail (Send Reminder)
```

### **[DRAFT]** Basic Automation Concept:
- Trigger otomatis dari kalender
- Kirim email reminder tanpa manual
- Hemat waktu admin meeting

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup test Google Calendar dengan sample events
- [ ] Buat template email reminder
- [ ] Test trigger timing
- [ ] Siapkan contoh skenario praktis

### **[DRAFT]** Simple Learning Path:
1. **Base**: Trigger dari kalender ke email
2. **Diskusi**: Potensi otomatisasi meeting

---

## **[DRAFT]** Pre-Workshop Setup Checklist

### Credentials & Permissions:
- [ ] Gmail account dengan app password
- [ ] Telegram bot token
- [ ] Slack workspace dan bot permissions
- [ ] Google Sheets API access
- [ ] Google Calendar API access

### Test Data Preparation:
- [ ] Sample customer messages (5-10 variations)
- [ ] Lead database dengan realistic business data
- [ ] Test calendar events dengan different timing
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

### Workflow Demo 1 (10 mins):
- Show complex customer support automation
- Highlight multiple integrations
- Emphasis pada business value dan time savings

### Workflow Demo 2 (5 mins):
- Simple lead capture demonstration
- Show expansion possibilities
- Connect ke hands-on session

### Transition to Hands-on (5 mins):
- Introduce student base workflow
- Set learning objectives
- Distribute exercise materials

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