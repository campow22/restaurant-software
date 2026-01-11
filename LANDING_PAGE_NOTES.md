# Landing Page - What's Different

## Major Changes from Original Version

### Tone & Positioning
- **Before:** Polished product, ready to buy
- **Now:** Early-stage, transparent research phase
- **Message:** "Help us build this" vs. "Buy this now"

### Content Updates

**Hero Section:**
- Headline: "Building the Future of Restaurant Training"
- Subheadline emphasizes customer discovery
- Primary CTA: Book interview (Calendly)
- Secondary CTA: Join newsletter

**New Sections Added:**
1. **Why I'm Building This** - Your founder story with Mission Hill Winery & Wildlight experience
2. **Industry Pain Statistics** - Real restaurant training costs (8-12 weeks, 75% turnover, $5,864 per turnover, $500-2K monthly errors)
3. **Timeline/Roadmap** - Shows current phase with future milestones
4. **How You Can Help** - 4 ways to participate
5. **FAQ** - Addresses stage, pricing, why talk to you, AI replacement concerns
6. **Newsletter Signup** - Email waitlist

**Removed:**
- Product success stats (50% faster, 40% fewer errors)
- "Results that matter" claims
- Over-confident language

**Kept (But Reframed):**
- Problem pain points (now research questions)
- Vision for solution (as "What We're Building")
- Value proposition (aspirational, not proven)

### CTAs

**Primary:** Calendly - https://calendly.com/cameron-p-servingsmart-ai/30min
- "Book a 15-Minute Interview"
- "Schedule Your Interview"
- "Share Your Challenges"

**Secondary:** Email - cameron.p@servingsmart-ai.com
- "Email Me Instead"
- For general inquiries

**Tertiary:** Newsletter signup
- Formspree integration (needs setup)

### Design Changes
- Softer purple color scheme (#4f46e5 vs #2563eb)
- More whitespace, less aggressive
- Timeline visualization with "We Are Here" marker
- Red stats callout box for industry pain
- Transparent about being student/aspiring entrepreneur

## Next Steps to Complete

### 1. Newsletter Form Setup

The form currently points to: `https://formspree.io/f/YOUR_FORM_ID`

**To set up:**
1. Go to [Formspree.io](https://formspree.io)
2. Sign up (free plan works)
3. Create new form
4. Get your form ID
5. Replace `YOUR_FORM_ID` in index.html line 790:
   ```html
   <form class="newsletter-form" action="https://formspree.io/f/YOUR_ACTUAL_ID" method="POST">
   ```

**Alternative:** Use Mailchimp, ConvertKit, or Google Forms
- More advanced email marketing features
- Automated welcome sequences
- Better for building email list

### 2. Deploy to Your Domain

Follow [LANDING_PAGE_DEPLOYMENT.md](LANDING_PAGE_DEPLOYMENT.md) to deploy to servingsmart-ai.com

**Quick deploy via GitHub Pages:**
1. Go to https://github.com/campow22/restaurant-software/settings/pages
2. Source: Deploy from branch `main`, folder `/ (root)`
3. Save
4. Add custom domain: `www.servingsmart-ai.com`
5. Update DNS in Google Domains (instructions in deployment guide)

### 3. Update Email Templates

Replace placeholder company name in [EMAIL_TEMPLATES.md](EMAIL_TEMPLATES.md):
- "Restaurant Training Solutions" → "ServingSmart AI"
- Add landing page URL to email signatures
- Update footer in all templates

### 4. Test Everything

Before sending to prospects:
- [ ] Preview landing page locally: `open index.html`
- [ ] Test Calendly link works
- [ ] Test email link (cameron.p@servingsmart-ai.com)
- [ ] Test newsletter form (after Formspree setup)
- [ ] View on mobile (responsive design)
- [ ] Check for typos

## Key Messages

**Problem:** Restaurant training is broken (8-12 weeks, high cost, high turnover)

**Solution Vision:** AI-powered platform that auto-generates training, empowers staff

**Stage:** Customer discovery - we're listening, not selling

**Ask:** 15-minute interview to share your training challenges

**Value Exchange:**
- Help shape the product
- Get early access
- Exclusive founding customer pricing
- Be part of the solution

## SEO & Metadata

**Title:** ServingSmart AI - Building the Future of Restaurant Training

**Description:** We're talking to restaurant managers to understand training challenges and build an AI-powered platform that empowers FOH staff.

**Keywords:** restaurant training, AI training platform, server training, restaurant staff training, menu knowledge training

## Analytics (Recommended)

Add Google Analytics to track:
- Page views
- Calendly click-through rate
- Newsletter signups
- Time on page
- Mobile vs desktop

**To add:**
1. Create Google Analytics account
2. Get tracking code
3. Add before `</head>` in index.html

## A/B Testing Ideas (Later)

Once you have traffic, test:
1. Headline variations
2. CTA button text
3. Founder bio placement
4. Industry stats presentation
5. FAQ order

## Content Updates Over Time

**After 10 interviews:**
- Add "What we're learning" section
- Update with real quotes from managers
- Show patterns emerging

**After pilot program:**
- Add results/testimonials
- Replace "What We're Building" with "What We've Built"
- Add case studies
- Update timeline

**After launch:**
- Full product page
- Pricing page
- Customer logos
- Demo videos

---

**Current Status:** Landing page is research-focused, authentic, and ready to drive customer discovery interviews.

**Next Immediate Action:** Deploy to servingsmart-ai.com domain so you can share it in emails.
