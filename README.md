# Real Estate Lead Scraper

Extract structured data from [google.com](https://google.com) — Find real-estate agents, realtors and brokers on Google Maps (google.com/maps) — name, category, address, phone, website, emails, tech stack, and a 0–100 lead score. Built for real-estate SMMA & recruiting outreach. Geo-accurate, pay per result.

**[Real Estate Lead Scraper on Apify →](https://apify.com/blackfalcondata/google-maps-real-estate-lead-scraper?fpr=1h3gvi)**

---

## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.

## Key features

**Result cap** — Stop after N listings (up to 1.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from google.com on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from google.com.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "searchTerms": [
    "real estate agent"
  ],
  "location": "Austin, TX",
  "maxResults": 10
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `searchTerms` | array | — | What to search for, e.g. "plumber", "roofer", "dentist". Add several to scan multiple categories in one run. |
| `location` | string | — | City, area, or region to search within, e.g. "Austin, TX" or "Manchester, UK". |
| `searchRadiusKm` | integer | `25` | How far from the location centre to include results. Results outside the radius are dropped. |
| `searchRadiusMiles` | integer | — | Optional alternative to km. Used only when the km radius is left empty. |
| `maxResults` | integer | `100` | Maximum number of businesses to return. |
| `gl` | enum | `"us"` | Country to bias the search and geocoding toward. |
| `hl` | string | `"en"` | Result language (2-letter code, e.g. "en"). |
| `minRating` | integer | — | Only keep businesses with at least this star rating (0–5). Leave empty for no minimum. |
| `minReviews` | integer | — | Only keep businesses with at least this many reviews. |
| `category` | string | — | Keep only businesses whose Google category contains this text (case-insensitive). |
| `requirePhone` | boolean | `false` | Keep only businesses that list a phone number (recommended for outreach). |
| `telegramToken` | string | — | Telegram bot token (from @BotFather). Required for Telegram notifications. |
| `telegramChatId` | string | — | Telegram chat or channel ID. Required when a Telegram token is set. |
| `discordWebhookUrl` | string | — | Discord incoming webhook URL. |
| `slackWebhookUrl` | string | — | Slack incoming webhook URL. |
| `whatsappAccessToken` | string | — | WhatsApp Cloud API access token. The recipient must have messaged your business number within the last 24h. |
| `whatsappPhoneNumberId` | string | — | Your WhatsApp Business phone-number ID. Required when a WhatsApp token is set. |
| `whatsappTo` | string | — | Recipient phone in E.164 format without + (e.g. "15125550100"). |
| `webhookUrl` | string | — | Receives a JSON POST with the run's leads after the run finishes (n8n / Make / Zapier / custom). |
| `webhookHeaders` | object | — | Optional JSON object of custom headers (e.g. {"Authorization":"Bearer ..."}). |
| `notifyOnlyChanges` | boolean | `false` | Only send notifications for businesses that are new or changed since the previous run. |

---

## Output fields

Every listing returns the same 32-field schema. Missing values are `null` — never omitted.

- `title`
- `categoryName`
- `cid`
- `fid`
- `mapsUrl`
- `location`
- `distanceFromCenterKm`
- `address`
- `neighborhood`
- `street`
- `city`
- `state`
- `postalCode`
- `countryCode`
- `totalScore`
- `reviewsCount`
- `claimThisBusiness`
- `openingHoursToday`
- `website`
- `displayDomain`
- `contactPhone`
- `extractedEmails`
- `extractedPhones`
- `extractedUrls`
- `socialProfiles`
- `leadEmail`
- `emailVerifications`
- `techStack`
- `leadScore`
- `leadTier`
- `changeType`
- `scrapedAt`

---

## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "title": "Lone Star Realty",
  "categoryName": "Real estate agency",
  "cid": "12345678901234567890",
  "fid": "0x0:0xab12cd34",
  "mapsUrl": "https://www.google.com/maps?cid=12345678901234567890",
  "location": {
    "lat": 30.2711,
    "lon": -97.7437
  },
  "distanceFromCenterKm": 1.95,
  "address": "300 Congress Ave, Austin, TX 78701",
  "neighborhood": null,
  "street": "300 Congress Ave",
  "city": "Austin",
  "state": "TX"
}
```

*Truncated — full records contain 32 fields. See Output fields for the complete schema.*

**[Try Real Estate Lead Scraper now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/google-maps-real-estate-lead-scraper?fpr=1h3gvi)**

---

## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Run start | $0.00005 |
| Place scraped | $undefined |
| Filtered out | $undefined |
| Place details | $undefined |
| Contacts extracted | $undefined |
| Email verified | $undefined |
| Tech stack detected | $undefined |

See the [actor on Apify](https://apify.com/blackfalcondata/google-maps-real-estate-lead-scraper?fpr=1h3gvi) for current pricing.

---

## FAQ

**How do I scrape google.com?**
Use this actor on Apify to extract structured data from google.com. Configure your search query and filters in the input, then click Start — no coding required.

**How do I get google.com data as JSON, CSV, or Excel?**
The actor writes each listing to Apify's dataset. Download as JSON, CSV, or Excel from the Console, stream via the API, or push to Make, Zapier, Airbyte, or Keboola.

**Is it legal to scrape google.com?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check google.com's terms of service for your specific use case.

**How much does it cost?**
Pay-per-event pricing — you only pay for listings extracted. Apify's free $5 credit is enough to run thousands of results before you pay anything.

**Do I need an API key or credentials?**
No. Just sign up for Apify, paste your input, and click Start. No credit card required.

---

## Related products by Black Falcon Data

[Browse all Black Falcon Data actors →](https://apify.com/blackfalcondata?fpr=1h3gvi)

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. Sign up — $5 platform credit included
2. Open [Real Estate Lead Scraper](https://apify.com/blackfalcondata/google-maps-real-estate-lead-scraper?fpr=1h3gvi) and configure your input
3. Click **Start** — export results as JSON, CSV, or Excel

Need more later? [See Apify pricing](https://apify.com/pricing?fpr=1h3gvi).

---

## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

*Last updated: 2026 06*
