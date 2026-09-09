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
- [ ] "Coming soon to the Mac App Store" button → the real store /
      pre-order link (`index.html`, marked with a TODO).
- [ ] Self-hosted fonts (Newsreader, Instrument Sans) in `fonts/` like the
      other sites; pages currently fall back to Georgia / system sans.
- [ ] `og-image.png` and screenshots.
- [ ] `support@nilad.app` mailbox must exist before the App Store record
      points here.

Deferred to the direct-build launch (T+4 weeks): `/download`, `/help`,
`/changelog` (Sparkle appcast), `/story`, `/press`, comparison pages,
Paddle checkout.
