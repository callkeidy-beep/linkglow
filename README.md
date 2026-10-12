# LinkGlow — prototype

Direct matching between Korean indie beauty / aesthetic-device brands and US micro-creators (10K–100K).

One self-contained file: `index.html`. No build step, no CDN, no network calls. Works offline inside a WebView.

## Run

Open `index.html` in a browser. Deploy: import this repo in Vercel (no build command, output = root) or enable GitHub Pages on `main` / root.

## What works (mock state, saved to localStorage)

| View | Screen | Interaction |
| --- | --- | --- |
| Brand (KO/EN) | Create Campaign | Category, target skin type, compensation (seeding / fixed / affiliate %), shipping. Validation and a live preview card. Publishing puts the campaign on the creator feed. |
| Brand | Creator Discovery | Filter by platform, niche, skin tone, follower band, engagement. **Send Offer** opens the contract, then the creator receives the offer. |
| Brand | My Campaigns | Applicant pipeline. **Approve & ship** issues an EMS/USPS tracking number. |
| Creator (EN) | Campaign Feed | Filter by skin concern, compensation, category. **Apply for Sample** opens the contract. |
| Creator | My Collaborations | Applied → Sample Shipped (tracking #) → Content Upload (live FTC caption check) → Completed. |
| Both | Performance | Clicks, promo-code uses, conversion rate, revenue or earnings, a 14-day trend, a per-creator table. |

"Reset demo" in the footer restores the seed data.

## Package for App Store / Google Play (Capacitor)

```bash
mkdir linkglow-app && cd linkglow-app
npm init -y && npm i @capacitor/core @capacitor/cli @capacitor/ios @capacitor/android
npx cap init LinkGlow com.linkglow.app --web-dir www
mkdir www && cp ../linkglow/index.html www/   # path to this repo's index.html
npx cap add ios && npx cap add android
npx cap sync && npx cap open ios   # or: npx cap open android
```

The page already sets `viewport-fit=cover` and respects safe-area insets on the header, the bottom tab bar, and modal footers.

The contract text is a prototype template, not legal advice.
