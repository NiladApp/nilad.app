# nilad.app

Static HTML marketing site for Nilad, hosted on GitHub Pages.
Current release reference: `../nilad/specs/app-store-submission.md`.
Brand reference: `../nilad/docs/nilad-brand.html`.

## Pages

- `/` — product overview, actual app screenshots, privacy and planned pricing
- `/pricing/` — free tier, purchase options and billing FAQ
- `/privacy/` — local app data, Apple purchases, hosting and support email
- `/support/` — support contact, requirements and FAQ
- `/terms/` — purchases, subscriptions, refunds and standard Apple EULA

## Before launch

- [ ] Replace both “Coming soon” spans with the real App Store/preorder link when available.
- [ ] Confirm production prices; displayed amounts are explicitly planned US prices, not live storefront offers.
- [ ] Verify that `support@nilad.app` receives messages and can reply.
- [ ] Review the policy against the actual support email provider and retention practices.
- [ ] Publish the reviewed changes. Editing these files alone does not update GitHub Pages.

Screenshots in `images/01-library.jpg` through `images/04-document-details.jpg`
come from the actual app with fictional fixtures. Refresh from
`../nilad/specs/screenshots/` after material UI changes. Images are linked at full
resolution, have descriptive alt text and explicit dimensions, and are lazy loaded
below the hero. Fonts remain self-hosted.

## Claims register

Checked against the promoted app on 29 September 2026. Paths below are relative to
`../nilad/`. Recheck copy and metadata when app behavior changes.

| Claim | Source of truth |
| --- | --- |
| Document processing stays local; no tracking or analytics SDKs | `Nilad/Resources/PrivacyInfo.xcprivacy`, `ArchiveCore/Package.swift`, `ArchiveCore/Sources/ArchiveCore/Understanding.swift` |
| Apple handles purchases and restoration | `Nilad/Integration/Purchases.swift` |
| Apple Silicon, macOS 26+ | `project.yml` |
| Apple Intelligence optional; OCR/search fallback remains available | `ArchiveCore/Sources/ArchiveCore/Understanding.swift`, `Nilad/LibraryView.swift` |
| Library/menu-bar/notch intake | `Nilad/Integration/ApplicationDelegate.swift`, `Nilad/Integration/FileDrops.swift` |
| Full-text, structured and semantic search | `ArchiveCore/Sources/ArchiveCore/Search.swift`, `ArchiveCore/Tests/ArchiveCoreTests/ArchiveTests.swift` |
| Editable metadata, tags and saved views | `Nilad/Views/DocumentView.swift`, `Nilad/LibraryView.swift` |
| Corrections guide suggestions without guaranteeing accuracy | `ArchiveCore/Sources/ArchiveCore/Understanding.swift`, `ArchiveCore/Sources/ArchiveCore/ArchiveStore.swift` |
| 25-document free tier; paid unlimited intake | `ArchiveCore/Sources/ArchiveCore/Licensing.swift`, `Nilad/LibraryState.swift` |
| Reading, search and export remain available without purchase | `ArchiveCore/Sources/ArchiveCore/Licensing.swift`, `Nilad/Views/PreferencesView.swift` |
| Export uses PDFs where available, otherwise originals, plus CSV and JSON | `ArchiveCore/Sources/ArchiveCore/ArchiveTransfer.swift` |
| Index-in-place preserves external originals | `ArchiveCore/Sources/ArchiveCore/IntakeQueue.swift`, `ArchiveCore/Sources/ArchiveCore/ArchiveStore.swift` |
| Local snapshots/change history retain metadata | `ArchiveCore/Sources/ArchiveCore/ArchiveStore.swift`, `ArchiveCore/Sources/ArchiveCore/DocumentChanges.swift` |
| Planned US price amounts only | `Nilad.storekit`; confirm production pricing separately in App Store Connect |

## Local preview

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Open `http://127.0.0.1:8765/`. Check every page at desktop and mobile widths,
links, screenshots, keyboard navigation and reduced motion before publishing.
