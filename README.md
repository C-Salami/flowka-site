# Flowka Lab — Personal Portfolio

Personal portfolio & digital business card for Hamza Salami.  
Live at [flowka.dev](https://flowka.dev)

## Project Structure

```
flowka-site/
├── index.html        # Main portfolio page
├── card.html         # QR digital business card
├── CNAME             # Custom domain config for GitHub Pages
├── images/
│   ├── sunset.jpg    # Profile photo (hero)
│   ├── portrait.jpg  # Portrait photo
│   ├── mountains.jpg # Travel photo
│   ├── hiking.jpg    # Hiking photo
│   └── qr-code.svg   # QR code → flowka.dev
└── README.md
```

## Deployment — GitHub Pages + Namecheap

### Step 1: Create GitHub Repo

1. Go to [github.com/new](https://github.com/new)
2. Name: `flowka-site` (or `Flowka-lab.github.io` for the org)
3. Public repo, no README (we have one)
4. Push the code:

```bash
cd flowka-site
git init
git add .
git commit -m "Initial commit — Flowka Lab portfolio"
git branch -M main
git remote add origin https://github.com/C-Salami/flowka-site.git
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. Go to repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. Click **Save**
5. Wait 1-2 minutes → your site is live at `c-salami.github.io/flowka-site`

### Step 3: Buy Domain on Namecheap

1. Go to [namecheap.com](https://www.namecheap.com)
2. Search for `flowka.dev`
3. Add to cart → checkout (~$12/year)
4. Complete purchase

### Step 4: Configure DNS on Namecheap

1. Go to **Domain List** → click **Manage** next to `flowka.dev`
2. Go to **Advanced DNS** tab
3. Delete any existing records
4. Add these **4 A Records** (point to GitHub Pages):

| Type | Host | Value | TTL |
|------|------|-------|-----|
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |

5. Add a **CNAME Record**:

| Type | Host | Value | TTL |
|------|------|-------|-----|
| CNAME | www | c-salami.github.io. | Automatic |

### Step 5: Connect Domain to GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Custom domain**, type: `flowka.dev`
3. Click **Save**
4. Wait for DNS check (can take up to 24 hours, usually 10-30 min)
5. Check **Enforce HTTPS** once available

### Step 6: Verify

- Visit `https://flowka.dev` — should show your portfolio
- Visit `https://flowka.dev/card.html` — should show your QR business card
- Share the QR code with people at meetings!

## Updating Content

Just edit the HTML files and push to GitHub. Changes deploy automatically in ~1 minute.

```bash
git add .
git commit -m "Update content"
git push
```

## QR Code

The QR code in `images/qr-code.svg` points to `https://flowka.dev`.  
If you change your domain, regenerate it at [qr-code-generator.com](https://www.qr-code-generator.com/) or using the Python `qrcode` library.

## Future Ideas

- Add blog posts (markdown → HTML) for each Flowka Lab project
- Add Google Analytics tracking
- Add a downloadable PDF CV
- Expand project pages with individual detail pages
