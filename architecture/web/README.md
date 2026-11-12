# Things to be included in (almost) all webapps

It is the machine's world, and we just live in it. So we must cater to their needs. Adding this content to all or most webapps, as appropriate, will make them more findable, and more useful to agents, so ultimately more useful also to the people who use agents.

Templates for most of these live in [`/templates/web`](/templates/web). For how to use them and common pitfalls, see:

- [Metadata](metadata.md): page titles, descriptions, Open Graph, icons
- [Agent readiness](agent-readiness.md): making content usable by AI agents, llms.txt
- [Search and discovery](search-and-discovery.md): robots.txt, sitemaps, canonical URLs, structured data, keeping non-production out of search
- [Security and headers](security-and-headers.md): HTTPS, security headers, security.txt, error pages

## Every web application
- Correct HTML/document metadata (see [metadata template](/templates/web/metadata.html))
- favicon
- Semantic/accessibility baseline
- HTTPS + security headers ([template](/templates/web/headers.example), [guidance](security-and-headers.md))
- security.txt ([template](/templates/web/security.txt))
- Correct HTTP status/error handling ([404](/templates/web/error-pages/404.html), [500](/templates/web/error-pages/500.html))
- Privacy/security requirements (?)

## Every public/indexable web application
- robots.txt ([public](/templates/web/robots.public.txt), [non-production](/templates/web/robots.non-production.txt), [guidance](search-and-discovery.md))
- sitemap.xml ([template](/templates/web/sitemap.xml))
- Unique page titles and descriptions
- Canonical URLs (in fact and as a metadata element)
- Open Graph/social cards (see [metadata template](/templates/web/metadata.html))
- meaningful server-accessible content (?)
- llms.txt ([template](/templates/web/llms.txt)) as RMI's recommended agent-discovery convention

## When applicable
- web manifest
- RSS/Atom
- hreflang
- OpenSearch
- OpenAPI
- API Catalog
- A2A Agent Card
- MCP
- specialized structured data

| Component | Recommendation | Notes |
|---|---|---|
| `/robots.txt` | **Required** | Explicit policy; include sitemap URL on public sites. RFC 9309 standard. ([RFC Editor][1]) |
| `/sitemap.xml` | **Required for public sites** | Ideally generated rather than manually maintained. |
| `<title>` | **Required** | Unique, descriptive page title. |
| `meta description` | **Required for indexable pages** | Human-readable summary. |
| `meta viewport` | **Required** | Normal responsive-web baseline. |
| canonical URL | **Required for public/indexable pages** | `<link rel="canonical">`. |
| robots meta | **Required where applicable** | `index/noindex`, `follow/nofollow`; also document `X-Robots-Tag` for non-HTML resources. |
| Open Graph metadata | **Required for public sites** | `og:title`, `og:description`, `og:url`, `og:image`, `og:type`, etc. |
| social-card metadata | **Recommended** | Twitter/X card fields remain broadly consumed even though they aren't web standards. |
| favicon(s) | **Required** | Include modern icon formats plus appropriate fallbacks. |
| `/site.webmanifest` | **Recommended** | App/site identity, icons, theme; especially useful for installable apps. |
| `theme-color` | **Recommended** | Browser/UI integration. |
| JSON-LD structured data | **Required where applicable** | At minimum appropriate `Organization`, `WebSite`, `SoftwareApplication`, `Dataset`, `Article`, etc. Don't manufacture schema that doesn't describe visible content. |
| `lang` attribute | **Required** | `<html lang="en">`, etc. |
| semantic HTML | **Required** | Proper headings, `main`, `nav`, forms, links/buttons, etc.; important for accessibility, search engines and agents. |
| image `alt` attributes | **Required** | Accessibility plus machine understanding. |
| `/.well-known/security.txt` | **Required** | Particularly appropriate for RMI. There is an RFC-defined format and location specifically for vulnerability disclosure. ([RFC Editor][2]) |
| HTTPS | **Required** | With HTTP → HTTPS redirect. |
| security headers | **Required** | HSTS, CSP, `X-Content-Type-Options`, `Referrer-Policy`, appropriate frame policy, permissions policy. |
| 404 response/page | **Required** | Must really return HTTP 404, not a 200 “not found” page. |
| 500/error behavior | **Required** | No stack traces/secrets; useful human error page. |
| redirects | **Required where URLs change** | Permanent URLs and appropriate 301/308 redirects. |
| privacy policy | **Required when applicable** | Especially when collecting analytics, accounts, forms or personal information. |
| accessibility baseline | **Required** | WCAG-oriented semantic markup, keyboard use, focus, contrast, labels, reduced motion, etc. |
| performance baseline | **Required** | Image sizing/compression, caching, compression, reasonable JS, Core Web Vitals. |
| RSS/Atom feed | **Conditional** | For regularly published content. |
| `hreflang` | **Conditional** | For multilingual/multiregional sites. |
| `opensearch.xml` | **Conditional** | Useful where the application has meaningful public search. W3C's current Web Sustainability Guidelines list it alongside favicon, robots, manifest and sitemap as an expected site file. ([W3C][3]) |

[1]: https://www.rfc-editor.org/rfc/rfc9309.html "RFC 9309: Robots Exclusion Protocol"

[2]: https://www.rfc-editor.org/rfc/rfc9116.html "RFC 9116: A File Format to Aid in Security Vulnerability Disclosure"

[3]: https://www.w3.org/TR/2026/DNOTE-web-sustainability-guidelines-20261016/ "Web Sustainability Guidelines (WSG)"