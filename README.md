# AgroKawak Website

A full-featured e-commerce website for AgroKawak mushroom products.  
**Pure frontend React app — no server or database required.**

---

## 🚀 Quick Start (Local Development in VS Code)

### Requirements
- **Node.js v18+** — download from https://nodejs.org  
  *(To check: open a terminal and run `node -v`)*

### Steps

```bash
# 1. Open this folder in VS Code
# 2. Open the terminal in VS Code (Ctrl + ` or View → Terminal)

# 3. Install dependencies (run once)
npm install

# 4. Start the development server
npm run dev
```

Then open your browser at **http://localhost:3000** 🎉

The page auto-reloads whenever you save a file.

---

## 🏗️ Build for Production

```bash
npm run build
```

This creates a `dist/` folder containing all the static files ready to upload.

---

## 🌐 Deploy to Any Hosting

### Option A — Netlify (recommended, free)
1. Go to https://netlify.com and create a free account
2. Click **"Add new site" → "Deploy manually"**
3. Drag and drop the `dist/` folder
4. Done! Netlify gives you a live URL instantly

For auto-deploy from GitHub:
- Connect your repo → Build command: `npm run build` → Publish directory: `dist`

---

### Option B — cPanel / Shared Hosting (any domain host)
1. Run `npm run build` on your computer
2. Open your hosting control panel (cPanel, Plesk, etc.)
3. Go to **File Manager** → navigate to `public_html`
4. Upload **all contents** of the `dist/` folder to `public_html`
5. Done!

> **Important for cPanel:** Create a file called `.htaccess` in `public_html` with this content:
> ```
> <IfModule mod_rewrite.c>
>   RewriteEngine On
>   RewriteBase /
>   RewriteRule ^index\.html$ - [L]
>   RewriteCond %{REQUEST_FILENAME} !-f
>   RewriteCond %{REQUEST_FILENAME} !-d
>   RewriteRule . /index.html [L]
> </IfModule>
> ```
> This ensures page refresh works on all routes.

---

### Option C — Vercel (free)
1. Go to https://vercel.com and sign up with GitHub
2. Import your repository
3. Framework preset: **Vite** (auto-detected)
4. Deploy — done!

---

### Option D — Cloudflare Pages (free)
1. Go to https://pages.cloudflare.com
2. Connect your Git repository
3. Build command: `npm run build`
4. Output directory: `dist`

---

## 🔐 Admin Panel

Visit `/admin-login` on your site (e.g. http://localhost:3000/admin-login).

**Default credentials:**
- Username: `admin`
- Password: `agrokawak2024`

⚠️ **Change the password immediately after first login:**  
Admin → Settings → Admin Password

The admin panel lets you:
- ✅ Add/edit/delete products
- ✅ Add/edit/delete blog posts
- ✅ View and update orders
- ✅ View contact messages and community signups
- ✅ Update site settings (phone, email, address, WhatsApp number)

---

## 📦 How Orders Work

1. Customer fills the checkout form → pays via UPI QR code
2. Customer uploads payment screenshot → clicks **Confirm Order**
3. A **WhatsApp message** automatically opens with the full order details — the customer sends it to you
4. The customer also sees a confirmation page with their **invoice** (downloadable as PDF)

**To receive WhatsApp notifications:**  
Go to Admin → Settings → update the **WhatsApp Number** field to your number  
(format: country code + number, e.g. `918877810916` for +91 88778 10916)

---

## 💾 How Data is Stored

All data (products, posts, orders, contacts) is stored in the browser's **localStorage**.

- **Products & posts:** Seeded from built-in defaults on first load. Editable via the admin panel.
- **Orders:** Saved locally when a customer places an order. Use WhatsApp to receive order notifications.
- **Settings:** Saved in localStorage, editable from the admin panel.

> 💡 To back up your admin data, you can export localStorage using the browser console:
> `copy(JSON.stringify(localStorage))`

---

## 📱 Updating Your UPI QR Code

Replace the file `public/upi-qr.png` with your own QR code image before building.

---

## 🛠️ Project Structure

```
AgroKawak/
├── public/             Static assets (favicon, QR code, images)
├── src/
│   ├── components/     Navbar, Footer, ProductCard, etc.
│   ├── lib/
│   │   ├── store.ts    All data persistence (localStorage)
│   │   └── cart.tsx    Shopping cart state
│   ├── pages/          All page components
│   └── App.tsx         Routing
├── package.json        Dependencies & scripts
├── vite.config.ts      Build configuration
└── netlify.toml        Netlify deployment config
```

---

## 🤝 Support

For any issues, WhatsApp: +91 88778 10916 or email: dkshmr7@gmail.com
