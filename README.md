[Google Maps Scraper](https://apify.com/nexgendata/google-maps-scraper?fpr=data)

## What does Google Maps Scraper do?

Google Maps Scraper extracts business data from Google Maps search results. It collects business names, addresses, phone numbers, websites, ratings, review counts, and operating hours for any search query or location.

## Why use Google Maps Scraper?

Finding business contact information manually is slow and expensive. This scraper automates the entire process, delivering structured data you can immediately use for lead generation, market research, or competitive analysis.

## Use cases

- **B2B Lead Generation**: Build targeted prospect lists with verified business contact information for any industry and location
- **Market Research**: Analyze business density, ratings, and competition in specific geographic areas
- **Local SEO**: Monitor your business listings and compare against competitors in your area
- **Real Estate Analysis**: Map businesses, amenities, and services around target properties
- **Sales Prospecting**: Find potential customers by industry, location, and rating

## Input parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `searchQuery` | String | Search query (e.g., "restaurants in Chicago") |
| `location` | String | Geographic location to search |
| `maxResults` | Number | Maximum results to return (default: 20) |
| `language` | String | Results language code (default: "en") |

## Output example

```
{
    "name": "Joe's Pizza",
    "address": "7 Carmine St, New York, NY 10014",
    "phone": "+1 212-366-1182",
    "website": "https://joespizzanyc.com",
    "rating": 4.5,
    "reviewCount": 8234,
    "category": "Pizza restaurant",
    "hours": "Mon-Sun: 10:00 AM - 4:00 AM",
    "latitude": 40.7303,
    "longitude": -74.0022
}
```

## How much does it cost?

The scraper uses Pay-Per-Event pricing. You pay $0.50 per 1,000 results extracted. There's a small platform fee of $0.005 per Actor start. A typical run extracting 100 businesses costs approximately $0.05.

## Tips for best results

1. Use specific search queries for better targeting (e.g., "dentists in downtown Seattle" rather than just "dentists")
2. Set `maxResults` to control costs - start small and scale up
3. Combine with our Lead Gen AI Agent for automated email enrichment

## Related Actors from NexGenData

- [Google Maps MCP Server](https://apify.com/nexgendata/google-maps-mcp-server) — AI-powered lead gen
- [Yelp Lead Scraper](https://apify.com/nexgendata/yelp-business-scraper) — Business emails & phones
- [Yellow Pages Scraper](https://apify.com/nexgendata/yellow-pages-scraper) — Local business leads
- [Company Email Finder](https://apify.com/nexgendata/company-email-finder) — B2B contact scraper