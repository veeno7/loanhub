# LoanHub — lending website (single-file build)

A complete, working loan-origination website: check a rate → 4-step application →
personalized offer → accept & fund → loan dashboard with payments and amortization.

Everything (HTML, CSS, JavaScript, icons, favicon) lives inside **one file**:
`index.html`. There are no images, no build step, no dependencies.

---

## Option A — Upload to GitHub and go live (recommended)

1. On GitHub, click **New repository**, give it a name (e.g. `loanhub`), keep it
   **Public**, and click **Create repository**.
2. On the empty repo page click **uploading an existing file**.
3. Drag in **`index.html`** and **`.nojekyll`** (both files from this folder).
   *On a phone: tap "Add file → Upload files", then choose the files from your
   unzipped folder.*
4. Scroll down and click **Commit changes**.
5. Go to **Settings → Pages**.
   * **Source:** `Deploy from a branch`
   * **Branch:** `main`  **Folder:** `/ (root)`
   * Click **Save**.
6. Wait ~1 minute, refresh the page. Your site is live at:
   `https://YOUR-USERNAME.github.io/loanhub/`

That's it. Every link, form and page works because it is all in `index.html`.

> `.nojekyll` tells GitHub Pages to serve the files exactly as they are. It is
> optional but recommended.

## Option B — Open it locally

Double-click `index.html`. It runs straight from your phone or computer with no
server and no internet connection.

---

## What works

| Area | Details |
|---|---|
| Rate engine | APR calculated from credit band, term and amount (5.99%–29.99%) |
| Application | 4 steps: purpose & amount → identity/address → employment/income → review |
| Validation | Email, 10-digit phone, 5-digit ZIP, age 18+, required consent |
| Offer | Amount, APR, monthly payment, total interest, total cost, "adjust" path |
| Funding | Generates loan ID, start date and first due date |
| Dashboard | Balance, progress bar, next payment, full amortization schedule |
| Payments | Scheduled, double, or full payoff; modal confirm; interest/principal split |
| History | Every payment listed with date and amount; "Paid off" state |
| Accounts | Email → password sign-in, session handling, header updates |
| Calculator | Live monthly payment + principal vs. interest bar |
| FAQ | Accordion with accessible `aria-expanded` |
| Assistant bot | Rule-based chat bot answering rates, limits, fees, funding, payments |
| Persistence | Draft, active loan and session saved in `localStorage` |

## Tested

61 automated browser checks across 1280px, 768px and 390px widths — all five
routes, the full apply → offer → fund → dashboard → payoff flow, validation
failures, schedule math, persistence after reload, mobile navigation,
Escape-to-close, print styles and the chat bot. Zero console errors, zero failed
requests, no horizontal overflow at any size.

## Customizing

Open `index.html` in any text editor and search for:

* `--green` / `--green-dark` — brand colors (top of the `<style>` block)
* `BASE_APR` / `TERM_ADJ` — rate table (inside the `<script>` block)
* `1-800-555-0142` — support phone number
* `LoanHub` — brand name

## Note

This is a demonstration platform. The footer discloses that rates, offers and
funding are illustrative and no real credit is extended. To go live, connect the
application submit handler (`#apSubmit`) to your backend or loan origination API
and replace the demo assistant with your own service.

## Files

```
index.html   the entire website (self-contained)
.nojekyll    tells GitHub Pages to serve files as-is
README.md    this file
```
