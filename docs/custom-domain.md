# Proposed custom domain

Owner-selected domain: **multispace.beasonapps.com**. Prepared on November 5, 2026 (Asia/Taipei). The owner has approved pushing the legal content. Domain migration remains pending DNS and HTTPS readiness; no DNS or GitHub Pages domain setting has been changed.

The inactive template `docs/custom-domain.CNAME` contains this hostname. A root `CNAME` on the Pages publication branch can change the site's domain configuration. Keep the template under `docs/` until migration is ready, then move/copy it to the root as part of that migration. The current legal-content publication deliberately leaves the working `github.io` domain in place.

## Read-only readiness checks

Google and Cloudflare public DNS-over-HTTPS results agreed:

- `beasonapps.com` uses `kehlani.ns.cloudflare.com` and `randy.ns.cloudflare.com`.
- `multispace.beasonapps.com` has no existing public CNAME, A, AAAA, TXT or CAA record (NXDOMAIN at review).
- The root domain has no CAA restriction; no additional CAA record is needed for the proposed GitHub Pages certificate on the evidence reviewed.
- Public DNS cannot establish whether another GitHub account has claimed the domain. Verify ownership in GitHub before binding it.

Local DNS was affected by a fake-IP proxy, so its synthetic `198.18.x`/IPv6 answers were not treated as public records.

## Approved migration steps

1. In the `mulitispaces` GitHub account's personal **Settings → Pages**, verify `beasonapps.com`. GitHub supplies the actual verification TXT value. Add that exact value in Cloudflare; do not invent it. A verified root domain covers its immediate subdomains. Retain the verification record.
2. Publish the approved legal revision and bind **multispace.beasonapps.com** in the website repository's **Settings → Pages → Custom domain**. Coordinate the checked-in `CNAME` with the Pages setting; saving that setting can itself create a commit on a branch-based Pages site.
3. Add this record in Cloudflare for `beasonapps.com`:

| Type | Name | Target | Proxy status | TTL |
| --- | --- | --- | --- | --- |
| CNAME | `multispace` | `mulitispaces.github.io` | DNS only (gray cloud) | Auto |

The target is a hostname, without `https://`, a repository name, or a page path. This migration requires no root-domain, MX, or other subdomain changes. Do not add conflicting A/AAAA records for `multispace`.

4. Wait for GitHub's DNS check and TLS certificate issuance, then enable **Enforce HTTPS**.
5. Verify logged-out access to both new pages, their updated developer name/email and text, and the redirects from both existing app links:

| Existing app URL | Intended new destination |
| --- | --- |
| `https://mulitispaces.github.io/privacy-policy.html` | `https://multispace.beasonapps.com/privacy-policy.html` |
| `https://mulitispaces.github.io/terms.html` | `https://multispace.beasonapps.com/terms.html` |

The old links are expected to redirect after binding, but that has not happened or been verified in this revision. The Android URL constants are retained so installed versions keep using their existing destinations. Verify redirect behavior before relying on it or changing app/store URLs.

6. Only after both new pages pass verification, use the new terms URL for the Google Play trader declaration and the new privacy URL in the appropriate store fields. Account/app trader identity and actual operator contact details remain the owner's responsibility. This document does not change Play Console.

Required access: Cloudflare DNS editing for `beasonapps.com`, the `mulitispaces` account's Pages verification settings, and the website repository's Pages settings. No passwords or API tokens belong in this repository.

## Official references

- [Manage a GitHub Pages custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Verify domain ownership](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)
- [GitHub Pages HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
