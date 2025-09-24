# Day-2 Demo Instructor Guide

## Overview
Panduan demo untuk Day 2 dengan fokus progressive complexity: Basic Data Flow → Multi-Node Processing → AI-Enhanced Automation. Setiap demo menunjukkan konsep yang berbeda dengan business value yang jelas.

---

## Demo 1: Basic Data Flow - "Customer Inquiry with Simple Branching" [DRAFT]

### **Available N8N Workflow:**
**"Customer Inquiry Branching - Day 2 Demo 1"** (ID: YHpBDgcGfc6HSSlo)

### Learning Objective
Mengenalkan konsep **data flow** dan **branching** dengan IF Node sederhana

### Business Scenario
**Problem**: Customer inquiry via form perlu response yang berbeda based on urgency level
**Solution**: Otomatisasi branching berdasarkan priority selection untuk handling yang tepat

### Workflow Design (5 nodes)
```
N8N Form Trigger (Priority Inquiry) → IF Node (Check "urgent") → Branch:
├── TRUE: Gmail (URGENT Template) → Telegram (Immediate Alert)
└── FALSE: Gmail (Standard Template) → Google Sheets (Log Only)
```

**Key Innovation**: Menggunakan **N8N Form Trigger** dengan built-in priority selector untuk demo yang lebih interactive.

### **[DRAFT]** Key Teaching Points:
- **Conditional Logic**: IF node sebagai decision maker dalam workflow
- **Branching Paths**: Satu input menghasilkan aksi berbeda berdasarkan kondisi
- **Priority-based Processing**: Business logic untuk urgent vs standard handling
- **Visual Flow Design**: Easy untuk understand dan modify business rules
- **Dual Email Templates**: Different messaging untuk different urgency levels

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Gmail credentials untuk automated email responses
- [ ] Configure Telegram bot untuk urgent alerts: URGENT_TELEGRAM_CHAT_ID
- [ ] Create Google Sheets untuk standard inquiry logging: STANDARD_INQUIRY_SHEETS_ID
- [ ] Test both priority paths: urgent dan standard responses
- [ ] Prepare sample data untuk realistic demo scenarios

### **[DRAFT]** Enhanced Demo Flow (8 mins):

**Step 1: Business Context Setup** (2 mins)
- Explain customer service priority handling challenge
- Show N8N form interface dengan priority selector
- Highlight business need untuk different response levels

**Step 2: Standard Priority Demo** (2.5 mins)
- Submit form dengan "No - Standard priority"
- Show standard email template execution
- Demonstrate Google Sheets logging
- Highlight 24-hour SLA messaging

**Step 3: Urgent Priority Demo** (2.5 mins)
- Submit form dengan "Yes - Need immediate response"
- Show URGENT email template dengan red styling
- Demonstrate immediate Telegram alert dengan escalation
- Highlight 15-minute SLA dan supervisor notification

**Step 4: Business Value Highlight** (1 min)
- **Automatic Prioritization**: No manual sorting needed
- **Appropriate Response**: Customers get right level of attention
- **Team Efficiency**: Urgent issues get immediate attention
- **Clear SLA Management**: Different expectations untuk different priorities

**Environment Variables Needed:**
- `URGENT_TELEGRAM_CHAT_ID`: Urgent escalation chat
- `STANDARD_INQUIRY_SHEETS_ID`: Standard inquiry tracking spreadsheet

**Demo Features:**
- **Visual priority differentiation** dengan color-coded emails
- **Indonesian language templates** untuk local audience
- **Realistic SLA messaging** (15 min urgent, 24 hour standard)
- **Supervisor escalation simulation** via Telegram mentions

---

## Demo 2: Multi-Node Processing - "Lead Processing Showcase" [DRAFT]

### Learning Objective
Demonstrasi **multiple node categories** bekerja bersama dalam satu workflow

### Business Scenario
**Problem**: Lead baru dari website butuh processing comprehensive
**Solution**: Multi-step automation dengan berbagai jenis node

### Workflow Design (7 nodes)
```
Google Forms Trigger (New Lead Submission) → Set Node (Format Data) → Wait Node (1 min) →
Gmail (Welcome Email) → Slack (Sales Alert) →
Merge Node (Combine with Historical Data) → Airtable (Update CRM)
```

### **[DRAFT]** Node Categories Showcase:
- **Trigger**: Google Forms (Lead submission)
- **Processing**: Set Node (Data transformation) + Wait Node (Timing)
- **Communication**: Gmail (Email) + Slack (Team notification)
- **Logic**: Merge Node (Data combination)
- **Storage**: Airtable (CRM update)

### **[DRAFT]** Merge Node Deep Dive:
**Concept**: Merge Node menggabungkan data dari multiple sources dalam satu workflow

**Business Use Case**:
- **Problem**: Lead baru masuk, tapi tidak ada context tentang interaction history
- **Solution**: Merge new lead data dengan historical customer data

**How it Works**:
1. **Input A (New Lead)**: Nama, Email, Company, Source dari Google Sheets
2. **Input B (Historical Data)**: Previous interactions, last contact, preferences dari Airtable
3. **Merge Key**: Email address untuk match records
4. **Output**: Enriched lead profile dengan complete context

**Business Value**:
- **Personalized communication**: Email tidak generic, tapi contextual
- **Better conversion**: Sales team tahu approach yang tepat
- **Avoid duplication**: Tidak treat returning customer sebagai cold lead

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup Google Sheets "Lead Database" dengan sample data
- [ ] Configure Set Node untuk format nama: "Firstname Lastname"
- [ ] Set Wait Node untuk 1 minute (demo-friendly timing)
- [ ] Create welcome email template dengan merge fields
- [ ] Setup Slack channel untuk sales notifications
- [ ] Prepare Airtable base dengan lead fields
- [ ] **Setup Merge Node data sources:**
  - [ ] Create historical lead data di Airtable dengan previous interactions (nama, email, last_contact_date, interaction_type, notes)
  - [ ] Test merge functionality: new lead + historical data
  - [ ] Configure merge key (email field) untuk match records
  - [ ] Prepare demo scenario: lead yang sudah pernah contact vs lead baru pertama kali

### **[DRAFT]** Demo Flow (10 mins):
1. **Node category overview** (2 mins): Jelaskan 5 kategori node yang akan terlihat
2. **Trigger execution** (1 min): Add new lead di Google Sheets
3. **Data transformation** (2 mins): Tunjukkan Set Node memformat data
4. **Wait demonstration** (1 min): Jelaskan Wait Node dan lihat countdown
5. **Multi-output execution** (3 mins): Gmail + Slack berjalan parallel
6. **Merge Node demonstration** (1 min):
   - **Show 2 input sources**:
     * Input A: New lead dari Google Sheets (nama: "John Doe", email: "john@company.com")
     * Input B: Historical data dari Airtable (same email, previous interaction: "Demo request 2 months ago")
   - **Live merge process**: Tunjukkan N8N matching records by email
   - **Combined output**: Complete profile dengan interaction history
   - **Business impact**: "Welcome email jadi personal: 'Great to hear from you again, John!'"

---

## Demo 3: AI-Enhanced Automation - "Smart Customer Support" [DRAFT]

### Learning Objective
Menunjukkan **AI/LLM integration** untuk decision making yang intelligent

### Business Scenario
**Problem**: Customer support emails perlu kategorisasi dan response yang smart
**Solution**: AI menganalisa email dan menentukan routing + response otomatis

### Workflow Design (6 nodes)
```
Email Trigger (support@) → OpenAI Node (Analyze Email) →
Set Node (Parse AI Response) → Switch Node (Route by Category) → Branch:
├── Technical: Slack (Tech Team) + Gmail (Technical Response)
├── Billing: Slack (Finance Team) + Gmail (Billing Response)
└── General: Slack (Support Team) + Gmail (General Response)
```

### **[DRAFT]** AI Enhancement Points:
- **Intelligent analysis**: AI understands context vs keyword matching
- **Dynamic categorization**: Flexible categories vs fixed rules
- **Natural language**: AI generates appropriate responses
- **Learning capability**: Better over time vs static rules

### **[DRAFT]** Instructor Setup TODO:
- [ ] Setup email trigger untuk support@ address
- [ ] Configure OpenAI node dengan analysis prompt:
  ```
  Analyze this customer email and return JSON:
  {
    "category": "technical|billing|general",
    "urgency": "high|medium|low",
    "sentiment": "positive|neutral|negative",
    "summary": "brief summary"
  }
  ```
- [ ] Setup Switch Node dengan 3 paths berdasarkan AI category
- [ ] Create response templates untuk each category
- [ ] Configure Slack channels untuk different teams
- [ ] Prepare sample emails: technical issue, billing question, general inquiry

### **[DRAFT]** Demo Flow (12 mins):
1. **AI concept introduction** (2 mins): Manual vs Rule-based vs AI comparison
2. **Workflow overview** (2 mins): Show AI-powered decision flow
3. **Technical email demo** (3 mins): Send technical email, lihat AI analysis
4. **Billing email demo** (3 mins): Send billing email, bandingkan AI response
5. **AI advantages highlight** (2 mins): Flexibility, accuracy, natural language

---

## **[DRAFT]** Pre-Demo Setup Checklist

### Credentials Required:
- [ ] Gmail account dengan app password untuk email automation
- [ ] Google Forms + Sheets access (same account)
- [ ] Slack workspace dengan 3 channels: urgent, sales, tech, finance
- [ ] OpenAI API key dengan sufficient credits
- [ ] Airtable account dengan sample base

### Technical Preparation:
- [ ] 3 separate N8N workflows ready dan tested
- [ ] All credentials configured dan tested
- [ ] Sample data prepared untuk each demo
- [ ] Backup screenshots jika live demo gagal
- [ ] Screen sharing optimal untuk audience visibility

### Data Preparation:
- [ ] Google Form dengan realistic customer inquiry samples
- [ ] Google Sheets dengan 5-10 sample leads
- [ ] Sample customer emails untuk AI analysis (technical, billing, general)
- [ ] Airtable base dengan historical lead data
- [ ] Slack channels dengan clear naming (demo-urgent, demo-sales, etc.)

---

## **[DRAFT]** Demo Presentation Flow (30 mins total)

### Opening (3 mins):
- Recap Day 1 learning (basic triggers & actions)
- Introduce Day 2 focus: data flow, multiple nodes, AI
- Set expectation: "Progressive complexity, real business impact"

### Demo 1: Basic Branching (8 mins):
- Introduce data flow concept
- Show simple IF node decision making
- Demonstrate different paths dari same input
- Emphasize business logic importance

### Demo 2: Multi-Node Power (10 mins):
- Showcase node category diversity
- Demonstrate timing dengan Wait node
- Show parallel execution (Gmail + Slack)
- Highlight data transformation dan merging

### Demo 3: AI Intelligence (12 mins):
- Compare rule-based vs AI-based automation
- Show AI understanding context
- Demonstrate dynamic decision making
- Emphasize future-ready automation

### Closing (2 mins):
- Recap 3 levels: Basic → Multi → AI
- Connect ke business transformation potential
- Transition ke hands-on practice

---

## **[DRAFT]** Troubleshooting & Backup Plans

### Technical Issues:
- **OpenAI API failure**: Use pre-recorded AI responses atau screenshot
- **Email delays**: Use pinned data untuk immediate results
- **Slack rate limits**: Prepare alternative notification channels
- **Internet slow**: Pre-load workflows dan use local examples

### Audience Engagement:
- **"Too complex"**: Always return ke business value explanation
- **"AI scary"**: Position as assistant, not replacement
- **"How much cost"**: Prepare ROI calculation examples
- **"Security concerns"**: Explain self-hosted options

### Demo Pace Management:
- **Running behind**: Skip detailed technical explanation, focus on results
- **Ahead of schedule**: Add more interaction dengan audience questions
- **Technical failure**: Switch ke backup screenshots dan continue teaching

---

## **[DRAFT]** Learning Assessment

### Immediate Indicators (During Demo):
- [ ] Audience can explain data flow concept
- [ ] Clear understanding branching vs linear workflow
- [ ] Recognition of different node categories
- [ ] Appreciation for AI enhancement possibilities

### Follow-up Validation:
- [ ] Students can identify appropriate workflow for business scenarios
- [ ] Understanding when to use AI vs rule-based logic
- [ ] Ability to plan multi-node workflows
- [ ] Questions about implementing similar automation di their business

---

## **[DRAFT]** Business Impact Messaging

### Demo 1 Takeaway:
"Smart routing berdasarkan content data = Customer satisfaction + Team efficiency"

### Demo 2 Takeaway:
"Multiple systems bekerja bersama otomatis = Massive time savings + Zero manual errors"

### Demo 3 Takeaway:
"AI-powered decisions = Human-level intelligence dengan machine speed + consistency"

### Overall Message:
"N8N bukan just automation - tapi intelligent business process optimization!"