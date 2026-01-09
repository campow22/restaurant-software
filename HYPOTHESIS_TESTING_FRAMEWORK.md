# Lean Startup Hypothesis Testing Framework

## Overview

You've identified two critical hypotheses to validate:
1. **Restaurants will pay for training software** (Willingness to Pay)
2. **The software will deliver promised results** (Value Delivery)

This framework provides a structured approach to test these hypotheses empirically using the Lean Startup methodology.

---

## Phase 1: Problem Validation (Weeks 1-4)

### Hypothesis 1A: Fine dining restaurants struggle with training consistency and effectiveness

**What we believe:**
- Training is currently ad-hoc, inconsistent, and time-consuming
- Onboarding takes 3-6 months to get servers fully productive
- Menu knowledge gaps lead to service errors and lost sales
- Managers lack visibility into who knows what

**How to test:**
- Conduct 30-50 customer discovery interviews with fine dining GMs/owners
- Observe current training processes if possible
- Ask about last 3 server hires - how long to productivity? What went well/poorly?

**Success criteria:**
- 70%+ of interviews confirm training is a top-3 operational challenge
- Can identify specific, quantifiable pain (error rates, training hours, turnover costs)
- Managers express frustration with current solutions

**Interview Script Questions:**
- Walk me through how you onboard a new server
- How long until they can handle a full section confidently?
- What are the most common mistakes new servers make?
- How do you test menu knowledge? How often?
- What happens when a server makes a mistake? What does it cost you?
- Have you tried any training solutions before? What happened?

**Invalidation signals:**
- "Training works fine for us"
- "We don't really track that"
- "It's not a problem worth solving"
- Focus on other issues (staffing shortages, food costs, etc.)

---

### Hypothesis 1B: Restaurants will pay $15-25/user/month for effective training software

**What we believe:**
- ROI is clear: preventing 1 error/month or reducing 1 turnover/year justifies cost
- Price point is affordable even for independent fine dining
- Per-user model aligns with their mental model

**How to test:**
- During problem interviews, transition to solution discussion
- Present hypothetical solution and pricing
- Use "broken product" technique: "I have software that does X, would you buy it?"

**Validation questions:**
- "If I could reduce your training time by 50% and reduce errors, what would that be worth?"
- "What do you currently spend on training per new hire?" (time × hourly rate)
- "What does a typical service error cost you?" (comped meals, guest satisfaction)
- Present pricing: "Would $20/user/month be reasonable if it delivered those results?"
- "What ROI or payback period would you need to see?"

**Success criteria:**
- 10+ restaurants say "yes, I would pay that" or "tell me more"
- Can articulate clear ROI that justifies cost
- No strong price objections (some negotiation is normal)
- Willing to commit to pilot if you build it

**Invalidation signals:**
- "That's too expensive" (without willingness to discuss value)
- "We'd need to see results first" (with no path to pilot)
- "Maybe $5/user" (10x off from your target)
- Budget is controlled by corporate/franchisee, can't make decision

**Experiment: Pre-Sales Test**
- After 15-20 validation interviews, create simple landing page or one-pager
- Ask 5-10 restaurants: "Would you commit to a 3-month pilot at 50% off ($10/user) if I build this?"
- Goal: Get 2-3 signed LOIs (letters of intent) before building anything

---

## Phase 2: MVP Solution Validation (Weeks 5-12)

### Hypothesis 2A: A menu knowledge quiz platform will be used by servers

**What we believe:**
- Servers will voluntarily use the platform if it helps them perform better
- Gamification and mobile-friendly design will drive engagement
- Managers will make it mandatory, ensuring adoption

**How to test:**
- Build absolute minimum quiz platform:
  - Menu items with descriptions, ingredients, preparation
  - Multiple choice and flashcard-style quizzes
  - Simple scoring and progress tracking
  - Manager dashboard showing completion and scores

**Success criteria (2-3 pilot restaurants, 8 weeks):**
- 70%+ of servers complete at least 3 quiz sessions in first month
- Average 2+ sessions per week per active user
- 80%+ of servers report it helped them feel more confident
- Managers report it's being used without constant reminders

**Key metrics to track:**
- Daily/weekly active users
- Average session length
- Quiz completion rate
- Score improvement over time
- Time to reach "certification" threshold
- Manager login frequency

**Invalidation signals:**
- <30% of servers use it after first week
- Managers have to constantly push adoption
- Servers say "I don't have time for this"
- Negative feedback about UX or relevance

**Iteration triggers:**
- If engagement is low: test different incentives, gamification, timing
- If scores don't improve: content quality issue
- If managers don't use dashboard: wrong metrics displayed

---

### Hypothesis 2B: Using the platform improves measurable outcomes

**What we believe:**
- Servers who use it will have fewer errors
- Servers who use it will have higher sales per cover
- Training time will be reduced
- Confidence and job satisfaction will improve

**How to test:**
- During pilot, collect baseline metrics BEFORE implementation
- Track same metrics during 8-week pilot
- Compare high-usage vs. low-usage servers (cohort analysis)

**Baseline data to collect:**
- Error rate (voids, comps, remakes per server per shift)
- Sales per cover by server
- Time to "certified" status for new hires (manager assessment)
- Turnover rate (if possible - may need longer timeframe)
- Guest satisfaction scores (if available)

**Success criteria:**
- Servers using platform 2x/week show 30%+ reduction in errors vs. baseline
- OR: Sales per cover improves by 10%+ for engaged users
- OR: New hire training time reduced from 12 weeks to 8 weeks
- Manager reports noticeable improvement in service quality

**How to measure:**
- Weekly data exports from POS system (errors, sales)
- Manager surveys: "Has this improved your team's performance?"
- Server surveys: "Do you feel more confident? Rate 1-10"
- Before/after comparison for new hires

**Invalidation signals:**
- No measurable difference in any metric after 8 weeks
- Managers say "it's nice to have but not game-changing"
- Cannot establish causal link between usage and outcomes
- Improvements are marginal and not worth the cost

---

## Phase 3: Value Proposition Validation (Weeks 13-20)

### Hypothesis 3: Restaurants will convert from pilot to paid subscription

**What we believe:**
- If we deliver results, restaurants will pay full price
- Early pilots will become case studies and references
- Word-of-mouth will generate additional leads

**How to test:**
- At end of 8-week pilot, present results and pricing
- Ask for commitment to 6-12 month contract
- Offer early adopter discount (20-30%) in exchange for case study

**Success criteria:**
- 2 out of 3 pilots convert to paid
- Average contract value: $5K-10K annually
- Willingness to provide testimonial and reference

**Questions to ask at conversion:**
- "Based on results, is this worth $20/user/month to you?"
- "What ROI did you see? Can you quantify it?"
- "Would you recommend this to other restaurants?"
- "What would make this a 'must-have' vs. 'nice-to-have'?"

**Invalidation signals:**
- "We liked it but can't justify the cost"
- "We'll keep using it if it's free"
- Results were positive but not compelling enough
- Budget constraints or approval issues

---

## Phase 4: Scaling Validation (Weeks 21-40)

### Hypothesis 4: We can acquire customers profitably and scale

**What we believe:**
- Can acquire customers for <$2K CAC (Customer Acquisition Cost)
- LTV:CAC ratio of 3:1 or better
- Churn rate <10% monthly
- Can onboard customers without unsustainable manual effort

**How to test:**
- Track CAC across channels (events, direct outreach, referrals)
- Measure time-to-value and onboarding effort
- Calculate LTV based on pilot retention and contract values
- Identify most efficient acquisition channels

**Success criteria:**
- CAC: <$2,000 per customer
- LTV: $20K+ (3+ years at $600/month with some growth)
- Gross margin: 70%+ after infrastructure costs
- Onboarding time: <10 hours per customer (eventually <2 hours)

---

## Hypothesis Testing Tracker

Use this table to track each hypothesis test:

| Hypothesis | Test Method | Start Date | End Date | Success Criteria | Result | Decision |
|------------|-------------|------------|----------|------------------|--------|----------|
| Fine dining has training pain | 30-50 interviews | TBD | TBD | 70%+ confirm top-3 problem | TBD | TBD |
| Will pay $15-25/user | Pricing interviews | TBD | TBD | 10+ interested, 2-3 LOIs | TBD | TBD |
| Servers will use platform | 8-week pilot | TBD | TBD | 70%+ use 3+ times in month 1 | TBD | TBD |
| Platform improves outcomes | Pilot metrics tracking | TBD | TBD | 30% error reduction OR 10% sales lift | TBD | TBD |
| Pilots convert to paid | End of pilot offer | TBD | TBD | 2/3 convert at target price | TBD | TBD |
| Can scale profitably | First 10 customers | TBD | TBD | CAC <$2K, LTV >$15K | TBD | TBD |

---

## Pivot Triggers

**When to pivot the customer segment:**
- Cannot find 30 fine dining restaurants with training pain in 2 months
- Willingness to pay is consistently below $10/user
- Other segment shows 10x more interest (e.g., casual dining chains)

**When to pivot the value proposition:**
- Restaurants care more about X feature than menu knowledge quizzes
- End users want different primary benefit
- Different pain point emerges as more critical

**When to pivot the revenue model:**
- Per-user pricing is barrier to adoption
- Different pricing structure gets more buy-in
- Need to bundle with other services to justify price

**When to pivot the product:**
- MVP doesn't improve measurable outcomes after 3 pilot iterations
- Different product approach tests better in interviews
- Technical approach (AI content generation) is not feasible

**When to pivot entirely:**
- Cannot validate problem across 50+ interviews
- Cannot get a single pilot customer after 6 months
- Pilots show no measurable improvement after good-faith effort
- Economics never work (CAC too high, churn too high, price too low)

---

## Key Lean Startup Principles

1. **Get out of the building** - Talk to customers constantly
2. **Build-Measure-Learn** - Minimum viable tests, rapid iteration
3. **Validated learning** - Every test should teach you something
4. **Innovation accounting** - Track actionable metrics, not vanity metrics
5. **Pivot or persevere** - Make conscious decisions based on data

---

## Next Actions

**Week 1:**
1. Create customer interview schedule (target 10 interviews)
2. Draft interview script based on questions above
3. Reach out to restaurant contacts for introductions
4. Set up simple tracking spreadsheet for interview insights

**Week 2-4:**
5. Conduct 30-50 interviews
6. Synthesize findings in shared doc
7. Map common pain points and themes
8. Test pricing hypothesis with subset of interviews

**Week 5-6 (if validated):**
9. Draft simple product spec for MVP quiz platform
10. Get 2-3 LOIs for pilot from best-fit restaurants
11. Build absolute minimum viable product
12. Plan pilot launch and metrics tracking

**Stay lean. Test fast. Learn constantly.**

---

*Last Updated: 2026-01-08*
