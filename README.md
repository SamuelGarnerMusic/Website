# Samuel Garner — Composer Portfolio

One-page site: landing area with name/title/photo, a Music section with your ReelCrafter embed, a Bio section, a Projects list, and a contact form. Plain HTML/CSS/JS — no build step, no frameworks.

## 1. Photos

All three photo spots are already filled in with the images you provided — hero, bio, and contact. If you ever want to swap one out later, just replace the file in `assets/images/` (keeping the same filename) or update the `<img src="...">` path in `index.html`.

## 2. Turn on the contact form

The form currently posts to a placeholder URL. It won't work until you connect it to a real form backend — GitHub Pages only serves static files, it can't process form submissions on its own. Two free options:

**Formspree** (what's wired up by default)
1. Go to formspree.io and create a free account (50 submissions/month, no card required).
2. Create a new form, copy the endpoint it gives you (looks like `https://formspree.io/f/xxxxxxxx`).
3. In `index.html`, replace `YOUR_FORM_ID` in the `<form action="...">` line with that endpoint.
4. Formspree emails you a confirmation link the first time — click it once, then the form is live.

**Web3Forms** (no account required, 250 free submissions/month)
1. Go to web3forms.com and generate an access key with just your email — no signup.
2. Swap the form's `action` for `https://api.web3forms.com/submit` and add a hidden field: `<input type="hidden" name="access_key" value="YOUR_KEY">`.

## 3. Update Projects

Each entry in the Projects section is one `<li class="credit">` block in `index.html` — role, title, and category/year. The 12 credits there now are yours; edit the text in place, duplicate a block to add more, or delete ones you don't need.

## 4. Put it on GitHub Pages (free hosting)

1. Create a free GitHub account at github.com if you don't have one.
2. Create a new **public** repository (name it anything, e.g. `portfolio`).
3. On the repo page, **Add file → Upload files**, drag in `index.html`, the `css/`, `js/`, and `assets/` folders, and `README.md`, then commit.
4. Go to **Settings → Pages**.
5. Under **Build and deployment → Source**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
6. Wait a minute, refresh — your live URL is `https://yourusername.github.io/portfolio/`.

## 5. Buy a domain

GitHub Pages hosting is free; a domain name isn't — roughly $10–20/year. Registrars that don't mark up the price or push upsells:

- **Cloudflare Registrar** — sells at wholesale cost.
- **Namecheap** or **Porkbun** — cheap, free WHOIS privacy included.

## 6. Point your domain at GitHub Pages

In your registrar's DNS settings:

**Root/apex domain (`samuelgarner.com`):** add four **A records** for `@` pointing to:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**`www.samuelgarner.com` (recommended alongside the root):** add a **CNAME record** for `www` pointing to `yourusername.github.io`.

Back in the repo's **Settings → Pages**, enter your domain in the Custom domain field and save. Once GitHub shows a green "DNS check successful," tick **Enforce HTTPS** for a free SSL certificate. DNS changes can take a few minutes to 24 hours to propagate.

## Notes

- No build tools, no npm — just static files. Preview locally by double-clicking `index.html`.
- Animations respect `prefers-reduced-motion`.
