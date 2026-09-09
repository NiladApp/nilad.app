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

## Claims register

Every factual claim on the site, and where it's true in the app repo.
Re-check this list when editing copy here or behaviour there. Audited
2026-09-09.

| Claim | Source of truth |
| :-- | :-- |
| Nothing uploaded; no analytics/accounts; network log stays empty | `NetworkGate` has no endpoints; `PrivacyTests` fails the build on any other networking |
| Reads with Vision + Foundation Models on the Neural Engine | `NiladCore/Pipeline` (Vision OCR, `ModelUnderstanding`) |
| Apple Silicon + macOS 26 only | `project.yml` (`ARCHS: arm64`, `deploymentTarget: 26.0`) |
| Drop on the notch; scan from iPhone | `NotchDropController`; `CameraCapture` (Continuity Camera) |
| "agl over 200"-style search | `SearchQuery.parse`, covered in `SearchEngineTests` |
| Views / types / tags sidebar with counts; running total | `FacetCounts`, `SavedViewStore` defaults, `SearchEngine.totals` |
| Filter to the tax year (not quarters — no quarter filter exists) | `DocumentFilter.Period.thisTaxYear` |
| Low-confidence fields wait in Needs review; corrections teach Nilad | `ConfidenceGate`, `DetailWindow` |
| First 25 documents free (App Store build) | `Trial.masFreeDocuments` |
| Lapse/free-tier pauses intake only; reading + export never lock | `Trial.intakeAllowed` / `libraryReadable` / `exportAllowed`, enforced by `TrialTests` |
| Export = searchable PDFs + one CSV (not byte-original files) | `LibraryExporter` (`derivedPDF ?? originalFile`) |
| Settings → Library shows the location, opens Finder, exports | `SettingsView.LibrarySettings` |
| $4.99 / $34.99 / $79.99; lifetime includes every future version | `Nilad.storekit`, spec §11 |
| No education discount offered (no App Store mechanism) | removed 2026-09-09; revisit with the Paddle direct build |
