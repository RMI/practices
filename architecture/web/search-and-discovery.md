# Search and discovery

How a public web application tells search engines what to crawl, what to index, and what each page is about. Applies to every public, indexable application. Non-production environments must opt out (see [Non-production environments](#non-production-environments)).

## Templates

| File | Served at | Purpose |
|---|---|---|
| [`robots.public.txt`](/templates/web/robots.public.txt) | `/robots.txt` (production) | Crawl policy and sitemap location |
| [`robots.non-production.txt`](/templates/web/robots.non-production.txt) | `/robots.txt` (dev, staging, preview) | Block all crawling |
| [`sitemap.xml`](/templates/web/sitemap.xml) | `/sitemap.xml` | List of canonical, indexable URLs |
| [`structured-data.jsonld`](/templates/web/structured-data.jsonld) | Inline `<script type="application/ld+json">` | Machine-readable description of the site and its content |

Page-level metadata (titles, descriptions, canonical URLs, Open Graph) is in [`metadata.html`](/templates/web/metadata.html).

## Guidance

- **Keep URLs consistent.** The canonical URL, the sitemap `<loc>`, and internal links should use the same scheme, host, and trailing-slash convention. Redirect other variants with a 301 or 308.
- **Generate the sitemap.** Build it from the app's routes or content at build or request time. Include only canonical pages that return 200 and are indexable. Set `lastmod` from real content changes, not deploy time.
- **robots.txt is not access control.** It is public and only respected by well-behaved crawlers. Don't list sensitive paths in it; protect them with authentication.
- **`Disallow` does not mean "not indexed."** A disallowed URL can still appear in results if it is linked from elsewhere. Use `noindex` (meta tag or `X-Robots-Tag` header) to keep a page out of results, and don't also disallow it, or crawlers will never see the `noindex`.
- **Structured data must describe visible content.** Use `Organization` and `WebSite` on every public app. Add `Dataset`, `SoftwareApplication`, `Article`, etc. only where the page actually presents that thing. Reference RMI's organization by `@id` (`https://rmi.org/#organization`) rather than redefining it differently in each app.
- **AI crawlers are a policy decision.** By default they're allowed, consistent with publishing `llms.txt`. If an app needs to opt out, do so explicitly per user agent in `robots.txt`.

## Non-production environments

Every dev, staging, and preview deployment should:

1. Serve `robots.non-production.txt` as `/robots.txt`.
2. Send `X-Robots-Tag: noindex, nofollow` on every response.
3. Preferably require authentication or an IP allowlist.

Make the robots file and header environment-driven so the production values can't be shipped to staging, or the reverse.

## Checking your work

- [Google Search Console](https://search.google.com/search-console): sitemap submission, indexing, and coverage errors.
- [Schema.org validator](https://validator.schema.org/) and [Rich Results Test](https://search.google.com/test/rich-results): structured data.
- `curl -I https://<host>/` on non-production hosts to confirm the `X-Robots-Tag` header.
