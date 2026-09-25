# Growfolio

A professional, minimalist CSV-first portfolio research dashboard designed for GitHub Pages.

## Visual system
Navy blue + cream, responsive, no framework.

## CSV format
Required: `Symbol`, `Quantity`, `AvgPrice`.
Recommended: `Company`, `Sector`, `CurrentPrice`, `PE`, `ROE`, `ROCE`, `DebtEquity`, `RevenueGrowth`, `ProfitGrowth`, `Volatility`.

A sample is included as `sample-portfolio.csv`.

## Price refresh
The static site attempts a browser-side Yahoo Finance quote request for `<SYMBOL>.NS`. This is intentionally best-effort: public browser endpoints can be blocked by CORS or change without notice.

For a reliable public deployment, put a licensed/authorized market-data provider behind a serverless function (Cloudflare Worker, Vercel Function, Netlify Function, etc.) so API credentials are not exposed in GitHub Pages.

Screener does not provide an API; its supported export workflow is CSV. Do not build production scraping around Screener pages.

## Deploy
Upload the contents of this folder to a GitHub repository. In Settings > Pages, deploy from `main` and `/ (root)`.

## Research model
The rating is transparent and rule-based. It uses profitability, growth, leverage, valuation and position performance. Risk buckets are research categories, not buy/sell instructions or predictions.


## ₹99 payment setup
The site includes a Growfolio Plus ₹99 payment section. Because this is a static GitHub Pages project, do not place payment gateway secrets in frontend code. Create a hosted Payment Link/Payment Page in your payment provider (for example Razorpay or Stripe) and paste that public checkout URL into `PAYMENT_LINK` near the end of `app.js`. A full API-based checkout with order creation and signature verification requires a backend/serverless function.


## Suggestions and payment
The Overview includes two complimentary rule-based portfolio suggestions and a Growfolio Plus payment call-to-action. Set `PAYMENT_LINK` in `app.js` to your hosted Razorpay or Stripe payment link. Do not place secret payment API keys in a GitHub Pages frontend.
