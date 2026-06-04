# DocIntel — Live Document Intelligence

> Upload any Aadhaar, PAN, or GST document (image or PDF) and watch AI extract, validate, and risk-score it in real time — built to demonstrate enterprise-grade KYC/identity verification capabilities inspired by [Zoop.one](https://zoop.one).

🔗 **Live Demo → [shanitnagre.github.io/doc-intelligence](https://shanitnagre.github.io/doc-intelligence)**

---

## What It Does

Drop any Indian identity document and the engine will:

- **Auto-detect document type** — Aadhaar, PAN, GST, Voter ID, Driving Licence
- **Extract all visible fields** — names, numbers, dates, addresses, state codes, entity types
- **Validate structure** — format checks, regex validation, checksum logic per document type
- **Detect anomalies** — inconsistencies, mismatched fields, fraud signals
- **Score confidence** — 0–100 authenticity score with colour-coded risk level
- **Return a recommendation** — PROCEED, MANUAL REVIEW, or REJECT
- **Session audit trail** — every document analysed is logged with timestamp and outcome
- **Raw JSON export** — structured API-grade response for downstream onboarding integration

---

## How It Works

```
Document Upload (Image/PDF)
        ↓
PDF.js renders first page → base64 image
        ↓
Groq Vision API (Llama 4 Scout) reads the document
        ↓
Field Extraction → Format Validation → Risk Scoring
        ↓
Structured JSON result (mirroring a real KYC API response)
        ↓
Confidence score + Checks + Recommendation rendered live
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML/CSS/JS — no framework, no build step |
| PDF Rendering | PDF.js (Cloudflare CDN) |
| Vision AI | Groq API — Llama 4 Scout 17B (vision model) |
| Fallback | Llama 3.3 70B (text reasoning) |
| Hosting | GitHub Pages |

---

## Sample Documents to Test

Any real or sample Indian document image works. Try:
- A downloaded Aadhaar PDF from UIDAI's sample portal
- A PAN card image (real or demo)
- A GST registration certificate screenshot
- Any document with visible Indian ID numbers

The vision model reads actual text from the document — the more legible the scan, the richer the extraction.

---

## Architecture Note

This prototype mirrors the core flow of Zoop.one's Smart KYC API:

1. **Document ingestion** → accepts image/PDF input, normalises to base64
2. **Vision extraction** → LLM reads raw document pixels, not pre-parsed text
3. **Validation layer** → format rules applied post-extraction (Aadhaar: 12-digit Verhoeff, PAN: AAAAA9999A, GSTIN: 15-char with state code)
4. **Risk engine** → anomaly detection + confidence scoring
5. **Structured output** → JSON response schema compatible with downstream onboarding APIs

---

## Built By

**Shanit Nagre** — Senior Product Manager, IIT Jodhpur  
Portfolio: [shanitnagre.github.io](https://shanitnagre.github.io)  
LinkedIn: [linkedin.com/in/shanit-nagre-b1060917b](https://linkedin.com/in/shanit-nagre-b1060917b)

---

*Built as a product demonstration of document intelligence and KYC verification concepts. Inspired by Zoop.one's identity verification platform and their B2B onboarding API suite.*
