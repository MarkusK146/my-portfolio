# Air Piano website deployment

Target: **https://airpiano.markuskapferer.de/**. This folder is the complete static
site document root. It contains the overview, `/support/`, `/privacy/`,
`/impressum/`, local CSS, `.nojekyll` and the site's `CNAME`. No build step is needed.

## Current state

The source has a dedicated public repository, `MarkusK146/air-piano-website`.
It remains a review draft; Pages deployment is not enabled. Portfolio draft PR #5
is retained as the original review handoff and must not be merged to publish this
standalone site. The portfolio's existing root `CNAME` and Pages configuration serve
`https://markuskapferer.de/` from `main` at `/`; leave that configuration in place.
The dedicated repository's root `CNAME` names `airpiano.markuskapferer.de`.
The portfolio draft keeps the same file nested under `air-piano/`; that nested
file does not alter the portfolio's domain. DNS and Pages still need configuration.

On 21 October 2026 a public DNS lookup returned no CNAME for the new subdomain,
A `217.160.0.90` and AAAA `2001:8d8:100f:f000::200`. Those values are not the
GitHub Pages destination. DNS/provider settings have not been changed by this work.

## Preview and check

From the dedicated website checkout:

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

For the historical portfolio draft, add `--directory air-piano`.

Open `http://127.0.0.1:8765/`, then test Support, Privacy, Impressum, section anchors,
and the FAQ disclosures. Relative navigation also permits the existing nested
`/air-piano/` preview. The Portfolio footer link intentionally opens the separate
portfolio domain. Canonical URLs identify the intended production subdomain;
`noindex, nofollow` remains in place while the content is a review draft.

## Publication sequence

1. Resolve the contact/privacy/publisher review notes listed in the repository
   README. Incoming forwarding to iCloud has been self-tested by the owner;
   replies currently use that inbox's identity. Confirm the intended reply setup
   and applicable provider arrangements. Remove draft markers only after review.
2. Use `MarkusK146/air-piano-website` as the Pages site, publishing `main` at `/`.
   It contains the already-public draft content; source publication does not mean
   the website has been deployed. Finish content review before enabling Pages.
3. Configure that site's custom domain as `airpiano.markuskapferer.de` in GitHub
   Settings → Pages before pointing DNS at it. Preserve the portfolio's domain.
4. At the DNS provider, set only the `airpiano` web hostname to a CNAME with target
   `markusk146.github.io`. It must not contain a scheme, slash or repository name.
   Replace conflicting A/AAAA records for this exact hostname as required by the
   provider. Leave the apex, portfolio and email/MX records alone. Verify the
   domain with GitHub where needed; do not invent a verification TXT value.
5. Wait for GitHub's domain check and certificate, enable HTTPS enforcement, and
   verify all four HTTPS URLs with valid TLS, CSS, navigation and mail links.
6. Update App Store Connect with `/support/` and `/privacy/` on this subdomain,
   then add the verified live policy URL to the iOS app and build/test a new
   candidate. Do not claim the current 0.1.0 (2) build contains the future URL.

Sources checked 21 October 2026:

- [GitHub custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)
- [GitHub custom-domain setup](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
