# Landing Page Deployment Guide

Your professional landing page is ready! This guide will help you deploy it to your custom domain.

## What I've Created

**File:** `index.html` - A single-page website with:
- Professional design with gradient hero section
- Clear value proposition
- Problem/solution framework
- Results-focused stats section
- How it works explanation
- Strong call-to-action for customer interviews
- Mobile responsive design
- Zero dependencies (no frameworks, loads instantly)

## Preview Locally (Optional)

To preview before deploying:

```bash
cd "/Users/cameronpowell/Desktop/Restaurant Software"
open index.html
```

This will open the page in your browser so you can see how it looks.

---

## Deployment Options

### Option 1: GitHub Pages (Recommended - Free & Easy)

**Why:** Free hosting, automatic SSL, fast, integrates with your existing repo

**Steps:**

1. **Commit the landing page to your repository**
   ```bash
   cd "/Users/cameronpowell/Desktop/Restaurant Software"
   git add index.html LANDING_PAGE_DEPLOYMENT.md
   git commit -m "Add professional landing page for ServingSmart AI"
   git push
   ```

2. **Enable GitHub Pages**
   - Go to your repository: https://github.com/campow22/restaurant-software
   - Click "Settings" tab
   - Scroll to "Pages" in left sidebar
   - Under "Source", select "Deploy from a branch"
   - Select branch: `main`
   - Select folder: `/ (root)`
   - Click "Save"

3. **Your site will be live at:**
   - `https://campow22.github.io/restaurant-software/`

4. **Connect your custom domain**
   - In GitHub Pages settings, add custom domain: `www.servingsmart-ai.com` (or your actual domain)
   - Click "Save"
   - GitHub will give you DNS instructions

5. **Update DNS in Google Domains**
   - Go to [Google Domains](https://domains.google.com)
   - Select your domain
   - Go to DNS settings
   - Add these records:

   **For www.servingsmart-ai.com:**
   ```
   Type: CNAME
   Name: www
   Data: campow22.github.io
   ```

   **For servingsmart-ai.com (root domain):**
   ```
   Type: A
   Name: @
   Data: 185.199.108.153

   Type: A
   Name: @
   Data: 185.199.109.153

   Type: A
   Name: @
   Data: 185.199.110.153

   Type: A
   Name: @
   Data: 185.199.111.153
   ```

6. **Wait for DNS propagation (15 minutes - 24 hours)**
   - Your site will be live at your custom domain
   - GitHub automatically provisions SSL certificate (HTTPS)

**Timeline:** 30 minutes of work, 1-24 hours for DNS

---

### Option 2: Netlify (Free, Easiest)

**Why:** Drag-and-drop deployment, automatic SSL, fast

**Steps:**

1. **Go to [Netlify](https://www.netlify.com)**
2. **Sign up with GitHub** (links to your repo automatically)
3. **Click "Add new site" → "Import an existing project"**
4. **Select your repository:** `restaurant-software`
5. **Deploy settings:**
   - Build command: (leave empty)
   - Publish directory: `/`
   - Click "Deploy"
6. **Site is live** at a Netlify URL (e.g., `random-name-12345.netlify.app`)
7. **Add custom domain:**
   - Site settings → Domain management → Add custom domain
   - Enter: `www.servingsmart-ai.com` (or your domain)
   - Follow Netlify's DNS instructions
8. **Update DNS in Google Domains** with Netlify's nameservers

**Timeline:** 10 minutes

---

### Option 3: Google Sites (Point-and-Click, No Code)

**Why:** Already included with Google Workspace, super simple

**Steps:**

1. **Go to [Google Sites](https://sites.google.com)**
2. **Create new site**
3. **Problem:** Google Sites doesn't easily let you use custom HTML
4. **Alternative:** Manually recreate the design using Google Sites blocks

**Verdict:** Not recommended - you'd lose the custom design

---

### Option 4: Firebase Hosting (Google's Platform)

**Why:** Google's hosting, free tier, integrates with Google Workspace

**Steps:**

1. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**
   ```bash
   cd "/Users/cameronpowell/Desktop/Restaurant Software"
   firebase login
   firebase init hosting
   ```

3. **Configure:**
   - Create new project or use existing
   - Public directory: `.` (current directory)
   - Single-page app: No
   - Don't overwrite index.html

4. **Deploy**
   ```bash
   firebase deploy
   ```

5. **Connect custom domain** in Firebase Console

**Timeline:** 20 minutes

---

## My Recommendation

**Use GitHub Pages (Option 1)** because:
- ✅ Free forever
- ✅ You're already using GitHub for your repo
- ✅ Automatic deployments when you update the file
- ✅ Free SSL certificate
- ✅ Fast global CDN
- ✅ Custom domain support

**Quick Start:**
1. Push the index.html file (already done above)
2. Enable GitHub Pages (2 minutes)
3. Connect domain (10 minutes)
4. Wait for DNS (passive)

---

## Updating Your Landing Page Content

To customize the page with your specific details:

### 1. Update Email Address

In `index.html`, find and replace:
```html
cameron@servingsmart-ai.com
```
With your actual email address.

### 2. Update Statistics (After Customer Discovery)

Once you have pilot data, update the stats section:
```html
<div class="stat-number">50%</div>
<div class="stat-label">Faster Training</div>
```

Change to your actual results.

### 3. Add Calendly Link (Optional)

Instead of mailto link, you can use Calendly for easier scheduling:

1. Create free Calendly account: https://calendly.com
2. Set up a "15-minute interview" event
3. Replace this line in index.html:
   ```html
   <a href="mailto:cameron@servingsmart-ai.com?subject=Customer Discovery Interview Request" class="cta-button">Schedule a 10-Minute Interview</a>
   ```

   With:
   ```html
   <a href="https://calendly.com/your-link/15min" class="cta-button" target="_blank">Schedule a 10-Minute Interview</a>
   ```

### 4. Track Visitors (Optional)

Add Google Analytics to see how many people visit:

1. Create Google Analytics account
2. Get tracking code
3. Add before `</head>` in index.html

---

## Testing Checklist

Before going live, test:

- [ ] Email link works correctly
- [ ] Page loads on mobile (use phone)
- [ ] All sections display properly
- [ ] Colors and branding look good
- [ ] Call-to-action buttons are clear
- [ ] Links work
- [ ] No typos or errors

---

## Next Steps After Deployment

1. **Add URL to email templates**
   - Update EMAIL_TEMPLATES.md with your live URL
   - Add "Learn more: https://www.servingsmart-ai.com" to emails

2. **Create email signature**
   ```
   Cameron Powell
   Founder, ServingSmart AI
   https://www.servingsmart-ai.com
   cameron@servingsmart-ai.com
   ```

3. **Share link in interviews**
   - Send to prospects after calls
   - Include in follow-up emails
   - Post on LinkedIn

4. **A/B test messaging**
   - Track which value props resonate
   - Update based on customer feedback
   - Iterate based on interview insights

---

## Quick Deploy Command

If you're ready to deploy to GitHub Pages right now:

```bash
cd "/Users/cameronpowell/Desktop/Restaurant Software"
git add index.html LANDING_PAGE_DEPLOYMENT.md
git commit -m "Add professional landing page for ServingSmart AI"
git push
```

Then go to: https://github.com/campow22/restaurant-software/settings/pages

And enable GitHub Pages!

---

## Need Help?

Let me know if you:
- Want me to update any content on the page
- Need help with DNS configuration
- Want to add features (waitlist form, video, testimonials)
- Have issues with deployment

Your landing page is professional, conversion-focused, and ready to go! 🚀
