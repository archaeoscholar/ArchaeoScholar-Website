# ArchaeoScholar — Complete Deployment Guide

## Your Files

You need these files (all already created):

```
archaeoscholar/
├── index.html       ← Your website
├── 404.html         ← Custom "page not found" page
├── CNAME            ← Tells GitHub to use archaeoscholar.com
├── robots.txt       ← Helps Google find your site
├── sitemap.xml      ← Helps Google index your pages
└── images/          ← Create this folder for your photos
    ├── field-1.jpg
    ├── field-2.jpg
    ├── mahabodhi.jpg
    ├── nalanda.jpg
    └── ... (all your site photos)
```

---

## STEP 1 — Buy the Domain

1. Go to **hostinger.in**
2. Search for `archaeoscholar.com`
3. Buy **only the domain** (no hosting plan needed)
4. Cost: ~₹700–900/year

---

## STEP 2 — Get GitHub Pro for Free (Private Repo)

This is the key step to keep your code private.

1. Go to **github.com** → Sign up (if you don't have an account)
2. Go to **education.github.com/benefits**
3. Click **"Get student benefits"** (it works for faculty too)
4. Verify with your **Magadh University email**
5. Once approved (usually 1–7 days), you get **GitHub Pro** for free

**What this gives you:**
- Private repositories (nobody can see your code)
- GitHub Pages works from private repos
- Your website loads normally — zero trace of GitHub

**If you can't wait for education verification:**
GitHub Pro costs ~$4/month (~₹330/month). You can start with this
and switch to the free education plan once approved.

---

## STEP 3 — Create a Private Repository

1. Log into **github.com**
2. Click the green **"New"** button (top left)
3. Settings:
   - Repository name: `archaeoscholar` (or anything you like)
   - Description: "ArchaeoScholar website" (optional)
   - ✅ Select **Private**
   - ✅ Check "Add a README file"
4. Click **"Create repository"**

---

## STEP 4 — Upload Your Files

1. In your new repo, click **"Add file"** → **"Upload files"**
2. Drag and drop these files:
   - `index.html`
   - `404.html`
   - `CNAME`
   - `robots.txt`
   - `sitemap.xml`
3. Scroll down, click **"Commit changes"**

### Adding your images:
1. Click **"Add file"** → **"Create new file"**
2. Type `images/.gitkeep` as the filename (this creates the images folder)
3. Click **"Commit changes"**
4. Navigate into the `images` folder
5. Click **"Add file"** → **"Upload files"**
6. Drag and drop all your site photos
7. Click **"Commit changes"**

---

## STEP 5 — Enable GitHub Pages

1. Go to your repo → **Settings** (top menu bar)
2. In the left sidebar, click **"Pages"**
3. Under **"Source"**, select:
   - **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
4. Click **Save**
5. Under **"Custom domain"**, type: `archaeoscholar.com`
6. Click **Save**
7. ✅ Check **"Enforce HTTPS"** (may appear after a few minutes)

---

## STEP 6 — Connect Your Domain (Hostinger DNS)

Log into your Hostinger account:

1. Go to **Domains** → `archaeoscholar.com` → **DNS / Nameservers**
2. **Delete** any existing A records for `@`
3. Add these 4 **A records**:

   | Type | Name | Value             | TTL  |
   |------|------|-------------------|------|
   | A    | @    | 185.199.108.153   | 3600 |
   | A    | @    | 185.199.109.153   | 3600 |
   | A    | @    | 185.199.110.153   | 3600 |
   | A    | @    | 185.199.111.153   | 3600 |

4. Add this **CNAME record** for www:

   | Type  | Name | Value                          | TTL  |
   |-------|------|--------------------------------|------|
   | CNAME | www  | YOUR-GITHUB-USERNAME.github.io | 3600 |

   (Replace YOUR-GITHUB-USERNAME with your actual GitHub username)

5. **Wait 15–60 minutes** for DNS to propagate

---

## STEP 7 — Verify Everything Works

Open your browser and check:

- ✅ `https://archaeoscholar.com` — shows your site
- ✅ `https://www.archaeoscholar.com` — also works
- ✅ Padlock icon shows (HTTPS working)
- ✅ `https://archaeoscholar.com/nonexistent` — shows your 404 page
- ✅ Going to `YOUR-USERNAME.github.io/archaeoscholar` redirects to archaeoscholar.com

---

## STEP 8 — Set Up Professional Email (Free)

Since you're not using Hostinger hosting, use **Zoho Mail** for free email:

1. Go to **zoho.com/mail** → Sign up for the **Free Plan**
2. Add domain: `archaeoscholar.com`
3. Zoho will ask you to add **MX records** in Hostinger DNS:

   | Type | Name | Priority | Value         |
   |------|------|----------|---------------|
   | MX   | @    | 10       | mx.zoho.in    |
   | MX   | @    | 20       | mx2.zoho.in   |
   | MX   | @    | 50       | mx3.zoho.in   |

   (Follow Zoho's exact setup wizard — values may vary slightly)

4. Create your email: `contact@archaeoscholar.com`
5. Access it at **mail.zoho.in**

---

## How to Add Photos to Your Site

Once your photos are uploaded to the `images/` folder in your repo,
update the HTML to use them. Replace placeholders like this:

**For hero gallery photos:**
```html
<!-- Find this in index.html -->
<div class="gallery-placeholder">[ Group tour photo at Nalanda ]</div>

<!-- Replace with -->
<img src="images/field-nalanda.jpg" alt="Group tour at Nalanda">
```

**For site photo cards:**
```html
<!-- Find this -->
<div class="site-card-placeholder" style="...">[ photo ]</div>

<!-- Replace with -->
<img class="site-card-img" src="images/mahabodhi.jpg" alt="Mahabodhi Temple">
```

**Recommended image sizes:**
- Hero gallery photos: 800×600px (landscape)
- Site cards: 400×400px (square)
- Portrait photo: 600×800px (portrait)
- Format: JPEG, compressed to ~80-150KB each

---

## Updating Your Site Later

1. Go to your GitHub repo
2. Click on `index.html`
3. Click the ✏️ pencil icon (Edit)
4. Make your changes
5. Click **"Commit changes"**
6. Your site updates within 1–2 minutes

For uploading new photos:
1. Navigate to the `images/` folder
2. Click **"Add file"** → **"Upload files"**
3. Drag and drop new images
4. Commit — they're live in 1–2 minutes

---

## Privacy Summary

| What visitors see          | What's hidden              |
|----------------------------|----------------------------|
| archaeoscholar.com         | Your GitHub username        |
| Your website content       | Your repository             |
| Your photos and text       | Your source code            |
| HTTPS padlock              | That GitHub hosts it        |

With a **private repo**, there is absolutely no public connection
between your website and GitHub. Nobody can see your code, your
commit history, or even know that GitHub is involved.

---

## Cost Summary

| Item                    | Cost             |
|-------------------------|------------------|
| Domain (Hostinger)      | ~₹700–900/year   |
| Hosting (GitHub Pages)  | Free              |
| Private repo (GitHub)   | Free (education)  |
| SSL Certificate         | Free              |
| Email (Zoho Mail)       | Free              |
| **Total**               | **~₹700–900/year**|

---

## Troubleshooting

**Site shows 404 after setup:**
- DNS takes up to 60 minutes. Wait and try again.
- Check that CNAME file contains exactly `archaeoscholar.com`
- Verify A records are correct in Hostinger DNS panel

**No HTTPS / no padlock:**
- Go to repo Settings → Pages → check "Enforce HTTPS"
- May take up to 24 hours after DNS propagation

**GitHub Education not approved yet:**
- You can start with a public repo (free) and make it private later
- Or pay for GitHub Pro (~₹330/month) temporarily

**Images not loading:**
- Check filenames are exact match (case-sensitive)
- Ensure images are in the `images/` folder, not root
- File names should not have spaces (use hyphens instead)

---

If you get stuck on any step, bring the error or screenshot
back to this chat and we'll sort it out.
