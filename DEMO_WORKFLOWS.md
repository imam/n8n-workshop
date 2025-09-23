# Demo Workflows untuk N8N Tutorial

## Filosofi: Show, Don't Tell 🎬

Peserta akan melihat langsung N8N bekerja dengan skenario bisnis real, bukan hanya teori. Setiap demo workflow dapat dijalankan live dan peserta bisa melihat data mengalir real-time.

---

## 📋 DEMO WORKFLOW LIST

### 🚀 DAY 1: TRIGGER-FOCUSED DEMOS

#### 1. Google Sheets Trigger Demo
**Skenario**: Customer Feedback Processor
**Real Business Context**: Restaurant punya form feedback di Google Forms → Data masuk ke Sheets → N8N ambil dan proses

**Live Demo Flow**:
1. **Show Google Sheets** dengan data feedback real (rating 1-5, comments)
2. **Add new row live** saat presentasi
3. **N8N instantly triggered** → Show execution real-time
4. **Result**: Slack notification + email ke manager untuk rating < 3

**Data Sample**:
```
Nama: John Doe
Rating: 2
Komentar: "Makanan dingin, service lambat"
Tanggal: 2024-01-15
```

**Business Impact**: Manager langsung tahu ada masalah, bisa respond cepat!

---

#### 2. Telegram Trigger Demo
**Skenario**: Customer Order via Telegram Bot
**Real Business Context**: Warung kopi punya bot Telegram untuk order → Customer ketik order → Otomatis jadi invoice

**Live Demo Flow**:
1. **Show Telegram bot** di grup demo
2. **Type order message**: "/order 2 cappuccino, 1 croissant"
3. **N8N instantly processes** → Parse text, calculate total
4. **Result**: Reply dengan invoice + forward ke POS system

**Data Flow Demo**:
```
Input: "/order 2 cappuccino, 1 croissant"
↓
Parse: qty=2, item=cappuccino, qty=1, item=croissant
↓
Calculate: 2×25k + 1×15k = 65k
↓
Output: "Invoice #001: Total Rp65,000"
```

**Business Impact**: Zero manual input, customer langsung dapat konfirmasi!

---

#### 3. Google Calendar Trigger Demo
**Skenario**: Meeting Reminder Automation
**Real Business Context**: Sales manager punya banyak client meeting → Auto-reminder + prep meeting notes

**Live Demo Flow**:
1. **Show Google Calendar** dengan meeting hari ini
2. **Create new meeting** 5 menit dari sekarang
3. **N8N triggers 3 menit before meeting**
4. **Result**: WhatsApp reminder + email dengan client profile dari CRM

**Real-time Experience**: Peserta akan lihat WhatsApp message masuk saat demo!

---

### 🔄 DAY 2: DATA FLOW & BRANCHING DEMOS

#### 4. Smart Lead Scoring Demo
**Skenario**: Lead Quality Assessment
**Real Business Context**: Startup SaaS terima banyak trial signup → Perlu qualify mana yang potential customer

**Live Demo Flow**:
1. **Form submission** dengan data lead real
2. **Data transformation** → Score calculation live
3. **Branching decision** based on score
4. **Different actions** untuk hot/warm/cold leads

**Data Sample**:
```
Company: "PT Teknologi Maju"
Employees: "500+"
Budget: "$10,000+"
Timeline: "Immediate"
→ Score: 9/10 → Hot Lead → Assign senior sales
```

---

#### 5. Customer Support Routing Demo
**Skenario**: Smart Ticket Routing
**Real Business Context**: E-commerce platform dengan berbagai jenis komplain → Route ke team yang tepat

**Live Demo Flow**:
1. **Send email** ke support@demo.com
2. **AI analyzes** content real-time
3. **Smart routing** berdasarkan analysis
4. **Different outcomes** untuk billing/technical/general

**Real Email Examples**:
- "Saya belum terima refund untuk order #12345" → Billing team
- "Website error saat checkout" → Technical team
- "Kapan ada promo lagi?" → Marketing team

---

### 🤖 DAY 2: AI INTEGRATION DEMOS

#### 6. AI Email Classification Demo
**Skenario**: Smart Email Processing
**Real Business Context**: CEO startup dapat 50+ email per hari → AI classify urgent vs non-urgent

**Live Demo Flow**:
1. **Send demo emails** dengan tingkat urgency berbeda
2. **AI processing** live classification
3. **Smart actions** based on AI result
4. **Dashboard update** dengan summary

**Email Examples**:
```
Subject: "URGENT: Server down, customers complaining"
→ AI: "High urgency, technical issue"
→ Action: Immediate Slack alert + SMS to CTO

Subject: "Monthly newsletter ideas"
→ AI: "Low urgency, content planning"
→ Action: Add to content planning board
```

---

### 🏪 DAY 2: E-COMMERCE COMPREHENSIVE DEMO

#### 7. Complete Order Processing Demo
**Skenario**: End-to-end E-commerce Automation
**Real Business Context**: Online shop dari order masuk sampai fulfillment

**Live Demo Flow** (10-minute journey):
1. **Customer places order** via demo website
2. **Email parsing** + data extraction
3. **Inventory check** against Google Sheets
4. **Payment verification** simulation
5. **Fulfillment routing** berdasarkan location
6. **Customer communication** automated
7. **Team notifications** dengan smart summaries

**Real Business Impact**: 15-minute manual process → 30-second automation!

---

## 🎯 DEMO PREPARATION GUIDELINES

### Pre-Demo Setup:
1. **Data sudah ready** - Jangan buat data di depan peserta
2. **Workflows tested** - Sudah ditest sebelumnya
3. **Backup plan** - Kalau demo fail, ada video backup
4. **Real accounts** - Pakai Slack/email/WhatsApp yang beneran
5. **Mobile ready** - Peserta bisa lihat notifikasi di HP mereka

### During Demo:
1. **Narrate what's happening** - "Sekarang N8N sedang parse email..."
2. **Show the data flow** - Buka tab Data di setiap node
3. **Highlight business value** - "Ini menghemat 2 jam kerja per hari"
4. **Invite participation** - "Siapa mau coba kirim message ke bot?"
5. **Handle failures gracefully** - "Ini contoh bagus untuk troubleshooting!"

### Post-Demo:
1. **Share workflow template** - Export dan share ke peserta
2. **Q&A focused** - Answer questions about what they just saw
3. **Next steps clear** - "Sekarang kita akan build yang serupa"

---

## 📱 INTERACTIVE DEMO IDEAS

### Audience Participation:
1. **Live Polling** - "Kirim emoji reaction kalau kalian dapat notifikasi"
2. **Real-time Chat** - Telegram grup demo dimana peserta bisa coba
3. **Form Submission** - Peserta submit data, lihat hasilnya langsung
4. **Mobile Notifications** - Peserta join WhatsApp grup demo

### "Behind the Scenes" Showing:
1. **Error simulation** - Show what happens when things go wrong
2. **Data inspection** - Deep dive ke JSON structure
3. **Performance monitoring** - Show execution times
4. **Cost calculation** - "Demo ini cost $0.02 untuk AI processing"

---

## 🔧 TECHNICAL DEMO SETUP

### Required Accounts:
- [ ] Google Workspace (Sheets, Calendar, Gmail)
- [ ] Slack workspace untuk demo
- [ ] Telegram bot dengan demo grup
- [ ] WhatsApp Business account
- [ ] OpenAI API dengan credits
- [ ] Demo domain dengan forms
- [ ] Airtable dengan sample data

### Demo Environment:
- [ ] N8N instance dengan workflows ready
- [ ] Projector-friendly UI (zoom, high contrast)
- [ ] Mobile device untuk show notifications
- [ ] Stable internet connection
- [ ] Backup internet (mobile hotspot)

### Workflow Templates Ready:
- [ ] Basic trigger demos (copy-paste ready)
- [ ] Branching logic demos
- [ ] AI integration demos
- [ ] Complex e-commerce demo
- [ ] Error handling demos

---

## 💡 DEMO ENHANCEMENT IDEAS

### Visual Appeal:
1. **Custom node icons** untuk brand consistency
2. **Color coding** untuk different types of data
3. **Annotations** di workflow canvas
4. **Progress indicators** untuk long-running demos

### Storytelling Elements:
1. **Character personas** - "Meet Sarah, restaurant owner..."
2. **Problem setup** - "Sarah spends 2 hours daily processing feedback"
3. **Solution reveal** - "With N8N, it's automated in 30 seconds"
4. **Impact measurement** - "Sarah saves 10 hours per week"

### Gamification:
1. **Demo challenges** - "Who can guess what happens next?"
2. **Speed contests** - "Let's see how fast this processes 100 orders"
3. **Before/after comparisons** - Manual vs automated side-by-side
4. **ROI calculator** - Real numbers pada demo

---

## 📊 SUCCESS METRICS FOR DEMOS

### Engagement Metrics:
- [ ] Peserta aktif bertanya selama demo
- [ ] Requests untuk repeat certain parts
- [ ] Mobile devices keluar untuk test notifications
- [ ] Note-taking activity increases

### Learning Metrics:
- [ ] Peserta bisa predict next step in workflow
- [ ] Questions shift from "what" to "how can I..."
- [ ] Requests for specific business use cases
- [ ] Post-demo hands-on participation

### Business Relevance:
- [ ] "Aha moments" ketika see business value
- [ ] Discussions about specific company use cases
- [ ] Questions about ROI and implementation
- [ ] Requests for custom demos

---

**Remember**: Demo yang baik membuat peserta berkata "I need this for my business!" bukan "That's cool technology."