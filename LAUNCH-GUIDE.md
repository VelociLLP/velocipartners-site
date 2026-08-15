# Veloci Partners — Launch Guide

Everything needed to take `index.html` from a file on your desktop to a live site at **www.velocipartners.com**.

Total time: about 60–90 minutes. Hosting cost: **$0**. You keep the domain at GoDaddy.

---

## Step 1 — Preview it

Double-click `index.html`. It opens in your browser. Nothing to install.

Resize the window narrow to check the mobile layout.

---

## Step 2 — Edit your details before going live

Open `index.html` in Notepad (or any text editor) and use Ctrl+F to find and replace:

| Find | Change to |
|---|---|
| `hello@velocipartners.com` | Your real email (appears twice) |
| `Add your number` | Your phone number |
| `Monday – Friday, 9:00am – 5:00pm` | Your actual hours |
| The `QUOTE` section | A real client testimonial — or delete the whole section |

**Placeholders to be aware of:**

- The chart card in the hero is labelled "Sample" — the figures are illustrative, not real client data. Leave the label on.
- The industries list under "Who We Serve" — trim it to the ones you actually serve. A shorter, honest list converts better than a long generic one.
- Don't add claims you can't back up (client counts, years in business, credentials). Accounting sites get read closely.

---

## Step 3 — Put it online (Netlify, free)

1. Go to **netlify.com** → **Sign up** (use your Google account, fastest).
2. On the dashboard, find the box that says **"Deploy manually"** / "Drag and drop your site folder here."
3. Drag the entire **`velocipartners-site`** folder onto that box.
4. Wait ~20 seconds. You get a live URL like `random-name-12345.netlify.app`.
5. Open it and confirm everything looks right.

Optional: **Site configuration → Change site name** → set it to `velocipartners`. Your temporary URL becomes `velocipartners.netlify.app`. You'll need this name in Step 4.

---

## Step 4 — Point your GoDaddy domain at it

Two routes. **Route A is easier and recommended.**

### Route A — Let Netlify run your DNS

1. In Netlify: **Domain management → Add a domain** → type `velocipartners.com` → Verify → Add.
2. Netlify shows you **four nameservers**, like `dns1.p03.nsone.net`, `dns2.p03…`, etc. Copy all four.
3. Go to **GoDaddy → My Products → Domains → velocipartners.com → DNS → Nameservers → Change**.
4. Choose **"I'll use my own nameservers"**, paste the four Netlify nameservers, save.
5. Wait. Usually under an hour, occasionally up to 48.

⚠️ If you already have email running on this domain (GoDaddy/Microsoft 365 mailboxes), switching nameservers will break it until you recreate the MX records inside Netlify. Screenshot your current GoDaddy DNS records first. If that sounds risky, use Route B.

### Route B — Keep DNS at GoDaddy

1. In Netlify: **Domain management → Add a domain** → `velocipartners.com`.
2. In **GoDaddy → DNS → Manage DNS**, add/edit these two records:

| Type | Name | Value | TTL |
|---|---|---|---|
| A | `@` | `75.2.60.5` | 1 hour |
| CNAME | `www` | `velocipartners.netlify.app` | 1 hour |

3. Delete any existing "Parked"/GoDaddy placeholder A record for `@` and any conflicting `www` CNAME.
4. Save. Wait for propagation.

Netlify recommends `www` as the primary address, with the bare domain redirecting to it — set that under **Domain management → Primary domain**.

---

## Step 5 — Turn on HTTPS

In Netlify: **Domain management → HTTPS → Verify DNS configuration → Provision certificate**. Free, automatic, renews itself. Your site becomes `https://` with the padlock.

Don't skip this — browsers flag finance sites without it, and no one submits a contact form to an unsecured page.

---

## Step 6 — Make the contact form work

The form is already wired for Netlify Forms. Two things to do:

1. Submit a test enquiry on the live site.
2. In Netlify: **Forms** → you'll see `contact` with your test in it → **Form notifications → Add notification → Email notification** → enter your email.

Free tier covers 100 submissions/month. A honeypot field is already in place for spam.

**If you host somewhere other than Netlify:** sign up at formspree.io, create a form, and change `<form name="contact" method="POST" data-netlify="true" ...>` to `<form action="https://formspree.io/f/YOUR_ID" method="POST">`.

---

## Step 7 — Get a professional email address

`hello@velocipartners.com` reads far better than a Gmail address on an accounting site.

Cheapest solid option: **Google Workspace** (~$7/user/month) or **Zoho Mail** (free for one user on your own domain). Both walk you through adding MX records — add them wherever your DNS lives after Step 4 (Netlify if Route A, GoDaddy if Route B).

GoDaddy will also try to sell you email. It works, it's just usually pricier.

---

## Step 8 — Get found

1. **Google Search Console** (search.google.com/search-console) → add `velocipartners.com` → verify via DNS TXT record → submit your homepage. This is how Google learns the site exists.
2. **Google Business Profile** (google.com/business) → create a listing with your service area, hours and phone. For a local accounting firm this drives more enquiries than the website itself.
3. Add the site link to your LinkedIn company page and email signature.

The page title and description are already written for search. If you later add city names ("Accounting & Advisory in [your city]") to the H1 and title, local search improves noticeably.

---

## Step 9 — Making changes later

Edit `index.html`, then drag the folder onto Netlify again — it redeploys in seconds and keeps a history you can roll back to.

When the site outgrows one page (separate Services, About, Blog, Client Portal pages), the natural next steps are either adding more HTML files to this same folder, or moving to a CMS. No need to decide now.

---

## Step 10 — Pre-launch checklist

- [ ] Email and phone replaced with real ones
- [ ] Placeholder quote replaced or removed
- [ ] Industries list trimmed to what you actually serve
- [ ] No unverifiable claims anywhere on the page
- [ ] Test form submission received in your inbox
- [ ] Padlock showing on `https://www.velocipartners.com`
- [ ] Checked on an actual phone, not just a narrow browser window
- [ ] Every nav link scrolls to the right section
- [ ] Old GoDaddy Website Builder site cancelled once the new one is live

---

## Sources

- [Configure external DNS for a custom domain — Netlify Docs](https://docs.netlify.com/manage/domains/configure-domains/configure-external-dns/)
- [Get started with domains — Netlify Docs](https://docs.netlify.com/manage/domains/get-started-with-domains/)
- [Bring a domain to Netlify DNS — Netlify Docs](https://docs.netlify.com/manage/domains/configure-domains/bring-a-domain-to-netlify/)
