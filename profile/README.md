<p align="center">
  <img src="https://assets.crawlbrulee.com/brand/custard-noto3d-v2-256.png" alt="crawlbrulee" width="88" height="88">
</p>

<h1 align="center">🍮 crawlbrulee</h1>

<p align="center">EU-native web scraping for AI agents & developers</p>

---

**🍮 crawlbrulee** turns a url into clean markdown, a screenshot, metadata, links or html. we take care of the hard parts for you: headless Chrome for javascript-heavy pages, rotating proxies, retries and cookie banners, so you don't have to run and maintain your own scraper.

everything runs on 🇪🇺 EU servers, and our [data processing agreement](https://crawlbrulee.com/legal/dpa) is public.

**to try it,** [create a free account](https://dashboard.crawlbrulee.com/auth/register?utm_source=github&utm_medium=org-profile&utm_campaign=github-org). you get 750 credits every month, no card needed. a simple page costs 1 credit.

## what a call looks like

```bash
curl -X POST https://api.crawlbrulee.com/api/scrape \
  -H "Authorization: Bearer $CRAWLBRULEE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "url": "https://example.com", "extract": { "markdown": true, "links": true } }'
```

you get json back with the markdown and the links. the shape is the same whether you wait for it or run it as a background job with a webhook. the [getting started guide](https://crawlbrulee.com/docs/getting-started) covers the rest.

## open source clients

our client tools live in this org, and all of them are open source:

| repo | what it is | try it |
| --- | --- | --- |
| [crawlbrulee-js](https://github.com/crawlbrulee/crawlbrulee-js) | typed js/ts sdk, no runtime dependencies | `npm install @crawlbrulee/sdk` |
| [crawlbrulee-py](https://github.com/crawlbrulee/crawlbrulee-py) | python sdk, sync and async | `pip install crawlbrulee` |
| [crawlbrulee-mcp](https://github.com/crawlbrulee/crawlbrulee-mcp) | mcp server, so your agent gets scrape and map as tools | `claude mcp add crawlbrulee -- npx -y @crawlbrulee/mcp` |
| [crawlbrulee-cli](https://github.com/crawlbrulee/crawlbrulee-cli) | scrape and map from your terminal | `npx crawlbrulee scrape https://example.com` |
| [crawlbrulee-skills](https://github.com/crawlbrulee/crawlbrulee-skills) | agent skills that teach your coding agent how to use crawlbrulee | `npx skills add crawlbrulee/crawlbrulee-skills` |
| [crawlbrulee-n8n](https://github.com/crawlbrulee/crawlbrulee-n8n) | a verified n8n node | search "crawlbrulee" in n8n |

prefer your own client? the [OpenAPI spec](https://crawlbrulee.com/docs/openapi.json) is public, so you can generate one in any language.

everything is Apache-2.0, except the n8n node, which is MIT.

## what we care about

- **you don't pay for failures.** a [failed scrape](https://crawlbrulee.com/docs/credits-and-pricing#what-counts-as-a-failure) costs 0 credits. so does a page we already have in cache.
- **your data stays in the EU.** the fetch, the render, the cache and the result all stay on EU servers. you pick the proxy exit, and if you pick an EU one, nothing leaves.
- **output that models can read.** markdown with ads, popups and cookie banners removed, and tall screenshots cut into slices an image model can handle. to drop anything else, like a nav or a footer, pass your own css selectors.

## get in touch

for a bug in one of the tools, open an issue in its repo. for anything else, write to contact@crawlbrulee.com or find us on [X](https://x.com/crawlbrulee).
