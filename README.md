# Multi Space legal website

Static English privacy policy and terms for the Android app `com.multispace.appcloner`.

- `index.html`: brand landing page and legal navigation.
- `privacy-policy.html`: local instance data, permissions, Firebase Remote Config, providers, retention, deletion, and contact.
- `terms.html`: use of the app, compatibility, third-party applications, updates, and legal rights.
- `assets/site.css`: responsive layout with automatic system light/dark appearance.
- `assets/multispace-logo.png`: existing Multi Space brand asset.

The site needs no JavaScript, external fonts, package installation, or build step. The HTML includes the full policy text and is readable without scripting. It does not add tracking scripts, advertising, or cookies.

## Local preview

From the repository root:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open `http://127.0.0.1:8000/`. Python is only a convenient local preview server; GitHub Pages serves the static files without it.

## Publication

Enable GitHub Pages in the repository's **Settings → Pages**, choose **Deploy from a branch**, then the approved publication branch and **/(root)**. `.nojekyll` prevents unnecessary Jekyll processing.

Expected URLs after GitHub Pages has actually deployed:

- `https://mulitispaces.github.io/`
- `https://mulitispaces.github.io/privacy-policy.html`
- `https://mulitispaces.github.io/terms.html`

These addresses are expected deployment destinations, not evidence that the site is already live. Do not submit a policy URL to Google Play until a logged-out HTTPS request returns the actual policy page.

## Keeping disclosures accurate

The policy describes the currently reviewed Android configuration: Firebase Remote Config is used, while Analytics collection, automatic Crashlytics reporting, and commercial advertising/purchase initialization are disabled. Review the policy when those settings, SDKs, data flows, purchases, or backup rules change. Do not enable new collection merely because wording exists for a future feature.

See [implementation notes](docs/implementation-notes.md) for the source basis and verification boundaries. A published policy is one part of release preparation; it does not replace Play Console Data safety, in-app access to the policy, permission disclosures, or any consent required for actual data processing.

Keep the published developer identity and private contact channel aligned with the app's store listing. Do not add an invented entity, address, retention period, or email account.
