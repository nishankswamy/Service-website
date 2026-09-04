# TechFix Pro — Website

Single-page static website for a laptop sales & repair service provider: laptop sales, software upgrades, electronic repairs, laptop servicing, antivirus installation, and free initial installation setup for laptops bought online (Amazon, Flipkart, etc.), plus a Contact/Support section.

`index.html` is fully self-contained (HTML/CSS/JS in one file) — no build step required.

## Push to GitHub

The remote is already set to `https://github.com/nishankswamy/Service-website.git`. Create the empty repo on GitHub first (name: "Service website" — GitHub will turn the space into a hyphen, giving the URL above — don't add a README/license there), then from this folder run:

```bash
git branch -M main
git push -u origin main
```

You'll be prompted to sign in to GitHub (browser popup or a personal access token) the first time — that part has to happen on your machine.

## Deploy for free with GitHub Pages

1. Push this repo to GitHub (see above).
2. On GitHub: **Settings → Pages → Source** → select the `main` branch, `/ (root)` folder → **Save**.
3. Your site will be live at `https://nishankswamy.github.io/Service-website/` within a few minutes.
4. To use a custom domain, add a `CNAME` file with your domain name, and point your domain's DNS to GitHub Pages per [GitHub's custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Manage the "Laptops in Stock" inventory yourself (no coding)

The inventory section on the homepage reads from a Google Sheet you control, so you can add/remove/edit laptops any time without touching code. Until you set this up, it shows sample placeholder listings.

**One-time setup (~5 minutes):**

1. Create a new Google Sheet. In row 1, add these exact column headers: `Model | Price | Specs | Image URL | In Stock`
2. Add one row per laptop, e.g. `Dell Inspiron 15 | ₹42,999 | 15.6" FHD, 8GB RAM, 512GB SSD | (leave blank or paste an image link) | Yes`
3. Go to **File → Share → Publish to web**, choose the sheet, format **CSV**, click **Publish**, and copy the link it gives you.
4. Open `index.html`, find the line `const INVENTORY_CSV_URL = "";` near the bottom, and paste your link between the quotes.
5. Save, commit, and push — the live site will now pull directly from your sheet.

**To add a laptop as a simple form instead of editing the spreadsheet directly:**

1. Create a Google Form with these fields, in this order: Model (short answer), Price (short answer), Specs (short answer), Image URL (short answer, optional), In Stock (multiple choice: Yes/No).
2. In the Form's **Responses** tab, click the Sheets icon to link responses to the same Google Sheet from step 1 above (or a new one — just make sure the column order matches).
3. Bookmark the Form link — that's your "add new laptop" form. Every submission appears as a new row, and the website picks it up automatically on next page load.
4. To remove or edit a laptop, delete/edit its row directly in the Sheet.

## Other things worth setting up (optional, need your own accounts)

- **Google Business Profile** (business.google.com) — this is what makes you show up on Google Maps and local search, separate from this website. Worth setting up regardless of the website.
- **Google Analytics** (analytics.google.com) — free visitor tracking; once you have a Measurement ID, I can add the tracking snippet.
- **Live chat widget** (e.g. Tawk.to, free) — an alternative to the WhatsApp button for website visitors who prefer typing on the site itself.
- **Appointment booking** (e.g. Calendly, free tier available) — lets customers pick a slot directly instead of just messaging; can be embedded once you have an account.

## Before going live

- Replace "TechFix Pro" with your real business name throughout `index.html`, `privacy.html`, and `terms.html`.
- Update the placeholder prices in the Pricing section (`#pricing`) with your real rates.
- Replace the sample reviews in the Reviews section with real customer feedback.
- Fill in the `privacy.html` and `terms.html` template sections marked with `[...]`.
- The contact form (`#supportForm`) currently only shows a success message locally — connect it to a form backend (e.g. Formspree, EmailJS) or your own server if you want submissions emailed to you.
- Contact details currently shown: +91 98459 26131, lakshmipriya12.g1@gmail.com, Bannerghatta Road, Bangalore.
