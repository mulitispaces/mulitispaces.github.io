# Multi Space legal website

Static English privacy policy and terms for the Android app `com.multispace.appcloner`.

- `index.html`: brand landing page and legal navigation.
- `privacy-policy.html`: local instance data, permissions, Google Mobile Ads/UMP, RevenueCat/Google Play purchases, Firebase configuration and Analytics choices, retention, deletion, and contact.
- `terms.html`: use of the app, compatibility, third-party applications, advertising, subscriptions and other purchases, updates, and legal rights.
- `assets/site.css`: responsive layout with automatic system light/dark appearance.
- `assets/multispace-logo.png`: existing Multi Space brand asset.
- `docs/custom-domain.CNAME`: inactive template for the proposed `multispace.beasonapps.com` binding.

The site needs no JavaScript, external fonts, package installation, or build step. The HTML includes the full policy text and is readable without scripting. It does not add tracking scripts, advertising, or cookies.

## Local preview

From the repository root:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open `http://127.0.0.1:8000/`. Python is only a convenient local preview server; GitHub Pages serves the static files without it.

## Publication

This repository is already served through GitHub Pages. `.nojekyll` keeps it a static HTML site. The owner approved pushing the November 5, 2026 legal revision after review. Publish the legal content on the existing Pages domain first; the custom-domain migration remains pending DNS and HTTPS readiness. If publication happens on a later date, review the displayed last-updated dates before publishing.

Existing public destinations used by the app:

- `https://mulitispaces.github.io/`
- `https://mulitispaces.github.io/privacy-policy.html`
- `https://mulitispaces.github.io/terms.html`

Before publication, logged-out HTTPS GET requests to the existing privacy and terms URLs returned HTTP 200 and HTML on November 5, 2026 (Asia/Taipei). Those checks covered the previous text; verify the deployed revision after pushing. The app's `MultiSpaceLegalLinks.kt` already points to these destinations.

The Google Play trader declaration's terms URL is `https://mulitispaces.github.io/terms.html`. Keep it an app-specific, publicly readable HTML page with valid HTTPS, no authentication, and no geographic restrictions. A successful request from this review environment does not prove accessibility from every country. Trader identity and operator contact details must remain accurate in Play Console; this repository does not change that declaration or invent an address or phone number.

The owner has selected **multispace.beasonapps.com** as the custom domain. The hostname still returned NXDOMAIN during the pre-push check, and Pages has no custom domain bound. An inactive CNAME template is stored under `docs/`; do not place it at the repository root until the domain migration is ready, because that could redirect working app links to an unresolved hostname. See the [migration plan](docs/custom-domain.md) for Cloudflare records, GitHub verification, and redirect checks. After migration and verification, the intended store URLs are `https://multispace.beasonapps.com/privacy-policy.html` and `https://multispace.beasonapps.com/terms.html`.

## Keeping disclosures accurate

The policy follows the checked-in commercial Universal configuration reviewed on November 5, 2026: Google Mobile Ads/UMP and RevenueCat/Google Play purchases are enabled; Firebase Remote Config supplies updates and feature settings. Firebase Analytics consent follows the app's privacy choice, while collection defaults remain disabled in the reviewed manifest; a consent update alone does not prove event collection is enabled. Automatic Crashlytics reporting is disabled. Internal builds, test products, and unverified provider configurations are not evidence of production data transfers.

Review the pages when those settings, SDKs, data flows, purchases, or backup rules change. Do not enable new collection merely because wording exists for a feature. Do not claim an actual purchase, ad delivery, Analytics upload, or mediation partner transfer has been verified from a source-only review.

The owner-supplied developer/service-provider name is **Fidei Trading Limited**, with private contact **addaeisidore@gmail.com**. The Multi Space brand, Android package and GitHub repository remain unchanged. The app's existing legal links are retained during the proposed domain migration, and its support email constant is synchronized with this revision; no Play Console identity declaration is changed here.

See [implementation notes](docs/implementation-notes.md) for the source basis and verification boundaries. A published policy is one part of release preparation; it does not replace Play Console Data safety, in-app access to the policy, permission disclosures, or any consent required for actual data processing.

Keep the published developer identity and private contact channel aligned with the app's store listing. Do not add an invented entity, address, retention period, or email account.
