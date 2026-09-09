# nilad.app

Marketing site for Nilad — static HTML on GitHub Pages, same shape as the
other `*_marketing` repos. The content plan lives in the app repo at
`nilad/docs/nilad-site-plan.md`; brand tokens in `nilad/docs/nilad-brand.html`.

## Pages

- `/` — hero, problem, how it works, facets, privacy strip, pricing strip
- `/pricing/` — the three App Store plans and FAQ
- `/privacy/` — plain-language privacy page
- `/support/` — support email (App Store requirement) and FAQ

## Placeholders to fill before launch

- [ ] Hero video: 12-second loop of the real intake (drag to notch, dot,
      confirmation card). Under 2 MB, muted, autoplay, loop, poster image.
      The CSS mocks stand in until then.
- [ ] "Coming soon to the Mac App Store" buttons → the real store /
      pre-order link (`index.html`, marked with a TODO).
- [ ] Real screenshots to replace or accompany the CSS product mocks.
- [ ] `support@nilad.app` mailbox must exist before the App Store record
      points here.

`og-image.png` is generated from the icon paths and brand palette; fonts
are self-hosted latin-subset variable woff2 (Newsreader, Instrument Sans).

Deferred to the direct-build launch (T+4 weeks): `/download`, `/help`,
`/changelog` (Sparkle appcast), `/story`, `/press`, comparison pages,
Paddle checkout.
