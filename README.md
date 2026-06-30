# 🏠 Rent vs. Buy — Net Worth Projection

A single-file, dependency-free financial planning dashboard that compares **buying a home**
against **renting and investing the difference** in the market (e.g. the S&P 500), and projects
total net worth over a configurable number of years.

It's just one self-contained `index.html` — no build step, no server, no external libraries.
Open it locally, or host it on GitHub Pages and share the link.

## Features

- **Rent vs. buy comparison** with a fair, cash-flow-matched model (both scenarios deploy the same
  total cash each month; the side that spends less on housing invests the difference).
- **All assumptions are adjustable** via sliders + number boxes: income, income growth, % of income
  invested, starting savings, investment return, home price, down payment, mortgage rate & term,
  property tax, HOA, insurance, maintenance, closing & selling costs, appreciation, rent, rent
  increase, projection length, and inflation.
- **"Wait before buying"** slider, plus an **Auto-set** button that finds the earliest month your
  savings can cover the (rising) down payment + closing costs.
- **Charts:** projected net worth over time, and two side-by-side stacked area charts showing the
  composition of net worth (home equity vs. investments) for buyer vs. renter on a shared scale.
- **Purchase marker** drawn on every chart at the month you buy.
- **Settings persist** automatically in your browser (`localStorage`) between visits.
- **Export / Import settings** as a JSON file, so you can save scenarios or send them to a friend.
- **Inflation toggle** to view everything in today's dollars.

## Use it locally

Just open `index.html` in any modern browser (double-click it, or `xdg-open index.html` /
`open index.html`). Everything runs client-side. You can email the single file to anyone.

## Save & share scenarios

- In the **Display & Settings** panel, click **Export JSON** to download `rent-vs-buy-settings.json`
  containing every parameter.
- Click **Import JSON** and pick a previously exported file to restore those parameters.
- Your latest settings are also remembered automatically the next time you open the page in the
  same browser.

## Host it on GitHub Pages

This repo is ready for GitHub Pages — `index.html` lives at the root, and a `.nojekyll` file tells
Pages to serve the files as-is.

**Option A — Deploy from a branch (simplest):**

1. Create a repo on GitHub and push this folder:
   ```bash
   git init
   git add .
   git commit -m "Rent vs. buy net-worth dashboard"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
2. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   pick `main` and `/ (root)`, then **Save**.
3. Your site goes live at `https://<you>.github.io/<repo>/` within a minute or two.

**Option B — Deploy with GitHub Actions:**

This repo includes `.github/workflows/deploy-pages.yml`. To use it, set
**Settings → Pages → Source: GitHub Actions**. Every push to `main` then publishes automatically.

## Notes & assumptions

This is a planning estimate, **not financial advice**. The model does not include income taxes,
the mortgage-interest / property-tax deductions, capital-gains tax, or PMI. Investment and
appreciation returns are nominal and pre-tax unless you enable the "today's dollars" toggle.
See the **How this works & assumptions** section at the bottom of the page for full detail.
