# Automated Email Campaign Setup Guide

## Overview

This guide will help you set up a semi-automated email outreach system where Claude can help manage, analyze, and respond to your customer discovery emails.

---

## Step 1: Create Business Email Identity

### Option A: Google Workspace (Recommended - $6/month)
**Benefits:** Professional, integrates with everything, unlimited storage

1. Go to [workspace.google.com](https://workspace.google.com)
2. Sign up with your domain (or buy one through Google for $12/year)
3. Suggested email: `cameron@restauranttrainingai.com` or similar
4. Set up email signature with:
   - Your name
   - Title: "Founder" or "Product Lead"
   - Company name (can be simple: "Restaurant Training Solutions")
   - Phone number
   - LinkedIn profile

### Option B: Free Gmail (Quick Start)
- Create: `restauranttraining.ai@gmail.com` or similar
- Pros: Free, immediate
- Cons: Less professional, may have deliverability issues at scale

**Recommendation:** Start with Option B for testing, upgrade to Option A once you have 5+ pilot prospects.

---

## Step 2: Choose and Set Up Email Platform

### Recommended: SendGrid (Best for personalized outreach)

**Why SendGrid:**
- Free tier: 100 emails/day (3,000/month)
- Excellent deliverability
- API access for automation
- Detailed analytics (opens, clicks, bounces)
- Dynamic templating for personalization

**Setup Process:**

1. **Create Account**
   - Go to [sendgrid.com](https://sendgrid.com)
   - Sign up for free account
   - Verify your business email

2. **Domain Authentication** (Critical for deliverability)
   - In SendGrid: Settings → Sender Authentication
   - Follow DNS setup instructions
   - This prevents emails from going to spam

3. **Create Sender Identity**
   - Settings → Sender Authentication → Single Sender Verification
   - Use your business email
   - This allows you to send from that address

4. **API Key**
   - Settings → API Keys → Create API Key
   - Full Access permissions
   - Save this key securely (you'll need it for automation)

---

## Step 3: Set Up Automation Hub (Make.com)

### Why Make.com:
- Free tier: 1,000 operations/month (plenty for early stage)
- More powerful than Zapier
- Visual workflow builder
- Can read/write to Google Sheets

### Setup Process:

1. **Create Account**
   - Go to [make.com](https://make.com)
   - Sign up for free account

2. **Connect Services**
   - Add Gmail integration (your business email)
   - Add Google Sheets integration
   - Add SendGrid integration (use API key from Step 2)

---

## Step 4: Create Response Tracking System

### Google Sheets Setup

I'll help you create a tracking sheet with these tabs:
1. **Prospects** - Your outreach list
2. **Responses** - Auto-populated from email replies
3. **Analysis** - Claude's categorization and insights
4. **Follow-ups** - Scheduled next steps

**Key features:**
- Webhook auto-populates responses
- I can read and analyze daily
- You can share access with me via file path

---

## Step 5: Build Automation Workflows

### Workflow 1: Outbound Campaign (SendGrid)

**What it does:** Sends personalized emails to your prospect list

**Setup in SendGrid:**

1. **Create Email Template**
   - Marketing → Dynamic Templates → Create Template
   - Use handlebars for personalization: `{{first_name}}`, `{{restaurant_name}}`, etc.
   - Claude will draft the template for you

2. **Upload Contact List**
   - Marketing → Contacts → Add Contacts
   - Upload CSV with columns: email, first_name, restaurant_name, category, etc.

3. **Create Campaign**
   - Marketing → Single Sends → Create Single Send
   - Choose template
   - Select segment
   - Schedule send time (Tuesday-Thursday 10am-2pm for best open rates)

**Personalization fields to include:**
- `{{first_name}}` - Restaurant manager's first name
- `{{restaurant_name}}` - Name of their restaurant
- `{{category}}` - Fine dining / casual / etc.
- `{{location}}` - City/neighborhood

---

### Workflow 2: Response Capture (Make.com)

**What it does:** Auto-logs email responses to Google Sheet for Claude analysis

**Make.com Scenario Setup:**

```
TRIGGER: Gmail - Watch Emails
  ↓
FILTER: Subject contains "Re:" or In-Reply-To exists
  ↓
ACTION: Google Sheets - Add Row
  - Sheet: "Responses" tab
  - Data: From, Subject, Body, Timestamp, Thread ID
  ↓
ACTION: Google Sheets - Update Row
  - Sheet: "Prospects" tab
  - Match: Email address
  - Update: Status = "Replied", Last Contact = Date
```

**Step-by-step in Make:**

1. Create New Scenario
2. Add Gmail "Watch Emails" module
   - Connect your business Gmail
   - Filter: Only emails to your address (not from you)
   - Folder: Inbox
   - Max results: 10

3. Add Router with 2 paths:

   **Path A: Log to Responses sheet**
   - Add "Google Sheets - Add a Row" module
   - Select your tracking spreadsheet
   - Map fields:
     - Timestamp: `{{now}}`
     - From Email: `{{from}}`
     - From Name: `{{fromName}}`
     - Subject: `{{subject}}`
     - Body: `{{text}}`
     - Thread ID: `{{threadId}}`
     - Status: "New"

   **Path B: Update prospect status**
   - Add "Google Sheets - Update a Row" module
   - Search by email address
   - Update "Last Response" and "Status" columns

4. Schedule: Every 15 minutes
5. Activate scenario

---

### Workflow 3: Daily Digest (Optional)

**What it does:** Sends you a summary of new responses each morning

**Make.com Scenario:**

```
TRIGGER: Schedule (Daily at 8am)
  ↓
ACTION: Google Sheets - Search Rows
  - Sheet: Responses
  - Filter: Date = Yesterday, Status = New
  ↓
ACTION: Gmail - Send Email
  - To: Your personal email
  - Subject: "New Restaurant Responses - [count]"
  - Body: Summary of responses with links
```

---

## Step 6: Claude Integration Workflow

### How You'll Work with Me:

**Daily/On-Demand Analysis:**

1. **You share the Google Sheet** with me by providing the file path
   - I can read Google Sheets if you export and share the file
   - Or you copy-paste new responses into our conversation

2. **I analyze responses:**
   - Categorize as: Hot Lead / Warm / Cold / Not a Fit
   - Extract key insights (pain points, WTP, objections)
   - Flag priority follow-ups
   - Draft personalized reply templates

3. **You review and send:**
   - I provide draft responses
   - You customize if needed
   - Send from your email platform

4. **I track in sheet:**
   - Update lead score
   - Log next steps
   - Track to pilot conversion funnel

---

## Simplified Workflow (If Full Automation Is Too Complex)

### Manual Process with Claude Support:

**Week 1: Keep it simple**

1. **Send emails manually** using Gmail + mail merge extension
2. **Forward me interesting responses** via copy-paste
3. **I draft replies** for you
4. **Track in simple spreadsheet**

**Week 2-4: Add automation incrementally**
- Set up response capture to Google Sheets
- I analyze sheets daily
- You still send manually but I help prioritize

**Month 2: Full automation**
- SendGrid for campaigns
- Make.com for response tracking
- Daily Claude analysis
- Scale to 50+ prospects

---

## Email Campaign Templates

I'll create these for you in the next section:

1. **Initial Outreach** - Cold email introducing yourself, asking for 10-min interview
2. **Follow-up #1** (3 days later) - Soft reminder if no response
3. **Follow-up #2** (7 days later) - Value-add (insight/article) + ask
4. **Thank You** - Post-interview appreciation + next steps
5. **Pilot Invitation** - For hot leads, formal pilot program invite
6. **Nurture** - For warm leads not ready yet

---

## Email Deliverability Best Practices

**To avoid spam folder:**

1. **Authenticate domain** (SPF, DKIM, DMARC) via SendGrid
2. **Warm up email** - Start with 10/day, increase slowly
3. **Personalize every email** - No mass generic blasts
4. **Include unsubscribe link** (even for cold outreach)
5. **Monitor bounce rate** - Remove bad emails immediately
6. **Don't use spam trigger words** - "Free", "Act now", "Limited time"

**Optimal sending times:**
- Tuesday-Thursday
- 10am-2pm or 4-6pm (avoiding meal service times for restaurants)
- Avoid Mondays (too busy) and Fridays (planning weekend)

---

## Metrics to Track

### Email Performance:
- **Open Rate** (target: 30-40% for cold outreach)
- **Reply Rate** (target: 5-10% for cold outreach)
- **Bounce Rate** (keep under 3%)
- **Unsubscribe Rate** (under 1%)

### Lead Conversion:
- **Responses → Interview Scheduled** (target: 50%+)
- **Interviews → Hot Leads** (target: 30%+)
- **Hot Leads → Pilot Customers** (target: 50%+)

I'll help you track all of these in your Google Sheet.

---

## Cost Summary

### Free Tier (Month 1-2):
- Gmail: $0 (or $6 if Google Workspace)
- SendGrid: $0 (up to 100 emails/day)
- Make.com: $0 (up to 1,000 operations/month)
- **Total: $0-6/month**

### Paid Tier (When scaling):
- Google Workspace: $6/month
- SendGrid Pro: $20/month (40,000 emails)
- Make.com Core: $9/month (10,000 operations)
- **Total: $35/month**

---

## Next Steps - What We'll Do Together

1. **I'll create email templates** (all 6 sequences)
2. **I'll build the Google Sheets tracker** for you
3. **I'll write Make.com scenario instructions** (step-by-step with screenshots descriptions)
4. **You set up accounts** (SendGrid, Make.com, business email)
5. **You build prospect list** (restaurants to target)
6. **I help you personalize and segment**
7. **You launch first campaign** (10-20 emails to test)
8. **We iterate based on response rates**

---

## Alternative: Start Simple, Scale Later

**Not ready for full automation yet?**

**Week 1 Approach:**
1. Create business Gmail
2. Use Gmail + "Yet Another Mail Merge" extension (free)
3. Send 10 personalized emails/day
4. Forward responses to our conversation
5. I help you draft replies

**This gets you started TODAY** without complex setup.

Once you have 5+ positive responses, we can build the automated system.

---

**Which approach do you want to take?**
- Full automation setup now (2-3 hours of setup)
- Simple manual start, automate later (30 min setup)

Let me know and I'll create the specific templates and tools you need!
