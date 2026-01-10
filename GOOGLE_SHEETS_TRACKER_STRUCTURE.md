# Google Sheets Email Campaign Tracker - Structure Guide

This document describes the structure for your email campaign tracking spreadsheet. You can create this in Google Sheets and share access with me for analysis.

---

## Sheet Overview

Your tracking spreadsheet should have **5 tabs:**

1. **Prospects** - Your outreach list with contact info and status
2. **Responses** - Auto-populated email replies (via Make.com webhook)
3. **Interviews** - Scheduled and completed interviews with notes
4. **Analysis** - Claude's categorization and insights
5. **Metrics** - Campaign performance dashboard

---

## Tab 1: PROSPECTS

### Column Structure:

| Column | Data Type | Description | Example |
|--------|-----------|-------------|---------|
| A: ID | Number | Unique prospect ID | 1, 2, 3... |
| B: Restaurant Name | Text | Full restaurant name | "Alinea" |
| C: Category | Dropdown | Fine Dining / Casual / Fast Casual | "Fine Dining" |
| D: Location | Text | City or neighborhood | "Chicago, Lincoln Park" |
| E: First Name | Text | Manager's first name | "Grant" |
| F: Last Name | Text | Manager's last name | "Achatz" |
| G: Title | Text | Their role | "Owner & Chef" |
| H: Email | Email | Contact email | "grant@alinea.com" |
| I: Phone | Text | Phone number (optional) | "(312) 867-0110" |
| J: Source | Text | How you found them | "Google search", "Referral" |
| K: Team Size (Est.) | Number | Estimated # of servers + support | 25 |
| L: Locations | Number | Number of restaurant locations | 1 |
| M: Menu Complexity | Dropdown | Simple / Moderate / Complex | "Complex" |
| N: Status | Dropdown | See status options below | "Email Sent" |
| O: Priority | Dropdown | Hot / Warm / Cold / Not a Fit | "Warm" |
| P: Email Sent Date | Date | When first email was sent | "2026-01-11" |
| Q: Last Contact | Date | Most recent touchpoint | "2026-01-15" |
| R: Next Action | Text | What to do next | "Follow-up #2 on Jan 18" |
| S: Next Action Date | Date | When to do it | "2026-01-18" |
| T: Emails Sent Count | Number | Total emails to this prospect | 3 |
| U: Opened? | Checkbox | Did they open email? | ✓ |
| V: Replied? | Checkbox | Did they reply? | ✓ |
| W: Interview Scheduled? | Checkbox | Interview on calendar? |  |
| X: Interview Completed? | Checkbox | Interview finished? |  |
| Y: Pilot Interest Level | Number 1-5 | 5=very interested, 1=not interested | 4 |
| Z: Notes | Text | Free-form notes | "Mentioned high turnover" |

### Status Options (Column N):
- `Prospect` - Not yet contacted
- `Email Sent` - Initial outreach sent
- `Follow-up #1` - First follow-up sent
- `Follow-up #2` - Second follow-up sent
- `Follow-up #3` - Final follow-up sent
- `Responded` - They replied
- `Interview Scheduled` - Call on calendar
- `Interview Complete` - Spoke with them
- `Hot Lead` - Strong pilot candidate
- `Warm Lead` - Interested but not ready
- `Cold Lead` - Low interest
- `Not a Fit` - Wrong customer
- `Nurture` - Long-term follow-up
- `Pilot Customer` - Signed up for pilot!

### Conditional Formatting:
- **Hot Lead**: Green background
- **Warm Lead**: Yellow background
- **Cold Lead**: Orange background
- **Not a Fit**: Red background
- **Pilot Customer**: Dark green background, white text

### Sample Data (First 3 Rows):

| ID | Restaurant Name | Category | Location | First Name | Email | Status | Priority |
|----|----------------|----------|----------|------------|-------|---------|----------|
| 1 | Alinea | Fine Dining | Chicago | Grant | grant@alinea.com | Interview Complete | Hot |
| 2 | The French Laundry | Fine Dining | Yountville | Thomas | tk@frenchlaundry.com | Email Sent | Warm |
| 3 | Shake Shack Downtown | Fast Casual | NYC | Maria | maria@shakeshack.com | Responded | Warm |

---

## Tab 2: RESPONSES

### Column Structure:

| Column | Data Type | Description |
|--------|-----------|-------------|
| A: Response ID | Auto-number | Unique ID for each response |
| B: Timestamp | Datetime | When email was received |
| C: Prospect ID | Number | Links to Prospects tab |
| D: From Email | Email | Their email address |
| E: From Name | Text | Their name from email |
| F: Subject | Text | Email subject line |
| G: Body | Long text | Full email body |
| H: Thread ID | Text | Gmail thread ID (for tracking conversations) |
| I: Status | Dropdown | New / Reviewed / Replied / Archived |
| J: Sentiment | Dropdown | Positive / Neutral / Negative / Question |
| K: Lead Score | Number 1-10 | Claude's assessment of lead quality |
| L: Key Points | Text | Main takeaways from response |
| M: Suggested Reply | Long text | Claude's draft response |
| N: Reply Sent? | Checkbox | Did you send a reply? |
| O: Reply Sent Date | Date | When you replied |

### Auto-Population via Make.com:
Columns A-H are auto-filled by Make.com webhook when new email arrives.
Columns I-M are filled by Claude during analysis.
Columns N-O are manually updated by you.

### Sample Data:

| Response ID | Timestamp | From Email | Subject | Body | Status | Sentiment |
|-------------|-----------|------------|---------|------|--------|-----------|
| 1 | 2026-01-11 14:23 | grant@alinea.com | Re: Training question | "Yes, I'd love to chat. We struggle with this..." | Reviewed | Positive |
| 2 | 2026-01-12 09:15 | maria@shakeshack.com | Re: Quick question | "Not interested right now, maybe in 6 months" | Reviewed | Neutral |

---

## Tab 3: INTERVIEWS

### Column Structure:

| Column | Data Type | Description |
|--------|-----------|-------------|
| A: Interview ID | Number | Unique ID |
| B: Prospect ID | Number | Links to Prospects tab |
| C: Restaurant Name | Text | Auto-filled from Prospects |
| D: Contact Name | Text | Who you interviewed |
| E: Date Scheduled | Date | Interview date |
| F: Date Completed | Date | When it actually happened |
| G: Duration (min) | Number | How long was it? |
| H: Format | Dropdown | In-person / Phone / Video / Email |
| I: Recording? | Checkbox | Did you record it? |
| J: Recording Link | URL | Link to audio/transcript |
| K: Pain Intensity | Number 1-10 | How much do they hurt? |
| L: Top Pain Points | Text | Main challenges mentioned |
| M: Error Cost/Month | Currency | $ cost of errors |
| N: Training Cost/Month | Currency | $ cost of training time |
| O: Turnover Cost/Year | Currency | $ cost of early turnover |
| P: Total Pain $/Month | Formula | Sum of costs |
| Q: WTP ($/emp/month) | Currency | Willingness to pay |
| R: Feature Rankings | Text | "Quizzes: 1, Dashboard: 2, Mobile: 1..." |
| S: Top 3 Features | Text | Must-have features |
| T: Pilot Interest? | Dropdown | Yes / Maybe / No |
| U: Decision Maker? | Checkbox | Can they say yes to pilot? |
| V: Follow-up Actions | Text | Next steps |
| W: Lead Classification | Dropdown | Hot / Warm / Cold / Not a Fit |
| X: Interview Notes | Long text | Full notes or key quotes |

### Sample Data:

| Interview ID | Restaurant | Contact | Pain $/mo | WTP | Pilot Interest | Classification |
|--------------|-----------|---------|-----------|-----|----------------|----------------|
| 1 | Alinea | Grant Achatz | $2,100 | $25 | Yes | Hot |
| 2 | Shake Shack | Maria Gonzalez | $800 | $8 | Maybe | Warm |

---

## Tab 4: ANALYSIS (Claude's Work Area)

This is where Claude will add insights from analyzing all the data.

### Section A: Lead Scoring & Prioritization

| Prospect ID | Restaurant | Category | Pain Score | WTP Score | Engagement Score | TOTAL SCORE | Recommended Action |
|-------------|-----------|----------|------------|-----------|------------------|-------------|--------------------|
| 1 | Alinea | Fine | 9 | 10 | 8 | 27 | Invite to pilot immediately |
| 3 | Shake Shack | Fast Casual | 5 | 4 | 6 | 15 | Nurture for later |

**Scoring criteria:**
- **Pain Score**: 1-10 based on quantified pain and urgency
- **WTP Score**: 1-10 based on willingness to pay (10 = $20+/user, 1 = <$5/user)
- **Engagement Score**: 1-10 based on response rate, interview quality, enthusiasm

### Section B: Segment Analysis

| Segment | # Prospects | # Interviewed | Avg Pain $/mo | Avg WTP | Hot Leads | Recommended Beachhead? |
|---------|-------------|---------------|---------------|---------|-----------|------------------------|
| Fine Dining | 15 | 8 | $1,850 | $22 | 5 | YES - Strong fit |
| Casual Dining | 20 | 12 | $1,200 | $14 | 3 | MAYBE |
| Fast Casual | 10 | 5 | $650 | $9 | 0 | NO - WTP too low |

### Section C: Feature Priority Insights

| Feature | Avg Ranking | % Ranked #1 or #2 | Build Priority | Notes |
|---------|-------------|-------------------|----------------|-------|
| Menu quizzes | 1.4 | 85% | MVP - Build first | Universal need |
| Manager dashboard | 1.8 | 70% | MVP - Build first | Buyer centric |
| Auto-generated content | 2.1 | 60% | MVP - Build first | Differentiator |
| Mobile | 2.3 | 55% | MVP | Mentioned by servers |
| Gamification | 3.2 | 20% | V2 - Later | Nice to have |

### Section D: Key Insights & Patterns

**Common Pain Points:**
1. Training takes 8-14 weeks (mentioned by 90% of interviews)
2. No systematic way to test menu knowledge (85%)
3. Errors cost $500-2000/month (75%)

**Objections to Address:**
1. "Staff won't use another app" - Need to prove engagement
2. "Setup sounds time-consuming" - Emphasize auto-generation
3. "We tried training software before" - Ask what failed, differentiate

**Surprising Findings:**
- [Claude will fill this in based on interview transcripts]

**Recommended Pivot/Adjust:**
- [Claude's strategic recommendations]

---

## Tab 5: METRICS (Dashboard)

### Campaign Performance

| Metric | Week 1 | Week 2 | Week 3 | Week 4 | Total | Target | Status |
|--------|--------|--------|--------|--------|-------|--------|--------|
| Emails Sent | 25 | 40 | 50 | 50 | 165 | 200 | ⚠️ Behind |
| Open Rate | 38% | 42% | 35% | 40% | 39% | 35% | ✅ Good |
| Reply Rate | 12% | 10% | 8% | 11% | 10% | 8% | ✅ Good |
| Meetings Booked | 2 | 3 | 3 | 4 | 12 | 15 | ⚠️ Behind |
| Interviews Completed | 1 | 2 | 4 | 3 | 10 | 20 | ⚠️ Behind |
| Hot Leads | 0 | 1 | 2 | 2 | 5 | 5 | ✅ On Track |

### Conversion Funnel

| Stage | Count | Conversion Rate | Notes |
|-------|-------|----------------|-------|
| Prospects Identified | 200 | - | Total list |
| Emails Sent | 165 | 82.5% | Still sending |
| Emails Opened | 64 | 38.8% | Strong open rate |
| Replied | 17 | 10.3% | Above target |
| Interview Scheduled | 12 | 70.6% of replies | Good |
| Interview Completed | 10 | 83.3% of scheduled | Excellent show rate |
| Hot Leads | 5 | 50% of interviews | On target |
| Pilot Customers | 0 | 0% | TBD |

### By Segment Performance

| Segment | Emails Sent | Reply Rate | Avg WTP | Hot Leads | Pilot Potential |
|---------|-------------|------------|---------|-----------|-----------------|
| Fine Dining | 50 | 14% | $22 | 4 | ⭐⭐⭐⭐⭐ |
| Casual Dining | 75 | 9% | $14 | 1 | ⭐⭐⭐ |
| Fast Casual | 40 | 7% | $9 | 0 | ⭐ |

### Email Template Performance (A/B Testing)

| Template Variant | Emails Sent | Open Rate | Reply Rate | Winner? |
|------------------|-------------|-----------|------------|---------|
| Subject A: "Quick question..." | 50 | 42% | 12% | ✅ |
| Subject B: "How do you train..." | 50 | 35% | 8% | |
| Subject C: "10 minutes to discuss..." | 50 | 38% | 10% | |

---

## Formulas to Include

### In PROSPECTS Tab:

**Next Action Date** (Auto-calculate based on status):
```
=IF(N2="Email Sent", P2+3,
  IF(N2="Follow-up #1", P2+4,
    IF(N2="Follow-up #2", P2+7, "")))
```

**Emails Sent Count** (Count how many emails to this prospect):
```
=COUNTIF(Q:Q, A2)
```

### In INTERVIEWS Tab:

**Total Pain $/Month** (Sum of all costs):
```
=M2+N2+(O2/12)
```

### In METRICS Tab:

**Open Rate**:
```
=COUNTIF(Prospects!U:U, TRUE) / COUNTIF(Prospects!N:N, "Email Sent", "Follow-up*")
```

**Reply Rate**:
```
=COUNTIF(Prospects!V:V, TRUE) / COUNTIF(Prospects!N:N, "Email Sent", "Follow-up*")
```

---

## How Claude Will Use This Sheet

### Daily Analysis Workflow:

1. **You share the sheet with me** (export as CSV or copy-paste new responses)
2. **I read the Responses tab** for new replies
3. **I analyze sentiment and intent**, update columns I-M
4. **I draft personalized replies** for you to review
5. **I update the Analysis tab** with patterns and insights
6. **I flag priority actions** for you (hot leads to contact, follow-ups due, etc.)

### Weekly Analysis:

1. **Review all interviews** from past week
2. **Update segment analysis** with new data
3. **Recalculate feature priorities** based on latest rankings
4. **Generate insights report** (what's working, what to change)
5. **Recommend strategy adjustments** (focus on segment X, test new message Y)

### Monthly Analysis:

1. **Full funnel analysis** - where are drop-offs?
2. **Beachhead recommendation** - ready to pick target segment?
3. **Pilot readiness assessment** - do you have 3-5 strong candidates?
4. **Content optimization** - which templates are winning?

---

## Setup Instructions

### Step 1: Create the Sheet

1. Go to [Google Sheets](https://sheets.google.com)
2. Create new spreadsheet: "Restaurant Training - Email Campaign Tracker"
3. Create 5 tabs as described above
4. Set up column headers in each tab
5. Add conditional formatting for status colors

### Step 2: Populate Prospects

1. Research restaurants in your target area
2. Find contact info (website, LinkedIn, Yelp)
3. Add to Prospects tab
4. Start with 50-100 prospects

### Step 3: Connect Make.com (Optional)

1. Set up Make.com scenario as described in EMAIL_CAMPAIGN_SETUP_GUIDE.md
2. Connect to Gmail and Google Sheets
3. Map email fields to Responses tab columns
4. Test with a sample email

### Step 4: Share with Claude

**Option A: Direct file sharing**
- Export sheet as CSV periodically
- Upload to our conversation

**Option B: Manual copy-paste**
- Copy new responses
- Paste into our conversation
- I'll analyze and provide updates

**Option C: Automated (advanced)**
- Set up webhook to write responses to a text file
- I can read the file periodically

---

## Sample Workflow: Week 1

**Monday:**
- Upload 50 prospects to sheet
- Send 10 initial outreach emails (Template 1)
- Mark status as "Email Sent", log date

**Tuesday:**
- Check for opens/replies (via SendGrid tracking)
- Update checkboxes in Prospects tab
- Send 10 more outreach emails

**Wednesday:**
- Copy-paste any responses to our conversation
- I analyze sentiment and draft replies
- You review and send replies
- Send 10 more outreach emails

**Thursday:**
- Follow up on any scheduled interviews
- Update interview tab with notes
- Send follow-up #1 to Day 1 emails (3 days later)

**Friday:**
- Copy full Responses tab to me
- I provide weekly analysis
- We review which templates are working
- Plan next week's outreach

**Repeat weekly, scaling up email volume as you refine the process.**

---

You now have a complete tracking system! Let me know when you've created the sheet and I can help you populate it or analyze your first batch of responses.
