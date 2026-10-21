# my-portfolio
My Portfolio Website

## Air Piano pages

The `air-piano/` directory adds a static, responsive product overview, support page,
privacy notice and German Impressum. It has no build step, JavaScript, analytics,
external fonts or CDN dependencies. The rest of the portfolio has its own existing
dependencies; the Air Piano privacy notice does not claim to audit them.

Planned URLs after publication:

- `https://markuskapferer.de/air-piano/`
- `https://markuskapferer.de/air-piano/support/`
- `https://markuskapferer.de/air-piano/privacy/`
- `https://markuskapferer.de/air-piano/impressum/`

### Draft status — do not deploy yet

All pages deliberately carry a review banner and `noindex, nofollow`. This is a
draft branch, not a published privacy policy or verified support channel.

- Owner confirmed publisher name and postal address for these public pages on
  21 October 2026. Do not import other contact details from account settings or
  the old portfolio without the owner's direction.
- The owner has created `airpiano@markuskapferer.de` as a forwarding address to
  their existing inbox. Successful receipt and the sender shown on replies still
  need verification. The destination address is not needed in public documentation.
- Public DNS routes mail to STRATO (`smtpin.rzone.de`), but the owner still needs
  to confirm the forwarding provider and the receiving inbox provider. No mail
  routing migration is planned for this setup and no DNS was changed.
- Verify delivery from an independent sender and confirm the reply identity.
  A forwarding address alone does not establish the ability to send replies as
  `airpiano@markuskapferer.de`; do not claim that this has been configured or tested.
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
- After merge/deployment, verify all four HTTPS URLs, then set the support/privacy
  URLs in App Store Connect and add the working policy link to the iOS app.
  Current Air Piano candidate 0.1.0 (2) has not been changed by these website files.

Local preview: `python3 -m http.server 8765 --bind 127.0.0.1`, then open
`http://127.0.0.1:8765/air-piano/support/`. The custom-domain root paths match the
existing `CNAME`. Website DNS and the Pages publishing configuration are unchanged.

Verified locally on 21 October 2026: all four pages render and navigate in the
browser; support accordions and privacy section anchors work. Desktop support
(1280 px), phone support (390 px), and narrow privacy/Impressum/overview layouts
(320 px) were checked without horizontal overflow. Internal links, anchor targets,
single page headings, absence of scripts and draft metadata passed a static check.
No browser warnings/errors were reported during the preview. Mail delivery and
live GitHub Pages deployment remain untested.

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
- [iCloud custom-domain setup](https://support.apple.com/en-au/guide/icloud/mma473945269/1.0)
