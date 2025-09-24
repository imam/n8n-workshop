# Day-1 Demo Instructor Guide

## Overview
Panduan ini berisi 3 workflow demo yang dirancang untuk target audience business professionals yang belum pernah coding. Setiap workflow memiliki tingkat kompleksitas berbeda untuk tujuan pembelajaran yang spesifik.

---

## Workflow 1: Minor Complexity - "Customer Support Automation" [DRAFT]

### Business Scenario
**Problem**: Customer service team kewalahan dengan pertanyaan yang masuk via website contact form
**Solution**: Otomatisasi capture dan routing pertanyaan customer dari form submission

### **Available N8N Workflows:**
1. **"Customer Support Automation - Day 1 Demo"** (ID: XTwQsELGf3AYijvG) - **Parallel Flow**
2. **"Customer Support Automation - Serial Flow"** (ID: 4M4G3kul340BcTCT) - **Sequential Flow**

### Workflow Design (4 nodes)
**Parallel Version:**
```
N8N Form Trigger → [Google Sheets + Gmail + Telegram] (simultaneous)
```

**Serial Version:**
```
N8N Form Trigger → Google Sheets → Gmail → Telegram (sequential)
```

### **[DRAFT]** Wow Factor Elements:
- **Built-in form generation** dengan N8N Form Trigger (no external Google Forms needed)
- **Parallel vs Serial execution** comparison untuk business understanding
- **Real-time notifications** ke Telegram (lebih mudah setup dari Slack)
- **Automatic logging** untuk reporting di Google Sheets
- **Personalized auto-reply** dengan Indonesian language template

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Google Sheets dengan columns: Timestamp, Nama, Email, Pertanyaan, Kategori
- [ ] Configure Gmail credential untuk auto-reply
- [ ] Setup Telegram bot dan get chat ID
- [ ] Set environment variables: GOOGLE_SHEETS_DOC_ID, TELEGRAM_CHAT_ID
- [ ] Activate workflow dan test dengan sample submission

### **[DRAFT]** Expected Demo Flow:
1. **Show N8N Form interface** - demonstrate built-in form generation capability
2. **Submit test inquiry** - live demo dengan realistic business data
3. **Demonstrate execution difference**:
   - Parallel: Show all actions happening simultaneously
   - Serial: Show step-by-step sequence with status confirmation
4. **Show Google Sheets logging** dengan structured data
5. **Show Gmail auto-reply** dengan personalized Indonesian content
6. **Show Telegram notification** dengan business-friendly formatting
7. **Highlight business value**: "Zero manual work, instant customer response, full tracking"

---

## Workflow 2: Basic Notification - "New Lead Alert" [DRAFT]

### Business Scenario
**Problem**: Sales team kesulitan tracking perubahan status lead secara real-time
**Solution**: Otomatisasi notifikasi untuk lead baru DAN update status existing lead

### **Available N8N Workflow:**
**"New Lead Alert - Day 1 Demo 2"** (ID: kFJzY8RvHZd959bi)

### Workflow Design (2 nodes)
```
Google Sheets Trigger → Telegram (Notify Sales Team)
```

### **[DRAFT]** Learning Objectives:
- Memahami trigger yang responsif terhadap berbagai perubahan data
- Demonstrate simple 2-node automation
- Show real-time data monitoring capabilities
- Business value dari instant notification systems

### **[DRAFT]** Instructor Setup TODO:
- [ ] Create shared Google Sheet "Lead Database" dengan kolom: Timestamp, Nama, Email, Status, Source
- [ ] Configure Google Sheets trigger untuk detect changes
- [ ] Setup Telegram notification dengan dynamic content dari sheet data
- [ ] Prepare sample lead data dengan berbagai status values
- [ ] Test both scenarios: new lead addition dan status updates

### **[DRAFT]** Enhanced Demo Flow:
Instruktur demonstrasikan **2 skenario trigger**:

**Skenario 1: New Lead Addition**
1. **Buka Google Sheets "Lead Database"** - show existing data structure
2. **Add new row** dengan data: Nama, Email, Status="New", Source="Website"
3. **Instant Telegram notification** with "🎉 NEW LEAD ADDED!" message
4. **Show dynamic data** dari sheets muncul di notification

**Skenario 2: Lead Status Update**
1. **Select existing lead** di Google Sheets
2. **Change Status** dari "New" ke "Hot Prospect"
3. **Real-time notification** dengan "🔄 LEAD STATUS UPDATED" message
4. **Demonstrate immediacy** - no delay between change dan notification

**Key Learning Demo Points:**
- **One workflow handles multiple scenarios** (create, update, delete)
- **Real-time monitoring** - no polling delays
- **Dynamic content** based on actual sheet data
- **Business critical notifications** - sales team never misses updates

**Environment Variables Needed:**
- `LEAD_SHEETS_DOC_ID`: Google Sheets document ID
- `SALES_TELEGRAM_CHAT_ID`: Sales team Telegram chat ID

---

## Workflow 3: Advanced - "Otomatisasi Follow-Up Pasca-Meeting" [DRAFT]

### Business Scenario
**Problem**: Sales team lupa follow-up setelah meeting dengan prospek, dan status di database tidak ter-update
**Solution**: Otomatisasi follow-up email dan update database status setelah meeting selesai

### **Available N8N Workflow:**
**"Post-Meeting Follow-Up Automation - Day 1 Demo 3"** (ID: 98WzmS6mMNif2WPl)

### Workflow Design (5 nodes)
```
Google Calendar Trigger → Google Sheets (Read Database) → Code (Process & Match) → Gmail (Follow-up) → Google Sheets (Update Status)
```

### **[DRAFT]** Advanced Learning Concepts:
- **Calendar Event Monitoring**: Automatic trigger when meetings end
- **Data Matching Logic**: Code node untuk match attendee dengan prospect database
- **Conditional Processing**: Only send follow-up for meetings with known prospects
- **Personalized Email Templates**: Dynamic content dengan meeting dan prospect details
- **Database State Management**: Update status tracking dengan timestamp
- **Full Business Process Automation**: End-to-end sales workflow

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Google Calendar dengan meeting events yang include attendee emails
- [ ] Create Google Sheets "Prospect Database" dengan columns: Nama, Email, Status, Last Contact, Updated
- [ ] Configure Gmail credentials untuk automated follow-up emails
- [ ] Populate sample prospect data dengan email addresses
- [ ] Set environment variable: PROSPECT_SHEETS_DOC_ID
- [ ] Test meeting creation dan completion untuk trigger workflow

### **[DRAFT]** "Aha! Moment" Demo Flow:

**Step 1: Setup Demo Context** (2 mins)
1. **Show Prospect Database** di Google Sheets dengan sample data
2. **Show scheduled meeting** di Google Calendar dengan prospect sebagai attendee
3. **Explain business pain point**: "Sales team often forgets follow-up after meetings"

**Step 2: The Magic Happens** (3 mins)
1. **End the meeting** di Google Calendar (simulate meeting completion)
2. **Watch workflow execute** di N8N:
   - Calendar trigger activates automatically
   - Code node matches attendee email dengan prospect database
   - Gmail sends personalized follow-up dengan meeting details
   - Google Sheets updates prospect status to "Followed Up"

**Step 3: Business Impact Demonstration** (3 mins)
1. **Show personalized follow-up email** dengan meeting summary
2. **Show updated prospect status** di Google Sheets dengan timestamp
3. **Highlight business value**:
   - "Zero manual follow-up needed"
   - "Complete audit trail in database"
   - "Personalized touch maintains relationship quality"
   - "Sales team can focus on selling, not administrative tasks"

**Advanced Demo Features:**
- **Indonesian language** follow-up email template
- **Meeting metadata integration** (subject, time, attendees)
- **Smart prospect matching** via Code node
- **Automatic status tracking** dengan timestamp
- **Conditional execution** - only processes meetings with known prospects

**Environment Variables Needed:**
- `PROSPECT_SHEETS_DOC_ID`: Prospect database Google Sheets ID

**Required Credentials:**
- Google Calendar (for meeting monitoring)
- Google Sheets (for prospect database access)
- Gmail (for automated follow-up emails)

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