# my-portfolio
My Portfolio Website

## Air Piano pages

The `air-piano/` directory adds a static, responsive product overview, support page,
privacy notice and German Impressum. It has no build step, JavaScript, analytics,
external fonts or CDN dependencies. The source was staged here for review and now has a dedicated repository:
[MarkusK146/air-piano-website](https://github.com/MarkusK146/air-piano-website), for
`airpiano.markuskapferer.de`. This portfolio PR remains an unmerged review record;
future website work belongs in the dedicated repository. The portfolio has its own existing dependencies; the
Air Piano privacy notice does not claim to audit them.

Planned URLs after publication:

- `https://airpiano.markuskapferer.de/`
- `https://airpiano.markuskapferer.de/support/`
- `https://airpiano.markuskapferer.de/privacy/`
- `https://airpiano.markuskapferer.de/impressum/`

### Draft status — do not deploy yet

All pages deliberately carry a review banner and `noindex, nofollow`. This is a
draft branch, not a published privacy policy or verified support channel.

- Owner confirmed publisher name and postal address for these public pages on
  21 October 2026. Do not import other contact details from account settings or
  the old portfolio without the owner's direction.
- The owner has created `airpiano@markuskapferer.de` as a forwarding address and
  reports that a self-sent test arrived in iCloud Mail. Replies use the receiving
  inbox's identity. Do not publish that private destination address.
- Public DNS routes incoming mail to STRATO (`smtpin.rzone.de`); the owner confirms
  Apple iCloud Mail receives the forwarded messages. Account-specific forwarding
  arrangements still need confirmation. No mail DNS was changed.
- Confirm the intended reply identity. Sending as `airpiano@markuskapferer.de`
  requires a suitable authenticated outgoing account; forwarding alone does not
  configure that. No external sender or outgoing support-identity test is claimed.
- Complete the email-provider paragraph in the privacy notice with both actual
  services and their privacy/transfer information. Confirm the proposed purposes,
  legal bases and retention criteria reflect the publisher's support practices.
- Confirm any applicable register/tax identification details and other required
  publisher information. No register number, VAT ID, business ID or phone number
  has been invented. The legal notice is a prepared draft, not a legal compliance
  certification.
- Resolve and remove every `.review-note`, the `.draft` banners, and the robots
  draft directives only when those inputs are settled. Add a link from the
  portfolio's navigation/footer when publishing.
- Deploy as a separate site following [the hosting handoff](air-piano/DEPLOYMENT.md).
  Merging this portfolio PR alone does not attach the subdomain.
- After deployment, verify all four HTTPS URLs, then set the support/privacy
  URLs in App Store Connect and add the working policy link to the iOS app.
  Current Air Piano candidate 0.1.0 (2) has not been changed by these website files.

Local preview: `python3 -m http.server 8765 --bind 127.0.0.1 --directory air-piano`,
then open `http://127.0.0.1:8765/support/`. The folder is the future site's document
root. Its nested `CNAME` names the new subdomain; the portfolio's root `CNAME` and
live Pages configuration remain unchanged. See [DEPLOYMENT.md](air-piano/DEPLOYMENT.md)
for the observed DNS, required destination and publication sequence.

Verified locally on 21 October 2026: all four pages render and navigate in the
browser; support accordions and privacy section anchors work. Desktop support
(1280 px), phone support (390 px), and narrow privacy/Impressum/overview layouts
(320 px) were checked without horizontal overflow. Internal links, anchor targets,
single page headings, absence of scripts and draft metadata passed a static check.
No browser warnings/errors were reported during the preview. These were browser checks of the initial nested preview. The owner later reported
successful incoming forwarding to iCloud; independent email delivery, sending as
the support address and live GitHub Pages deployment remain untested.

### Subdomain preparation verification

All four pages now have relative internal links and production canonical URLs for
`airpiano.markuskapferer.de`. Link/anchor, single-H1, draft metadata, no-script,
public-mail-link and both-CNAME checks passed. The first static check encountered
macOS's `/tmp` → `/private/tmp` path alias; resolving the root path corrected the
checker, with no website change needed. `git diff --check` passes.

A fresh browser preview served `air-piano/` as `/`: overview → support → privacy
anchor → Impressum → overview navigation worked with CSS loaded and no reported
console warnings/errors. The portfolio link points to its separate HTTPS domain.
This verifies local routes, not public DNS, live TLS or deployment.

### Content references

App behavior was checked against Air Piano's current source and release record:
local sound/preferences, explicit schema-3 JSON export and no Air Piano backend.
The privacy notice distinguishes Apple's automatic TestFlight collection from
user-initiated diagnostic exports. External policy references checked 21 October 2026:

- [Apple TestFlight & Privacy](https://www.apple.com/legal/privacy/data/en/test-flight/)
- [GitHub Pages data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection)
- [GitHub General Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement)
- [European Commission: individual privacy rights](https://commission.europa.eu/law/law-topic/data-protection/information-individuals_en)
- [§ 5 DDG](https://www.gesetze-im-internet.de/ddg/__5.html)
- [BayLDA complaints](https://www.lda.bayern.de/de/beschwerde.html)
- [STRATO mailbox administration](https://www.strato.de/faq/mail/e-mail-adressen-einrichten-und-bearbeiten/)
- [STRATO privacy notice](https://www.strato.de/datenschutz/)
- [Apple privacy policy](https://www.apple.com/legal/privacy/en-ww/)
- [iCloud custom-domain setup](https://support.apple.com/en-au/guide/icloud/mma473945269/1.0)
