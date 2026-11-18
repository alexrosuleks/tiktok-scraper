# TikTok Scraper: TikTok Scraper API for Python & Node.js (2026)

Scrape public TikTok videos from profiles, hashtags, video URLs, and keyword search, plus comments. Get captions, play, like, share, and comment counts, music, and author details.

**[▶ Try the TikTok Scraper free on Scrapely](https://scrape.ly/store/echofield/tiktok-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape TikTok data with the [TikTok Scraper](https://scrape.ly/store/echofield/tiktok-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the tiktok scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this TikTok scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/tiktok-scraper) or from your code with the SDK.
- **Structured tiktok data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $0.35 per 1,000 result results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when TikTok changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What TikTok data can you extract?

Scrape public TikTok videos from profiles, hashtags, video URLs, and keyword search, plus comments. Get captions, play, like, share, and comment counts, music, and author details.

| Output field |
|---|
| `authorMeta.avatar` |
| `authorMeta.name` |
| `text` |
| `diggCount` |
| `shareCount` |
| `playCount` |
| `commentCount` |
| `collectCount` |
| `videoMeta.duration` |
| `musicMeta.musicName` |
| `musicMeta.musicAuthor` |
| `musicMeta.musicOriginal` |
| `createTimeISO` |
| `webVideoUrl` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/tiktok-scraper').call({"hashtags": ["fyp"], "resultsPerPage": 20, "maxFollowersPerProfile": 0, "maxFollowingPerProfile": 0, "commentsPerPost": 0, "topLevelCommentsPerPost": 0, "maxRepliesPerComment": 0, "proxyCountryCode": "None"});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/tiktok-scraper').call(run_input={ "hashtags": [ "fyp" ], "resultsPerPage": 20, "maxFollowersPerProfile": 0, "maxFollowingPerProfile": 0, "commentsPerPost": 0, "topLevelCommentsPerPost": 0, "maxRepliesPerComment": 0, "proxyCountryCode": "None" })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~tiktok-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "hashtags": [
    "fyp"
  ],
  "resultsPerPage": 20,
  "maxFollowersPerProfile": 0,
  "maxFollowingPerProfile": 0,
  "commentsPerPost": 0,
  "topLevelCommentsPerPost": 0,
  "maxRepliesPerComment": 0,
  "proxyCountryCode": "None"
}
```

See every input option on the [TikTok Scraper page](https://scrape.ly/store/echofield/tiktok-scraper).

## Pricing

**$0.35 per 1,000 result results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/tiktok-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape TikTok with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape TikTok with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a tiktok scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~tiktok-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping TikTok legal?** This scraper collects publicly available data. Check TikTok's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related TikTok scrapers

- [TikTok Shop Scraper](https://github.com/alexrosuleks/tiktok-shop-scraper): Scrape TikTok Shop products: price, discount, sold count, rating, reviews, seller, variants, stock and shipping. No…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** tiktok scraper, tiktok scraper, tiktok scraper api, tiktok scraper python, tiktok scraper node.js,
scrape tiktok, tiktok data extraction, tiktok crawler, tiktok api, export tiktok data to csv, tiktok-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/tiktok-scraper).
