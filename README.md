# velocipartners.com

Marketing site for **Veloci Partners** — accounting and advisory for owner-led businesses.

Static site. One HTML file, no build step, no dependencies. Edit and push.

```
.
├── index.html      # the entire site (HTML + CSS + JS inline)
├── 404.html        # not-found page
├── CNAME           # custom domain for GitHub Pages
├── robots.txt      # crawler rules
├── sitemap.xml     # for Google Search Console
├── .nojekyll       # tells GitHub Pages to skip Jekyll processing
└── LAUNCH-GUIDE.md # step-by-step deploy + DNS instructions
```

---

## Push it to GitHub

The repo is already initialised with a first commit. From this folder:

```bash
git remote add origin https://github.com/YOUR_USERNAME/velocipartners-site.git
git branch -M main
git push -u origin main
```

Create the empty repo at [github.com/new](https://github.com/new) first — **don't** tick "Add a README", the repo must be empty.

If you'd rather not use the command line: install [GitHub Desktop](https://desktop.github.com), choose *Add Local Repository*, point it at this folder, and click *Publish repository*.

---

## Publish it

**Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / `root` → Save.**

Live within a minute at `https://YOUR_USERNAME.github.io/velocipartners-site/`, and at `www.velocipartners.com` once DNS is pointed (see `LAUNCH-GUIDE.md`).

Every `git push` redeploys automatically.

---

## Before you go live

- [ ] Replace `YOUR_FORM_ID` in `index.html` with your Formspree ID — **the contact form does nothing until you do**
- [ ] Replace `hello@velocipartners.com` with your real email (3 places)
- [ ] Replace `Add your number` with your phone number
- [ ] Replace or delete the placeholder quote section
- [ ] Trim the "Who We Serve" list to industries you actually serve
- [ ] Remove any claim you can't substantiate

The hero chart shows illustrative figures and is labelled "Sample". Keep that label.

---

## Editing

Everything lives in `index.html`. The CSS is in one `<style>` block at the top; the palette is at the very top in `:root`:

```css
--ink:  #0A1F33;   /* navy — backgrounds, headings */
--gold: #C8A951;   /* accent — buttons, rules, numbers */
--paper:#FBFAF7;   /* page background */
```

Change those three and the whole site reskins.

Sections are marked with comment banners (`<!-- ==== SERVICES ==== -->`) so they're easy to find, reorder or delete.

## License

© Veloci Partners. All rights reserved.
