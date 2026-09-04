# TechFix Pro — Website

Single-page static website for a laptop sales & repair service provider: laptop sales, software upgrades, electronic repairs, laptop servicing, antivirus installation, and free initial installation setup for laptops bought online (Amazon, Flipkart, etc.), plus a Contact/Support section.

`index.html` is fully self-contained (HTML/CSS/JS in one file) — no build step required.

## Push to GitHub

```bash
git remote add origin https://github.com/<your-username>/<your-repo>.git
git branch -M main
git push -u origin main
```

(Create the empty repo on GitHub first, without a README, then run the above from this folder.)

## Deploy for free with GitHub Pages

1. Push this repo to GitHub (see above).
2. On GitHub: **Settings → Pages → Source** → select the `main` branch, `/ (root)` folder → **Save**.
3. Your site will be live at `https://<your-username>.github.io/<your-repo>/` within a few minutes.
4. To use a custom domain, add a `CNAME` file with your domain name, and point your domain's DNS to GitHub Pages per [GitHub's custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Before going live

- Replace "TechFix Pro" with your real business name throughout `index.html`.
- The contact form (`#supportForm`) currently only shows a success message locally — connect it to a form backend (e.g. Formspree, EmailJS) or your own server if you want submissions emailed to you.
- Contact details currently shown: +91 98459 26131, lakshmipriya12.g1@gmail.com, Bannerghatta Road, Bangalore.
