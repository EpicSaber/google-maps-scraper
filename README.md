[Google Maps Scraper](https://apify.com/alizarin_refrigerator-owner/google-maps-scraper?fpr=data)

# Google Maps Business Scraper v3.0

Comprehensive Google Maps & GBP scraper with Camoufox stealth browser. Two modes: Search mode for bulk scraping, Place ID mode for detailed GBP data. Extracts business name, address, phone, website, description ('From the business'), reviews, opening hours, photos, Q&A, and more.

---

## Quick Start

### Test with Demo Mode (free, no API key needed)

```
{
  "demoMode": true,
  "webhookHeaders": {}
}
```

### Run with real data

```
{
  "demoMode": false,
  "analysisMode": "full",
  "maxCrawledPlacesPerSearch": 20,
  "maxReviews": 0,
  "reviewsSort": "newest",
  "includeQA": false,
  "language": "en",
  "zoom": 13,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL"
    ]
  },
  "webhookPlatform": "custom",
  "webhookHeaders": {}
}
```

---

## Input Parameters

| Parameter | Type | Default | Required | Description |
| --- | --- | --- | --- | --- |
| `analysisMode` | string | `"full"` | No | Choose 'full' for comprehensive scraping of each business page, or 'local-pack' for a lightweight extraction of only the top 3 search results (name, rating, review count, category, URL) without navigating to individual pages. |
| `searchStringsArray` | array | - | No | List of search queries like 'Bar Fort Lauderdale FL' or 'Plumber Miami'. Used for search mode. |
| `maxCrawledPlacesPerSearch` | integer | `20` | No | Maximum number of places to return per search query |
| `placeIds` | array | - | No | Direct Google Place IDs (ChIJ...) or CIDs for detailed GBP scraping. Use this mode to get comprehensive data including description, reviews, hours, and photos for specific businesses. |
| `maxReviews` | integer | `0` | No | Maximum number of reviews to extract per business (0 = no reviews). Reviews include author, rating, text, date, and response. |
| `reviewsSort` | string | `"newest"` | No | How to sort reviews before extraction |
| `includeQA` | boolean | `false` | No | Extract Questions & Answers section from the business profile |
| `language` | string | `"en"` | No | Language code for results |
| `lat` | string | - | No | Center latitude for geo-biased search |
| `lng` | string | - | No | Center longitude for geo-biased search |
| `zoom` | integer | `13` | No | Map zoom level (10=city, 14=neighborhood, 17=street) |
| `proxyConfiguration` | object | `{"useApifyProxy":true,"apifyProxyGroups":["RESIDENTIAL"]}` | No | Proxy settings. Residential proxies recommended for best results. |
| `demoMode` | boolean | `false` | No | Run in demo mode without real scraping. Returns mock success response for testing. Set to false for real scraping. |
| `webhookUrl` | string | - | No | URL to POST results when scraping completes (Zapier, Make, n8n, custom endpoint) |
| `webhookPlatform` | string | `"custom"` | No | Platform type for webhook payload formatting |
| `webhookHeaders` | object | - | No | Additional HTTP headers to send with webhook (e.g., authorization tokens) |

---

## Pricing

This actor uses **pay-per-event** billing:

| Event | Description | Price |
| --- | --- | --- |
| Business Scraped | Each Google Maps business scraped (basic data) | $0.04 |
| Business with Reviews | Business scraped with review extraction | $0.08 |

**Demo mode is free** -- no charges for sample data.

---

## Troubleshooting

### "API error 429" or "Rate limit"

Too many requests. Wait a minute and try again, or reduce the number of items per run.

### No results or empty dataset

Check the run log for error messages. Common causes:

- Invalid input format (check the examples above)
- The target data doesn't exist or is too small to track

### How do I test without an API key?

Enable **Demo Mode** in the input. This returns realistic sample data so you can verify the output format works for your workflow.

---

**Built by John Rippy | [Actor Arsenal](https://actorarsenal.com)**