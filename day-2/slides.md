# N8N Tutorial - Day 2

## Menguasai Node dan Data Flow untuk Automation Bisnis

---

<!-- SECTION 1: Introduction -->
# Selamat Datang di Day 2!

---

## Recap Day 1

![Day 1 Recap](day-2/images/day1-recap.png)
<!-- Placeholder: Visual summary day 1 -->

### Yang Sudah Kita Kuasai:
✅ **Dasar N8N** - Tool automation tanpa coding
✅ **Trigger sederhana** - Google Sheets, Telegram, Calendar
✅ **Koneksi aplikasi** - Menghubungkan tools favorit
✅ **Automation pertama** - Newsletter signup otomatis

---

## Target Day 2

![Day 2 Goals](day-2/images/day2-goals.png)
<!-- Placeholder: Day 2 learning objectives -->

### Setelah sesi ini, Anda akan bisa:
🎯 **Memahami alur data** - Bagaimana informasi mengalir antar aplikasi
🔀 **Membuat percabangan** - Satu input, banyak aksi berbeda
🧰 **Menggunakan node populer** - Tools yang paling sering dipakai bisnis
🤖 **Integrasi AI/LLM** - Membuat automation yang "pintar"

### Business Impact:
💰 Automation yang lebih complex = lebih banyak waktu & uang yang dihemat!

---

<!-- SECTION 2: Data Flow -->
# Memahami Alur Data dalam Automation

---

## Apa itu Data Flow?

![Data Flow Concept](day-2/images/data-flow-concept.png)
<!-- Placeholder: Visual data flow diagram -->

**Data Flow** = Bagaimana informasi berpindah dari satu langkah ke langkah berikutnya

### Analogi Sederhana:
🏭 **Seperti pabrik** - Bahan mentah masuk, diproses, jadi produk jadi
📧 **Contoh**: Email masuk → Ekstrak info penting → Simpan ke database → Kirim notifikasi

---

## Contoh Real: Lead Processing

![Lead Processing Flow](day-2/images/lead-processing-flow.png)
<!-- Placeholder: Screenshot workflow lead processing -->

### Skenario Bisnis:
1. **Customer isi form** → Data: Nama, Email, Perusahaan, Kebutuhan
2. **Scoring otomatis** → Data: Score 1-10 berdasarkan kriteria
3. **Routing berdasarkan score** → Data: High/Medium/Low priority
4. **Assignment ke sales** → Data: Sales person yang tepat
5. **Follow-up reminder** → Data: Jadwal kontak ulang

**Setiap langkah menerima, memproses, dan meneruskan data!**

---

## Melihat Data di N8N

![View Data N8N](day-2/images/view-data-n8n.png)
<!-- Placeholder: Screenshot data view dalam N8N -->

### Cara Mudah Lihat Data:
1. **Klik node** yang sudah dijalankan
2. **Tab "Data"** - Lihat input dan output
3. **Format JSON** - Struktur data yang rapi
4. **Preview** - Data dalam bentuk tabel

### Tips untuk Non-Technical:
- Fokus pada **nilai** bukan struktur
- Cari **field yang Anda butuhkan** (nama, email, dll)
- **Copy data** untuk testing node selanjutnya

---

## Data Transformation

![Data Transformation](day-2/images/data-transformation.png)
<!-- Placeholder: Before/after data transformation -->

### Mengapa Perlu Transform Data?

**Masalah Umum:**
- Aplikasi A pakai format "John Doe", aplikasi B butuh "Doe, John"
- Tanggal dari form: "01/15/2024", CRM butuh: "2024-01-15"
- Nomor telepon: "+62-21-1234567", WhatsApp butuh: "6221234567"

**Solusi N8N:**
🔧 Node khusus untuk mengubah format data
✂️ Ambil sebagian data yang dibutuhkan saja
➕ Gabungkan data dari beberapa sumber

---

## Hands-on: Trace Data Flow

![Trace Data Exercise](day-2/images/trace-data-exercise.png)
<!-- Placeholder: Step-by-step data tracing -->

### Exercise Sederhana:
1. **Buat workflow baru**
2. **Google Sheets trigger** - Baris baru di spreadsheet "Customers"
3. **Lihat data** - Klik node, cek tab Data
4. **Transform data** - Gabungkan nama depan + belakang
5. **Gmail node** - Kirim email dengan data yang sudah diformat

**Goal**: Memahami bagaimana data berubah di setiap step

---

<!-- SECTION 3: Branching -->
# Branching: Satu Input, Banyak Aksi

---

## Apa itu Branching?

![Branching Concept](day-2/images/branching-concept.png)
<!-- Placeholder: Visual branching diagram -->

**Branching** = Membuat keputusan otomatis berdasarkan data

### Analogi Bisnis:
🚦 **Seperti traffic light** - Berdasarkan kondisi, ambil jalur yang berbeda
📋 **Seperti SOP** - "Jika customer VIP, lakukan A. Jika customer biasa, lakukan B"

### Contoh Real:
- **Lead score tinggi** → Langsung assign ke senior sales
- **Lead score rendah** → Masuk ke nurturing campaign
- **Komplain urgent** → Langsung ke manager
- **Komplain biasa** → Ke customer service

---

## IF Node: Decision Maker

![IF Node](day-2/images/if-node.png)
<!-- Placeholder: Screenshot IF node configuration -->

### Cara Kerja IF Node:
1. **Input data** masuk
2. **Cek kondisi** - Apakah sesuai kriteria?
3. **True path** - Jika ya, lakukan ini
4. **False path** - Jika tidak, lakukan itu

### Contoh Kondisi Bisnis:
✅ **Email berisi kata "urgent"** → True
✅ **Order value > 1,000,000** → True
✅ **Customer dari Jakarta** → True
✅ **Jam kerja (9-17)** → True

---

## Switch Node: Multiple Paths

![Switch Node](day-2/images/switch-node.png)
<!-- Placeholder: Screenshot Switch node dengan multiple output -->

### Kapan Pakai Switch Node?

**IF Node** = 2 pilihan (Ya/Tidak)
**Switch Node** = 3+ pilihan (A/B/C/D)

### Contoh Business Case:
📊 **Lead Scoring**:
- Score 80-100 → Hot Lead (assign senior sales)
- Score 60-79 → Warm Lead (assign junior sales)
- Score 40-59 → Cold Lead (email nurturing)
- Score <40 → Archive

🌍 **Geographic Routing**:
- Jakarta → Tim Jakarta
- Surabaya → Tim Surabaya
- Bali → Tim Bali
- Others → Tim Pusat

---

## Contoh Real: Customer Support Routing

![Support Routing](day-2/images/support-routing.png)
<!-- Placeholder: Complex branching workflow untuk customer support -->

### Workflow: Tiket Support Otomatis

1. **Customer kirim email** ke support@company.com
2. **Extract keywords** dari subject & content
3. **Branching berdasarkan kategori**:
   - "billing", "payment" → Finance team
   - "bug", "error", "not working" → Tech team
   - "feature", "request" → Product team
   - "urgent", "down" → Escalate ke manager
4. **Auto-reply** dengan estimasi response time
5. **Create ticket** di sistem tracking
6. **Notify assigned team** via Slack

**Result**: Support ticket terorganisir otomatis tanpa manual sorting!

---

## Hands-on: Build Branching Workflow

![Branching Exercise](day-2/images/branching-exercise.png)
<!-- Placeholder: Exercise workflow diagram -->

### Exercise: Lead Qualification Automation

**Scenario**: Otomatisasi proses kualifikasi lead dari website

**Step-by-step**:
1. **Form Trigger** - Lead dari contact form
2. **IF Node** - Cek apakah company email (bukan Gmail/Yahoo)
3. **IF True**:
   - Calculate lead score berdasarkan company size
   - Switch Node untuk routing ke sales yang tepat
4. **IF False**:
   - Add ke nurturing email list
   - Schedule follow-up dalam 1 minggu

**Business Value**: Lead qualified otomatis, sales fokus ke prospect terbaik!

---

<!-- SECTION 4: Popular Nodes -->
# Node Populer untuk Automation Bisnis

---

## Node Categories untuk Bisnis

![Node Categories](day-2/images/node-categories-business.png)
<!-- Placeholder: Kategorisasi node untuk business use case -->

### 📧 **Communication Nodes**
Gmail, Slack, Telegram, WhatsApp Business

### 📊 **Data & Storage Nodes**
Google Sheets, Airtable, MySQL, Notion

### 🔗 **Integration Nodes**
Zapier, Webhook, HTTP Request, API calls

### 🤖 **AI & Processing Nodes**
OpenAI, Claude, Text processing, Image analysis

### ⏰ **Scheduling & Logic Nodes**
Cron, IF, Switch, Wait, Merge

---

## Communication Nodes

![Communication Nodes](day-2/images/communication-nodes.png)
<!-- Placeholder: Screenshots of communication nodes -->

### Gmail Node
**Use Cases**:
- Send welcome emails to new customers
- Auto-reply to common inquiries
- Forward urgent emails to management
- Bulk email campaigns

**Business Value**: 24/7 email automation, faster response time

### Slack Node
**Use Cases**:
- Notify team about new orders/leads
- Alert on system issues or deadlines
- Share daily reports automatically
- Create channels for new projects

**Business Value**: Real-time team coordination, nothing falls through cracks

---

### Telegram Node
**Use Cases**:
- Customer service bot for basic queries
- Order status updates to customers
- Internal alerts for urgent issues
- Broadcast announcements to subscribers

**Business Value**: Instant communication, reduce manual customer service

### WhatsApp Business Node
**Use Cases**:
- Send order confirmations
- Appointment reminders
- Customer feedback surveys
- Product updates & promotions

**Business Value**: High open rates, direct customer engagement

---

## Data & Storage Nodes

![Data Storage Nodes](day-2/images/data-storage-nodes.png)
<!-- Placeholder: Screenshots of data nodes -->

### Google Sheets Node
**Use Cases**:
- Customer database management
- Sales pipeline tracking
- Inventory monitoring
- Report generation

**Configuration Tips**:
- Use clear column headers
- Set up data validation
- Create separate sheets for different purposes
- Regular backup to avoid data loss

---

### Airtable Node
**Use Cases**:
- CRM with custom fields
- Project management with attachments
- Event planning with linked records
- Product catalog with images

**Why Choose Airtable**:
- More powerful than Sheets
- Database relationships
- Multiple views (calendar, kanban, gallery)
- Better for complex data structures

### Notion Node
**Use Cases**:
- Knowledge base automation
- Task management integration
- Documentation updates
- Team wiki maintenance

---

## Processing & Logic Nodes

![Processing Nodes](day-2/images/processing-nodes.png)
<!-- Placeholder: Screenshots of processing nodes -->

### Set Node
**Purpose**: Transform and clean data
**Use Cases**:
- Rename fields for consistency
- Calculate new values (total, percentage)
- Format dates and phone numbers
- Remove unnecessary data fields

### Function Node
**Purpose**: Custom data processing with JavaScript
**Business Examples**:
- Calculate commission based on sales tiers
- Generate unique order numbers
- Parse and clean imported data
- Custom business logic implementation

---

### Wait Node
**Purpose**: Add delays between actions
**Use Cases**:
- Wait 24 hours before sending follow-up email
- Delay between API calls to avoid rate limits
- Pause workflow for manual approval
- Schedule actions for business hours only

### Merge Node
**Purpose**: Combine data from multiple sources
**Use Cases**:
- Merge customer data with order history
- Combine social media metrics
- Join data from different departments
- Create comprehensive reports

---

## Hands-on: Node Exploration

![Node Exercise](day-2/images/node-exploration-exercise.png)
<!-- Placeholder: Node exploration workflow -->

### Exercise: Multi-Node Customer Onboarding

**Business Scenario**: Comprehensive new customer automation

**Workflow Steps**:
1. **Google Sheets Trigger** - New customer in spreadsheet
2. **Set Node** - Format customer data (name, email, phone)
3. **IF Node** - Check if email is valid format
4. **Gmail Node** - Send personalized welcome email
5. **Wait Node** - Wait 1 day
6. **Slack Node** - Notify sales team about new customer
7. **Airtable Node** - Add to CRM with enriched data
8. **Function Node** - Calculate customer lifetime value prediction

**Business Impact**: Seamless onboarding, no customer falls through gaps!

---

<!-- SECTION 5: LLM Integration -->
# Integrasi AI/LLM untuk Automation Pintar

---

## Mengapa AI dalam Automation?

![AI in Automation](day-2/images/ai-automation-concept.png)
<!-- Placeholder: AI + automation concept visual -->

### Traditional Automation:
🤖 **Rule-based** - Jika A maka B
📋 **Predictable** - Hasil selalu sama
⚙️ **Rigid** - Harus setup untuk setiap skenario

### AI-Powered Automation:
🧠 **Smart decisions** - AI analisa dan putuskan
🎯 **Adaptive** - Belajar dari data dan pola
💬 **Natural language** - Proses teks seperti manusia

**Business Value**: Automation yang lebih fleksibel dan "pintar"

---

## OpenAI Node

![OpenAI Node](day-2/images/openai-node.png)
<!-- Placeholder: Screenshot OpenAI node configuration -->

### Setup OpenAI Node:
1. **Get API Key** dari OpenAI platform
2. **Connect credential** di N8N
3. **Choose model** - GPT-4 untuk quality, GPT-3.5 untuk speed
4. **Set parameters** - temperature, max tokens

### Model Selection:
- **GPT-4** - Lebih pintar, lebih mahal, lebih lambat
- **GPT-3.5-turbo** - Cukup pintar, murah, cepat
- **Text-davinci** - Untuk completion tasks

---

## Business Use Cases untuk LLM

![LLM Business Cases](day-2/images/llm-business-cases.png)
<!-- Placeholder: Various LLM use cases untuk bisnis -->

### 📧 **Email Processing**
- **Classify emails** - urgent, normal, spam
- **Sentiment analysis** - positive, negative, neutral
- **Auto-reply generation** - contextual responses
- **Extract key information** - names, dates, amounts

### 📝 **Content Generation**
- **Product descriptions** from specifications
- **Social media posts** from blog articles
- **Email templates** for different scenarios
- **Translation** to multiple languages

---

### 🎯 **Customer Analysis**
- **Lead scoring** based on communication
- **Customer feedback analysis**
- **Churn prediction** from support tickets
- **Personalized recommendations**

### 📊 **Data Processing**
- **Clean and standardize** inconsistent data
- **Categorize transactions** or expenses
- **Generate insights** from raw data
- **Create summaries** of long documents

---

## Prompt Engineering untuk Bisnis

![Prompt Engineering](day-2/images/prompt-engineering.png)
<!-- Placeholder: Good vs bad prompts examples -->

### Bad Prompt:
```
"Analyze this email"
```

### Good Prompt:
```
You are a customer service AI. Analyze this email and provide:
1. Sentiment (positive/negative/neutral)
2. Urgency level (high/medium/low)
3. Category (billing/technical/general)
4. Suggested response tone (apologetic/helpful/informative)
5. Key action items

Email: [email content]

Format your response as JSON.
```

### Tips untuk Effective Prompts:
✅ **Be specific** about desired output format
✅ **Give context** about your business/role
✅ **Provide examples** of good responses
✅ **Set constraints** (word limit, tone, etc.)

---

## Real Example: Customer Support AI

![Support AI Example](day-2/images/support-ai-example.png)
<!-- Placeholder: Screenshot workflow dengan OpenAI untuk customer support -->

### Workflow: AI-Powered Support Ticket Processing

**Scenario**: Otomatisasi initial processing support emails

1. **Gmail Trigger** - New email ke support@
2. **OpenAI Node** - Analyze email content:
   ```
   Analyze this support email:
   1. Extract customer issue category
   2. Determine urgency (1-5 scale)
   3. Suggest solution or next steps
   4. Identify if escalation needed

   Email: {email_content}
   ```
3. **Switch Node** - Route berdasarkan urgency score
4. **Set Node** - Format hasil AI untuk ticket system
5. **Create ticket** dengan AI insights
6. **Auto-reply** dengan AI-generated response

**Business Impact**: Support tickets diproses lebih cepat dan akurat!

---

## Advanced LLM Techniques

![Advanced LLM](day-2/images/advanced-llm-techniques.png)
<!-- Placeholder: Advanced techniques visualization -->

### Chain of Thought Prompting
**Technique**: Minta AI untuk "berpikir step-by-step"

**Example**:
```
Analyze this sales lead step by step:
1. First, identify the company size indicators
2. Then, assess the decision-making authority
3. Next, evaluate the urgency signals
4. Finally, provide a lead score (1-100) with reasoning

Lead info: [data]
```

### Few-Shot Learning
**Technique**: Berikan contoh untuk guide AI

**Example**:
```
Categorize customer feedback like these examples:

Example 1: "Love the product but shipping was slow" → Category: Shipping, Sentiment: Mixed
Example 2: "Amazing support team, very helpful!" → Category: Support, Sentiment: Positive

Now categorize: "[customer_feedback]"
```

---

## Hands-on: Build AI-Powered Workflow

![AI Workflow Exercise](day-2/images/ai-workflow-exercise.png)
<!-- Placeholder: AI workflow exercise diagram -->

### Exercise: Smart Lead Qualification with AI

**Business Goal**: Qualify inbound leads automatically using AI

**Workflow Steps**:
1. **Form Trigger** - Lead from website contact form
2. **Set Node** - Prepare data for AI analysis
3. **OpenAI Node** - AI lead scoring with prompt:
   ```
   You are a B2B sales AI. Score this lead 1-100 based on:
   - Company size (employees, revenue indicators)
   - Job title (decision maker level)
   - Stated needs (urgency, budget signals)
   - Communication quality

   Lead data: {form_data}

   Provide: Score (1-100), Reasoning (2 sentences), Next Action
   ```
4. **IF Node** - Check if score > 70
5. **High Score Path**: Slack notify sales + schedule call
6. **Low Score Path**: Add to nurturing campaign
7. **Airtable** - Save lead with AI insights

**Business Value**: Only qualified leads go to sales team!

---

<!-- SECTION 6: Hands-on Practice -->
# Latihan Comprehensive: E-commerce Order Processing

---

## Exercise Overview

![Ecommerce Exercise](day-2/images/ecommerce-exercise-overview.png)
<!-- Placeholder: Complete ecommerce workflow diagram -->

### Business Scenario:
**Otomatisasi Komprehensif Order Processing untuk Online Store**

### Current Manual Process:
1. Order masuk via email
2. Manual data entry ke spreadsheet
3. Manual check stock
4. Manual assign ke fulfillment team
5. Manual customer notification
6. Manual tracking update

**Pain Points**: Lambat, error-prone, tidak scalable

---

## Target Automation Workflow

![Target Workflow](day-2/images/target-automation-workflow.png)
<!-- Placeholder: Detailed workflow with all nodes -->

### Automated Process:
1. **Email Trigger** - Order confirmation email
2. **AI Extraction** - Parse order details with OpenAI
3. **Data Validation** - Check completeness & format
4. **Stock Check** - Query inventory database
5. **Smart Routing** - Assign based on location & product type
6. **Customer Communication** - Personalized updates
7. **Team Notification** - Relevant teams get notified
8. **Tracking Setup** - Create tracking records

**Business Impact**: 90% faster processing, zero manual errors!

---

## Step 1: Order Email Processing

![Step 1](day-2/images/exercise-step1-email.png)
<!-- Placeholder: Email processing setup -->

### Setup Email Trigger:
1. **Gmail Trigger** untuk orders@yourstore.com
2. **Filter** - Hanya email dengan subject "New Order"
3. **Test** dengan sample order email

### Extract Order Data with AI:
```javascript
// OpenAI Prompt untuk extract order details
You are an e-commerce order processor. Extract these details from the order email:

Required fields:
- order_id: Order number
- customer_name: Full customer name
- customer_email: Email address
- items: Array of {product_name, quantity, price}
- total_amount: Total order value
- shipping_address: Full address
- payment_method: How customer paid

Email content: {email_body}

Return as valid JSON only.
```

---

## Step 2: Data Validation & Processing

![Step 2](day-2/images/exercise-step2-validation.png)
<!-- Placeholder: Data validation logic -->

### Validation Logic:
1. **Function Node** - Check data completeness:
   ```javascript
   // Validate required fields
   const required = ['order_id', 'customer_email', 'items', 'total_amount'];
   const missing = required.filter(field => !items[0].json[field]);

   if (missing.length > 0) {
     return [{json: {status: 'invalid', missing: missing}}];
   }

   return [{json: {status: 'valid', data: items[0].json}}];
   ```

2. **IF Node** - Branch based on validation result
3. **Invalid Path** - Send alert to admin
4. **Valid Path** - Continue processing

---

## Step 3: Smart Inventory & Routing

![Step 3](day-2/images/exercise-step3-routing.png)
<!-- Placeholder: Smart routing logic -->

### Inventory Check:
1. **Google Sheets Node** - Query inventory spreadsheet
2. **Function Node** - Calculate available stock
3. **IF Node** - Stock sufficient?

### Smart Routing Logic:
```javascript
// Determine fulfillment center based on:
// 1. Customer location
// 2. Product availability
// 3. Shipping speed preference

const shipping_city = data.shipping_address.toLowerCase();
const total_value = parseFloat(data.total_amount);

let fulfillment_center = 'jakarta'; // default

if (shipping_city.includes('surabaya')) {
  fulfillment_center = 'surabaya';
} else if (shipping_city.includes('medan')) {
  fulfillment_center = 'medan';
}

// Express orders go to nearest center
if (data.shipping_method === 'express') {
  fulfillment_center = getNearestCenter(shipping_city);
}

return [{json: {center: fulfillment_center, priority: total_value > 500000 ? 'high' : 'normal'}}];
```

---

## Step 4: Customer & Team Communication

![Step 4](day-2/images/exercise-step4-communication.png)
<!-- Placeholder: Communication flow -->

### Customer Communication:
1. **OpenAI Node** - Generate personalized email:
   ```
   Write a friendly order confirmation email for this customer:

   Customer: {customer_name}
   Order: {order_id}
   Items: {items_summary}
   Estimated delivery: {delivery_date}

   Tone: Professional but warm, include tracking info and support contact.
   ```

2. **Gmail Node** - Send confirmation email
3. **Wait Node** - Wait 1 hour
4. **WhatsApp Node** - Send tracking link via WhatsApp

### Team Notifications:
1. **Switch Node** - Route based on fulfillment center
2. **Slack Nodes** - Notify respective teams:
   - Jakarta team channel
   - Surabaya team channel
   - Medan team channel

---

## Step 5: Tracking & Follow-up

![Step 5](day-2/images/exercise-step5-tracking.png)
<!-- Placeholder: Tracking setup -->

### Setup Tracking:
1. **Airtable Node** - Create order record with:
   - Order details
   - AI insights
   - Assigned team
   - Processing timestamps
   - Customer communication log

2. **Function Node** - Generate tracking number
3. **Set Node** - Prepare follow-up schedule

### Automated Follow-up:
1. **Wait Node** - Wait 24 hours
2. **IF Node** - Check if order shipped
3. **Not Shipped**: Alert fulfillment team
4. **Shipped**: Send shipping notification

**Business Result**: Complete order lifecycle automated!

---

## Step 6: Analytics & Insights

![Step 6](day-2/images/exercise-step6-analytics.png)
<!-- Placeholder: Analytics dashboard -->

### Daily Reports Automation:
1. **Cron Trigger** - Every day at 8 AM
2. **Google Sheets Node** - Aggregate yesterday's orders
3. **OpenAI Node** - Generate insights:
   ```
   Analyze yesterday's e-commerce data and provide business insights:

   Orders processed: {count}
   Total revenue: {revenue}
   Top products: {top_products}
   Fulfillment performance: {fulfillment_stats}
   Customer satisfaction signals: {satisfaction_data}

   Provide: 3 key insights, 2 action recommendations, 1 concern to watch
   ```
4. **Slack Node** - Send daily insights to management
5. **Gmail Node** - Email detailed report to stakeholders

**Business Value**: Data-driven decision making, proactive issue detection!

---

<!-- SECTION 7: Summary -->
# Summary & Next Steps

---

## Apa yang Sudah Dikuasai Hari Ini

![Day 2 Achievements](day-2/images/day2-achievements.png)
<!-- Placeholder: Visual summary of achievements -->

### 🎯 **Core Skills Acquired:**
✅ **Data Flow Mastery** - Memahami bagaimana data mengalir dan bertransformasi
✅ **Branching Logic** - Membuat keputusan otomatis berdasarkan kondisi bisnis
✅ **Node Expertise** - Menguasai node populer untuk automation sehari-hari
✅ **AI Integration** - Menggunakan LLM untuk automation yang lebih pintar
✅ **Complex Workflows** - Membangun automation end-to-end untuk proses bisnis real

### 💼 **Business Impact:**
- Automation lebih sophisticated dan fleksibel
- Proses bisnis yang kompleks bisa diotomatisasi
- AI membuat automation "pintar" dan adaptif
- ROI automation meningkat significantly

---

## Real-World Applications

![Real World Apps](day-2/images/real-world-applications.png)
<!-- Placeholder: Various business applications -->

### Yang Bisa Anda Terapkan Sekarang:

🏢 **Sales & Marketing**:
- Lead qualification otomatis dengan AI scoring
- Personalized email campaigns berdasarkan behavior
- Social media content generation dan scheduling
- Customer journey automation dengan branching logic

📊 **Operations**:
- Inventory management dengan predictive alerts
- Order processing end-to-end automation
- Customer support dengan AI-powered routing
- Report generation dan distribution otomatis

💰 **Finance**:
- Invoice processing dengan data extraction
- Expense categorization menggunakan AI
- Payment reconciliation automation
- Financial reporting dengan insights generation

---

## Advanced Patterns Learned

![Advanced Patterns](day-2/images/advanced-patterns.png)
<!-- Placeholder: Pattern illustrations -->

### 🔄 **Data Patterns**:
- **Extract-Transform-Load (ETL)** untuk data processing
- **Merge & Split** untuk handling multiple data sources
- **Validation & Error Handling** untuk data quality
- **Format Standardization** untuk cross-platform compatibility

### 🧠 **Logic Patterns**:
- **Conditional Routing** berdasarkan business rules
- **Priority Queuing** untuk task management
- **Exception Handling** untuk edge cases
- **Fallback Mechanisms** untuk reliability

### 🤖 **AI Patterns**:
- **Prompt Engineering** untuk consistent results
- **Chain of Thought** untuk complex analysis
- **Few-Shot Learning** untuk specific business contexts
- **Confidence Scoring** untuk quality control

---

## Next Steps & Homework

![Homework](day-2/images/homework-assignments.png)
<!-- Placeholder: Homework visual -->

### 📝 **Homework Assignments:**

**Level 1 - Practice Core Skills:**
- Buat 1 workflow dengan minimal 3 nodes berbeda
- Implementasi 1 branching logic untuk use case bisnis Anda
- Test data flow dengan tracing dari input ke output

**Level 2 - Apply to Business:**
- Identifikasi 1 proses bisnis yang bisa pakai branching
- Design workflow dengan AI integration untuk 1 use case
- Hitung potential time savings dari automation yang dibuat

**Level 3 - Advanced Challenge:**
- Buat end-to-end automation untuk proses bisnis kompleks
- Integrasikan minimal 5 applications yang berbeda
- Implementasi error handling dan monitoring

---

## Persiapan Day 3

![Day 3 Preview](day-2/images/day3-preview.png)
<!-- Placeholder: Day 3 preview topics -->

### 🚀 **Coming Up in Day 3:**

**Error Handling & Debugging**:
- Mengatasi automation yang "stuck" atau error
- Best practices untuk reliability dan monitoring
- Notification systems untuk automation failures

**Performance Optimization**:
- Membuat automation yang cepat dan efficient
- Rate limiting dan resource management
- Scaling automation untuk volume tinggi

**Security & Governance**:
- Protecting sensitive data dalam automation
- Access control dan permissions management
- Compliance considerations untuk automation

### Prepare by:
- Documenting challenges dari homework exercises
- Listing questions tentang reliability concerns
- Thinking about scaling current automations

---

## Resources untuk Lanjutan

![Resources](day-2/images/additional-resources.png)
<!-- Placeholder: Resource links dan materials -->

### 📚 **Learning Materials:**

**N8N Documentation:**
- [Advanced Workflows Guide](https://docs.n8n.io/workflows/)
- [Node Reference](https://docs.n8n.io/nodes/)
- [Best Practices](https://docs.n8n.io/workflows/best-practices/)

**AI Integration:**
- [OpenAI API Documentation](https://platform.openai.com/docs)
- [Prompt Engineering Guide](https://promptengineering.org)
- [Business AI Use Cases](https://openai.com/business)

**Community & Support:**
- [N8N Community Forum](https://community.n8n.io)
- [Discord Channel](https://discord.n8n.io)
- [GitHub Repository](https://github.com/n8n-io/n8n)

### 🛠️ **Tools untuk Practice:**
- N8N Cloud free tier untuk testing
- OpenAI playground untuk prompt development
- Sample datasets untuk practice workflows

---

# Terima Kasih!

## Q&A Session

![QA Session](day-2/images/qa-session-day2.png)
<!-- Placeholder: Q&A session image -->

### Discussion Topics:
- Challenges dengan complex data flows
- AI integration questions dan concerns
- Business-specific automation ideas
- Technical troubleshooting

### Contact & Support:
- **Email**: [instructor-email@domain.com]
- **Slack**: #n8n-tutorial-day2
- **Office Hours**: [Schedule untuk individual help]
- **Homework Submission**: [Platform/method]

**Remember**: Start simple, then add complexity. Master the basics before advanced features!

---