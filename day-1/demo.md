# Day-1 Demo Instructor Guide

## Overview
Panduan ini berisi 3 workflow demo yang dirancang untuk target audience business professionals yang belum pernah coding. Setiap workflow memiliki tingkat kompleksitas berbeda untuk tujuan pembelajaran yang spesifik.

---

## Workflow 1: Minor Complexity - "Customer Support Automation" [DRAFT]

### Business Scenario
**Problem**: Customer service team kewalahan dengan pertanyaan yang masuk via berbagai channel
**Solution**: Otomatisasi kategorisasi dan routing pertanyaan customer

### Workflow Design (5-6 nodes)
```
Telegram Trigger → IF Node (Categorize) → Split into:
├── Gmail (Urgent Issues → Manager)
├── Slack (General → Support Team)
└── Google Sheets (Log All Issues)
```

### **[DRAFT]** Wow Factor Elements:
- **Smart categorization** berdasarkan keyword
- **Multiple outputs** dari satu input
- **Real-time notifications** ke berbagai platform
- **Automatic logging** untuk reporting

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Telegram bot untuk demo
- [ ] Prepare sample customer messages (urgent vs general)
- [ ] Test Gmail, Slack, Google Sheets connections
- [ ] Create simple keyword categorization rules

### **[DRAFT]** Expected Demo Flow:
1. Show incoming customer message di Telegram
2. Demonstrate automatic categorization
3. Show different routing based on urgency
4. Highlight business value: "Tim support jadi lebih efisien"

---

## Workflow 2: Minimum Complexity - "Lead Capture" [DRAFT]

### Business Scenario
**Problem**: Sales team manual copy-paste lead dari berbagai sumber
**Solution**: Otomatisasi capture dan notification lead baru

### Workflow Design (3 nodes)
```
Google Sheets Trigger → Gmail (Welcome Email) → Slack (Notify Sales Team)
```

### **[DRAFT]** Instructor Expansion Ideas:
- Add more notification channels (WhatsApp, Discord)
- Add data validation (email format check)
- Add lead scoring based on company size
- Add CRM integration (HubSpot, Salesforce)

### **[DRAFT]** Instructor Setup TODO:
- [ ] Create shared Google Sheet "Lead Database"
- [ ] Setup Gmail template untuk welcome email
- [ ] Test Slack channel notification
- [ ] Prepare sample lead data for live demo

### **[DRAFT]** Hands-on Expansion Session:
Instruktur bisa live expand workflow ini dengan:
1. **Add SMS node** untuk urgent leads
2. **Add conditional logic** berdasarkan lead source
3. **Add data enrichment** via API

---

## Workflow 3: Student Base - "Event Reminder" [DRAFT]

### Business Scenario
**Problem**: Meeting organizer lupa kirim reminder
**Solution**: Otomatisasi reminder sebelum meeting

### Workflow Design (2 nodes)
```
Google Calendar Trigger → Gmail (Send Reminder)
```

### **[DRAFT]** Student Expansion Ideas:
- Add SMS reminder untuk VIP attendees
- Add Slack notification ke team channel
- Add Zoom link preparation
- Add attendee RSVP tracking
- Add post-meeting follow-up survey

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup test Google Calendar dengan sample events
- [ ] Create email reminder template
- [ ] Test calendar trigger timing (15 mins before)
- [ ] Prepare expansion challenges untuk students

### **[DRAFT]** Student Exercise Structure:
1. **Base**: Students implement basic calendar → email
2. **Challenge 1**: Add second notification channel
3. **Challenge 2**: Add conditional logic (VIP vs regular)
4. **Challenge 3**: Add pre/post meeting automation

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