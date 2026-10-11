# Binary Companion website

Source for <https://binarycompanion.com> (also <https://binary-companion.web.app>): a static single-page site
for Binary Companion, LLC. No build step.

- `public/index.html`, `public/styles.css`, `public/assets/` is the whole site.
- Hosted on Firebase Hosting, project `binary-companion`, site `binary-companion`. Both URLs above are served by
  that one site; DNS for `binarycompanion.com` is at Squarespace Domains and points at Firebase. Do not change
  the custom-domain settings in the Firebase console without checking DNS first.

## Deploying

Pushing to `main` runs `.github/workflows/deploy.yml`, which deploys through GitHub's OIDC identity
(Google Workload Identity Federation). There is **no stored key or token**: the Google Cloud provider only
accepts tokens from this repository's `production` environment, and that environment only runs from `main`.

To preview locally: `cd public && python3 -m http.server 8000`.

## Who can change `main`

The `Protect main` ruleset requires a pull request, blocks force pushes and deletion, and restricts updates
to the repository admin role (the owner). Anyone else contributes through a fork pull request, and only the
owner can merge it. A merge to `main` deploys the site, so that is the only gate.

## Related

- The TimeTug product site and policy pages live in <https://github.com/darkarena1/timetug> under `site/`.
