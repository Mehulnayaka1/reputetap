# ReputeTap - Smart NFC & QR Google Review Acceleration Platform

> **Turn venue walk-in traffic into 5-star Google reviews and resolve customer issues in real-time before they turn into public negative reviews.**

---

## Executive Overview & Opportunity

Local consumer walk-in businesses (specialty cafés, hair & beauty salons, auto detailing studios, dental clinics, boutique retail) lose over 95% of satisfied customers who leave without reviewing due to search and typing friction. Concurrently, frustrated customers often leave public 1-star reviews simply because they lack an immediate, frictionless channel to speak with management while still at the venue.

**ReputeTap** solves this with a turnkey physical-plus-digital solution:
1. **Physical Asset**: Laser-cut, direct UV-printed acrylic counter desk standee custom branded with the business logo, housing an embedded NTAG213/215 NFC chip and high-contrast QR code.
2. **Digital Micro-App**: A lightning-fast, mobile-optimized micro-landing page (`index.html`) loaded instantly upon tap/scan:
   - **1-Tap AI Review Drafter**: Customers tap category tags (e.g., *"Great coffee"*, *"Courteous staff"*) to generate a polished 2-sentence review that is copied to clipboard and pasted into Google Maps in 1 tap.
   - **Private Manager Resolution Path**: Disables friction for unhappy customers by giving them a direct *"Speak with Management"* button, routing their complaint privately to WhatsApp/webhooks to resolve issues before public negative posting.
   - **Google Review Policy Compliance**: Fully transparent direct public review button included to ensure compliance with Google Business Profile review gating guidelines.

---

## Ecosystem Directory & Created Documents

| File Name | Purpose & Description |
| :--- | :--- |
| 📱 [`index.html`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/index.html) | Production-ready web application micro-landing page (Tailwind CSS, AI tag review generator, WhatsApp & webhook integration, parameter debug modal). |
| 🗣️ [`ReputeTap - Counter Pitch Script.md`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/ReputeTap%20-%20Counter%20Pitch%20Script.md) | The "3-Second Counter Demo" walk-in sales pitch protocol, target prospect timing, and objection handling matrix. |
| 🏷️ [`ReputeTap - NFC Programming SOP.md`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/ReputeTap%20-%20NFC%20Programming%20SOP.md) | Standard Operating Procedure for programming NTAG213/215 chips using NFC Tools and permanent write-locking. |
| 📐 [`ReputeTap - Standee Specifications.md`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/ReputeTap%20-%20Standee%20Specifications.md) | Physical hardware specs, acrylic dimensions (100x150mm), ferrite anti-metal shielding, BOM, and unit economics (80–85% gross margin). |
| 🎨 [`ReputeTap - Standee Print Template.md`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/ReputeTap%20-%20Standee%20Print%20Template.md) | Graphic layout design guide, color palettes (#FFFFFF, #111827, #FBBC05, #4285F4), vector layer structure, and print specs. |
| 🔔 [`ReputeTap - Webhook Notification Guide.md`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/ReputeTap%20-%20Webhook%20Notification%20Guide.md) | Integration guide for automated negative feedback notifications via n8n, Make.com, Formspree, WhatsApp Cloud API, and Telegram. |
| 📁 [`docx/`](file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/docx) | Dedicated folder storing all original `.docx` asset documents. |

---

## Unit Economics & Business Model

- **Upfront Setup Package**: ₹2,499 to ₹3,499 ($30–$45) per location (Includes 2 custom branded acrylic standees + hosted dynamic micro-redirect page).
- **Unit Production Cost**: ₹210 to ₹310 (~$2.50–$3.70) per standee from local acrylic fabricators via IndiaMART.
- **Cost for Pair**: ~₹500 ($6.00).
- **Gross Margin**: **80% – 85%** (~₹2,499 gross profit per client onboarded).
- **Optional Monthly Recurring Revenue (MRR)**: ₹399 – ₹499/month ($5–$7/month) for instant automated WhatsApp webhook notifications and review analytics digest.

---

## Quickstart & Testing

### 1. Test Digital Web App Locally
Open `index.html` in any modern mobile browser or test with custom URL parameters:

```url
file:///c:/Users/Mehul/Documents/Web%20Apps/ReputeTap%20-%20Assets%20&%20Source%20Files/index.html?placeid=ChIJN1t_tDeuEmsRUsoyG83frY4&biz=The%20Roasting%20Room&phone=919876543210&type=cafe
```

### 2. URL Parameter Reference
- `biz`: Business Name displayed on card header.
- `placeid`: Google Place ID for direct Google Maps review deep-linking (`https://search.google.com/local/writereview?placeid={PLACE_ID}`).
- `phone`: Manager/Owner WhatsApp phone number (with country code, no `+` sign).
- `type`: Category (`cafe`, `salon`, `carcare`, `clinic`, `retail`, `restaurant`).
- `webhook`: (Optional) Custom HTTP POST webhook URL for instant complaint logging.

---

## Google Policy Compliance Guarantee

> [!IMPORTANT]
> **Deceptive Review Gating Policy**: Google Business Profile guidelines strictly prohibit blocking or discouraging negative reviews while filtering positive reviews to Google Maps.  
> **ReputeTap Solution**: ReputeTap provides an immediate private resolution path for customer convenience while maintaining a transparent, unhindered link to submit a direct public Google review at all times, making it **100% compliant with Google policies**.
