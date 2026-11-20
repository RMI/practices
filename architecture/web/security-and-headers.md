# Security and headers

The baseline transport, header, and disclosure setup for every RMI web application, public or internal. This isn't a full security review; it's the set of things every app should have before launch.

## Templates

| File | Served at | Purpose |
|---|---|---|
| [`headers.example`](/templates/web/headers.example) | Response headers (platform config) | HSTS, CSP, and other browser security headers |
| [`security.txt`](/templates/web/security.txt) | `/.well-known/security.txt` | How to report a vulnerability ([RFC 9116](https://www.rfc-editor.org/rfc/rfc9116.html)) |
| [`error-pages/404.html`](/templates/web/error-pages/404.html) | Not-found responses | Helpful page with a real 404 status |
| [`error-pages/500.html`](/templates/web/error-pages/500.html) | Server errors | Self-contained page that leaks nothing |

## Guidance

- **HTTPS only.** Redirect HTTP to HTTPS and send HSTS. Don't add the HSTS `preload` directive unless every subdomain is ready for HTTPS permanently; removal from the preload list takes months.
- **Roll out CSP in report-only mode first.** Deploy `Content-Security-Policy-Report-Only`, fix violations (analytics, fonts, map tiles, embeds), then switch to the enforcing header. Avoid `'unsafe-inline'` and `'unsafe-eval'`; use nonces or hashes instead. The baseline policy is in [`headers.example`](/templates/web/headers.example).
- **Deny unused browser features.** Permissions-Policy should turn off camera, microphone, geolocation, and so on unless the app uses them.
- **Set headers in one place.** Prefer the hosting platform or reverse proxy over per-route application code, so that static assets and error responses get the headers too.
- **Keep security.txt current.** `Expires` should be less than a year away. Set a reminder to renew it. `Canonical` must be the file's own full URL. `Contact` must be a monitored address.
- **Return real status codes.** A missing page returns 404, not a 200 "not found" page. Errors return 5xx.
- **Error pages leak nothing.** No stack traces, framework or version strings, request dumps, or environment details. The 500 page should be fully self-contained (inline CSS, no scripts or API calls), because it is shown when the app itself may be broken.

## Checking your work

- [securityheaders.com](https://securityheaders.com/) or [Mozilla HTTP Observatory](https://developer.mozilla.org/en-US/observatory): header coverage.
- [CSP Evaluator](https://csp-evaluator.withgoogle.com/): policy weaknesses.
- `curl -I https://<host>/does-not-exist` to confirm a 404 status and that the headers are present on error responses.
