# Multi Space legal website

Static English privacy policy and terms for the Android app `com.multispace.appcloner`.

- `index.html`: brand landing page and legal navigation.
- `privacy-policy.html`: local instance data, permissions, Google Mobile Ads/UMP, RevenueCat/Google Play purchases, Firebase configuration and Analytics choices, retention, deletion, and contact.
- `terms.html`: use of the app, compatibility, third-party applications, advertising, subscriptions and other purchases, updates, and legal rights.
- `assets/site.css`: responsive layout with automatic system light/dark appearance.
- `assets/multispace-logo.png`: existing Multi Space brand asset.
- `CNAME`: active GitHub Pages custom-domain configuration for `multispace.beasonapps.com`.
- `docs/custom-domain.CNAME`: same-hostname reference copy; the root `CNAME` is the Pages configuration.

The site needs no JavaScript, external fonts, package installation, or build step. The HTML includes the full policy text and is readable without scripting. It does not add tracking scripts, advertising, or cookies.

## Local preview

From the repository root:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open `http://127.0.0.1:8000/`. Python is only a convenient local preview server; GitHub Pages serves the static files without it.

## Publication

This repository is served through GitHub Pages under the GitHub owner `mulitispaces`. `.nojekyll` keeps it a static HTML site. The owner approved publishing the November 5, 2026 legal revision and configuring the custom domain. The custom-domain migration is complete: domain verification, DNS, Pages binding, the certificate, HTTPS enforcement, and legal-page access have been checked.

Existing public destinations retained for the app and Google Play:

- `https://mulitispaces.github.io/`
- `https://mulitispaces.github.io/privacy-policy.html`
- `https://mulitispaces.github.io/terms.html`

On November 5, 2026 (Asia/Taipei), both existing HTTPS legal links were verified to follow this chain: old GitHub Pages HTTPS URL → HTTP 301 to the custom-domain HTTP URL → HTTP 301 to the custom-domain HTTPS URL → HTTP 200. The final pages use HTTPS; the redirect chain includes an intermediate HTTP URL. The owner chose to retain the existing app and Google Play URLs. The app's `MultiSpaceLegalLinks.kt` URL constants and Play Console fields are unchanged.

The retained terms destination is `https://mulitispaces.github.io/terms.html`. The Google Play trader declaration needs an app-specific, publicly readable HTML terms page with valid HTTPS, no authentication, and no geographic restrictions. The checked old terms link reaches the correct final HTTPS page without a login. A successful request from this review environment does not prove accessibility from every country. Trader identity and operator contact details must remain accurate in Play Console; this repository does not change that declaration or invent an address or phone number.

As of November 5, 2026, **multispace.beasonapps.com** is verified for the `mulitispaces` GitHub account, and Pages is bound to it with `protected_domain_state=verified`. Only this exact hostname was verified; the parent domain was not verified. Cloudflare has saved the GitHub-generated verification TXT and the `multispace` CNAME targeting `mulitispaces.github.io` with **DNS only** proxy status and **Auto** TTL. GitHub created the root `CNAME` in commit `5b678e2`, which has been pulled into this checkout. Retain the exact verification TXT; its value need not be copied into this repository.

GitHub's certificate is approved for `multispace.beasonapps.com`, and **Enforce HTTPS is enabled** in the refreshed Pages UI and API (`enforce=true`). Both `https://multispace.beasonapps.com/privacy-policy.html` and `https://multispace.beasonapps.com/terms.html` return HTTPS 200 with the correct developer and email; no old email remains in the checked page text. Requests to the custom-domain HTTP URLs return 301 to HTTPS. See the [completed domain configuration](docs/custom-domain.md) and [verification results](docs/verification.json), including the certificate details and redirect boundaries. The custom-domain URLs are available directly, while the existing app/store URLs remain the owner's selected destinations.

## Keeping disclosures accurate

The policy follows the checked-in commercial Universal configuration reviewed on November 5, 2026: Google Mobile Ads/UMP and RevenueCat/Google Play purchases are enabled; Firebase Remote Config supplies updates and feature settings. Firebase Analytics consent follows the app's privacy choice, while collection defaults remain disabled in the reviewed manifest; a consent update alone does not prove event collection is enabled. Automatic Crashlytics reporting is disabled. Internal builds, test products, and unverified provider configurations are not evidence of production data transfers.

Review the pages when those settings, SDKs, data flows, purchases, or backup rules change. Do not enable new collection merely because wording exists for a feature. Do not claim an actual purchase, ad delivery, Analytics upload, or mediation partner transfer has been verified from a source-only review.

The owner-supplied developer/service-provider name is **Fidei Trading Limited**, with private contact **addaeisidore@gmail.com**. The Multi Space brand, Android package and GitHub repository remain unchanged. The app's existing legal links are retained after domain migration, and its support email constant is synchronized with this revision; no Play Console identity declaration is changed here.

See [implementation notes](docs/implementation-notes.md) for the source basis and verification boundaries. A published policy is one part of release preparation; it does not replace Play Console Data safety, in-app access to the policy, permission disclosures, or any consent required for actual data processing.

Keep the published developer identity and private contact channel aligned with the app's store listing. Do not add an invented entity, address, retention period, or email account.
