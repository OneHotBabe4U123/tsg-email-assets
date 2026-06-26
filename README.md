# tsg-email-assets

Public static asset host for **The Sandhill Group — DC Policy Digest** email.

Images are served over a path-preserving CDN (jsDelivr) so the email renderer can
build deterministic URLs from a single base prefix.

## Usage

The renderer reads a base prefix from `TSG_EMAIL_ASSETS_BASE_URL` and appends the
asset path, e.g. `agency-seal__sec.png`:

```
https://cdn.jsdelivr.net/gh/OneHotBabe4U123/tsg-email-assets@main/entity-library/agency-seal/agency-seal__sec.png
```

Set in the email environment:

```bash
export TSG_EMAIL_ASSETS_BASE_URL="https://cdn.jsdelivr.net/gh/OneHotBabe4U123/tsg-email-assets@main"
```

For frozen, immutable image URLs in sent mail, pin a tag instead of `@main`
(e.g. `@v1`) so a future asset change cannot alter already-delivered emails.

## Contents

`entity-library/` — image classes consumed by the digest renderer:

- `agency-seal/` — US federal agency seals (public domain), used to label sections by agency
- `person/` — public-figure portraits
- `company-logo/` — organization logos
- `country-flag/`, `us-state-flag/` — flags
- `building/`, `map/`, `topic-illustrative/` — illustrative slots

Images only. Internal metadata (manifest / review JSON, per-class READMEs) is kept
in the private source repo, not here.
