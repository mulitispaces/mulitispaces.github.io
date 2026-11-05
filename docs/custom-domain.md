# Custom domain configuration

Owner-selected domain: **multispace.beasonapps.com**. Migration completed and verified on November 5, 2026 (Asia/Taipei). The owner authorized the legal-content publication and domain setup. GitHub verification, the Cloudflare records, Pages binding, certificate issuance, HTTPS enforcement, and legal-page access are complete. The owner chose to retain the existing GitHub Pages URLs in the app and Google Play.

GitHub created the active root `CNAME` containing `multispace.beasonapps.com` in commit `5b678e2`, and that commit has been pulled into this checkout. `docs/custom-domain.CNAME` remains a same-value reference copy; it is not the active Pages configuration.

## Saved GitHub and Cloudflare configuration

- GitHub owner: `mulitispaces`; repository: `mulitispaces/mulitispaces.github.io`.
- GitHub **Settings → Pages** shows the exact hostname `multispace.beasonapps.com` as **Verified**. The parent `beasonapps.com` was not verified.
- The repository's Pages custom domain is `multispace.beasonapps.com`, with `protected_domain_state=verified`.
- The GitHub-generated verification TXT for this exact hostname is saved in Cloudflare. Retain its exact record name and value as supplied by GitHub; they are not reproduced here.
- Cloudflare has saved the following record for the `beasonapps.com` zone:

| Type | Name | Target | Proxy status | TTL |
| --- | --- | --- | --- | --- |
| CNAME | `multispace` | `mulitispaces.github.io` | DNS only (gray cloud) | Auto |

The target is a hostname, without `https://`, a repository name, or a page path. Keep it DNS only. Do not add conflicting A/AAAA records for `multispace` or change the root domain, MX records, or unrelated subdomains.

Only the exact hostname was verified because sibling subdomains already serve Pages sites under other GitHub accounts (`browser` → `si-browser.github.io`, `pdf` → `inkpdf.github.io`, and `phantom` → `multimorespace.github.io`). Do not expand verification to the parent `beasonapps.com`, since parent-domain verification could affect those apps.

## Verified HTTPS and legal-page access

GitHub's certificate is approved with CN/SAN `multispace.beasonapps.com`, issued by **Let's Encrypt YR2**, and valid until **February 3, 2027 at 07:37:21 Asia/Taipei**. **Enforce HTTPS is enabled**: the setting was checked in the Pages UI after refresh and confirmed by the API (`enforce=true`).

Both new legal pages return **HTTPS 200** and contain **Fidei Trading Limited** and **addaeisidore@gmail.com**, with no old contact email in the checked text. Their HTTP URLs return **301 to HTTPS**. The existing app links were also checked:

| Retained app/store URL | Verified final HTTPS destination |
| --- | --- |
| `https://mulitispaces.github.io/privacy-policy.html` | `https://multispace.beasonapps.com/privacy-policy.html` |
| `https://mulitispaces.github.io/terms.html` | `https://multispace.beasonapps.com/terms.html` |

For each old link, the observed chain is **old GitHub Pages HTTPS → 301 to new-domain HTTP → 301 to new-domain HTTPS → 200**. The final response is HTTPS; this is not a direct HTTPS-to-HTTPS redirect at every hop. The Android URL constants remain unchanged so installed versions keep their existing destinations. Google Play fields were not changed, in accordance with the owner's choice to keep the old URLs.

See [verification results](verification.json) for the deployment and redirect checks. The custom-domain URLs can be opened directly, but no app/store URL migration is required by this configuration. Account/app trader identity and actual operator contact details remain the owner's responsibility. This document does not change Play Console.

Earlier pre-configuration checks returned NXDOMAIN for the new hostname; those historical readiness results are superseded by the completed configuration and HTTPS checks. Local DNS was affected by a fake-IP proxy, so its synthetic `198.18.x`/IPv6 answers were not treated as public records. These checks establish observed access from the review environment, not availability in every country.

Required access: Cloudflare DNS editing for `beasonapps.com`, the `mulitispaces` account's Pages verification settings, and the website repository's Pages settings. No passwords or API tokens belong in this repository.

## Official references

- [Manage a GitHub Pages custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Verify domain ownership](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)
- [GitHub Pages HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
