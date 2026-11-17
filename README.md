# Peter’s email agent

A small, dependency-free static landing page for <https://agents.pcstj.com/>.
Open `index.html` directly to preview it. The robot is an original SVG; no scripts,
third-party fonts, or build step are needed.

## Hosting

Publish this directory as the root of the separate `pstjohn/agents` repository.
In GitHub Settings → Pages, deploy from `main` / root and set the custom domain
to `agents.pcstj.com`. Enable HTTPS when GitHub has issued the certificate.

The existing `pstjohn/pstjohn.github.io` repository serves `pcstj.com` and keeps
its existing custom domain. Each Pages repository supports one custom domain.

## DNS and email

If `agents.pcstj.com` has MX/TXT email records, use the following **A records**
at the `agents` name instead of a CNAME. A DNS CNAME cannot coexist with MX or
TXT records at that same name. GitHub Pages supports these addresses:

| Type | Name | Value |
| --- | --- | --- |
| A | agents | 185.199.108.153 |
| A | agents | 185.199.109.153 |
| A | agents | 185.199.110.153 |
| A | agents | 185.199.111.153 |

Preserve all email MX, SPF, DKIM, and DMARC records. The `CNAME` **file** in
this repository configures GitHub Pages and is separate from a DNS CNAME record.
Check any existing A/AAAA records before changing web routing.

Once DNS resolves, GitHub can issue the TLS certificate. With Enforce HTTPS
enabled, HTTP visitors are redirected to HTTPS.
