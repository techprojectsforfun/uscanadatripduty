# 🍁 Canadian Duty Calculator

A free, single-page web app that helps Canadians returning from the United States estimate the **customs duty, GST/HST, and provincial sales tax** owed on goods purchased in the US — based on Canada Border Services Agency (CBSA) rules.

---

## Live Demo

Open `index.html` directly in any browser. No server, build step, or installation required.

---

## Features

- **Trip duration selector** — automatically applies the correct CBSA personal exemption ($0 / $200 / $800 CAD) based on how long you were away
- **Province / territory picker** — calculates the right tax rate for all 13 provinces and territories (HST, GST+PST, GST+QST, GST-only)
- **Live USD → CAD exchange rate** — auto-fetches today's rate via the [Frankfurter API](https://www.frankfurter.app/) (European Central Bank data, no API key required); manual override supported
- **17 item categories** with individual duty rates (electronics 0%, clothing 18%, footwear 20%, luggage 16%, etc.)
- **Special handling for alcohol and tobacco** — enforces CBSA allowance limits and applies excise duty rates for over-limit quantities
- **Exemption progress bar** — visually shows how close you are to your personal exemption limit
- **Full cost breakdown** — line-by-line table showing purchases, exemption deduction, duty, and tax
- **Terms of Use modal** — full liability disclaimer citing the *Customs Act*, *Customs Tariff*, *Excise Act 2001*, and *Excise Tax Act*, required to accept before use
- **SEO-optimised** — structured data (Schema.org `WebApplication` + `FAQPage`), Open Graph, Twitter Card, semantic HTML

---

## Personal Exemption Reference

| Time away from Canada | Exemption (CAD) | Alcohol & Tobacco |
|---|---|---|
| Less than 24 hours | $0 | Not included |
| 24 – 48 hours | $200 | Not included |
| 48 hours – 6 days | $800 | Included (within limits) |
| 7 days or more | $800 | Included (within limits) |

### Alcohol allowances (48h+ trips)
- 1.14 L of spirits (> 22% ABV), **or**
- 1.5 L of wine / coolers, **or**
- 8.5 L of beer (~24 cans)

### Tobacco allowance (48h+ trips)
- 200 cigarettes (1 carton)
- 50 cigars
- 200 g of manufactured tobacco

---

## Duty Rates by Category

| Category | Duty Rate |
|---|---|
| Electronics & Computers | 0% |
| Books, Magazines & Maps | 0% |
| Toys & Games | 0% |
| Sporting Goods | 0% |
| Children's Clothing | 0% |
| Vitamins & Supplements | 0% |
| Adult Clothing & Apparel | 18% |
| Footwear / Shoes | 20% |
| Luggage & Bags | 16% |
| Furniture & Home Decor | 9.5% |
| Jewelry & Watches | 6.5% |
| Cosmetics & Personal Care | 6.5% |
| Other / General | 6.5% |
| Tools & Hardware | 6% |
| Food & Groceries | ~5% |
| Alcohol | Special (see above) |
| Tobacco | Special (see above) |

Rates are approximate MFN (Most Favoured Nation) tariff rates under the *Customs Tariff, S.C. 1997, c. 36*.

---

## Tax Rates by Province / Territory

| Province / Territory | Tax |
|---|---|
| Ontario | HST 13% |
| New Brunswick, Nova Scotia, Newfoundland & Labrador, PEI | HST 15% |
| British Columbia | GST 5% + PST 7% |
| Manitoba | GST 5% + RST 7% |
| Saskatchewan | GST 5% + PST 6% |
| Quebec | GST 5% + QST 9.975% |
| Alberta, NWT, Nunavut, Yukon | GST 5% only |

---

## How It Works

1. Select how long you were in the US (determines exemption tier)
2. Choose your home province and confirm the exchange rate
3. Add each item with its description, category, price (USD), and quantity
4. The calculator instantly shows total duty + tax owed, with a full breakdown

Tax is applied on the **dutiable value + duty paid** (i.e., duty-inclusive base), consistent with CBSA assessment methodology.

---

## Tech Stack

| | |
|---|---|
| Language | Vanilla HTML / CSS / JavaScript (ES2020) |
| Fonts | [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts |
| Exchange rate API | [Frankfurter](https://www.frankfurter.app/) (ECB data, free, no key) |
| Dependencies | None — zero npm, zero build tools |
| Hosting | Any static host (GitHub Pages, Netlify, Vercel, S3, etc.) |

---

## Deployment

Since this is a single static file, deployment is straightforward:

**GitHub Pages**
```bash
git init
git add index.html README.md
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/canadian-duty-calculator.git
git push -u origin main
# Enable Pages in repo Settings → Pages → Deploy from branch: main
```

**Netlify / Vercel**

Drag and drop the folder into the Netlify or Vercel dashboard. No configuration needed.

**Custom domain**

Update the `<link rel="canonical">` and Open Graph `og:url` in `index.html` to match your domain:
```html
<link rel="canonical" href="https://yourdomain.com/" />
<meta property="og:url" content="https://yourdomain.com/" />
```

---

## SEO

The app includes:

- Keyword-rich `<title>` and `<meta name="description">`
- Open Graph tags for social sharing previews (Facebook, LinkedIn, Google)
- Twitter / X Card meta tags
- `lang="en-CA"` and `<link rel="canonical">`
- **Schema.org `WebApplication`** JSON-LD structured data
- **Schema.org `FAQPage`** JSON-LD — enables expandable FAQ cards directly in Google search results

---

## Legal & Disclaimer

All calculations are **estimates only** and do not constitute legal, tax, or customs advice.

Actual duty is determined solely by CBSA officers at the time of importation and may differ based on:

- Specific tariff classification (*Customs Tariff, S.C. 1997, c. 36*)
- Country of origin and trade agreement treatment
- CBSA officer discretion (*Customs Act, R.S.C. 1985, c. 1 (2nd Supp.)*)
- Excise duty (*Excise Act, 2001, S.C. 2002, c. 22*)
- GST/HST (*Excise Tax Act, R.S.C. 1985, c. E-15*)
- Current exchange rates

The operator assumes **no liability** for any duty assessed, fines, penalties, or seizures resulting from reliance on this tool. Always declare all goods truthfully to CBSA.

Full terms are presented in-app and must be accepted before use.

**Official CBSA reference:** https://www.cbsa-asfc.gc.ca/travel-voyage/itr-rji-eng.html

---

## Contributing

Pull requests are welcome. If duty rates or exemption thresholds change due to new legislation or budget measures, please open an issue or PR with a reference to the relevant CBSA notice or Order in Council.

---

## License

MIT — free to use, modify, and distribute, Attribution appreciated but not required.
