# PASTE SCOPE X

Public archive discovery dashboard (alpha).

## First commit
- Responsive search dashboard with keyword, public Bitcoin address, date-range and result-limit controls.
- Wayback CDX lookup for archived Pastebin URLs.
- Common Crawl index discovery for archived Pastebin URL metadata.
- External indexed Pastebin search shortcut.
- Source status, deduplication, date sorting and archive replay links.

## Limitations
This is an archive URL-discovery prototype, not an IntelX replacement. Common Crawl CDX and Wayback CDX primarily index URL/capture metadata; they do not provide global full-text search over every archived page. This frontend filters discovered URLs, not the body text of every paste. Archive coverage varies, and unavailable, private or never-archived posts cannot be recovered.

For full-text search, add a server-side pipeline that fetches permitted WARC records, extracts text, redacts secrets, and indexes safe text. Add IntelX only through a server-side API integration using a valid API key and plan. Never expose API keys in browser code.

## Run
Open index.html in a modern browser. Some archive endpoints may reject browser CORS requests; use a server-side proxy/worker with caching, rate limiting and backoff when needed.

## Safety
- Public Bitcoin addresses may be searched as public identifiers.
- Do not collect, display, export or process passwords, API tokens, private keys, seed phrases or session cookies.
- Respect source terms, rate limits and robots policies.
- No promise of unlimited coverage or error-free operation.
