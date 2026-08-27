# SafeShare V1.0 App Store Web Pack

This directory is a deployment-ready static source pack for the public SafeShare support and privacy pages.

## Public routes

- `privacy.html` — Simplified Chinese and English Privacy Policy
- `support.html` — Simplified Chinese and English Support page
- `index.html` — lightweight landing page linking to both public routes

The two App Store URLs should ultimately resolve to separate, public HTTPS pages without login:

- Privacy Policy URL: `https://zhangyiconge6.github.io/safeshare-support/privacy.html`
- Support URL: `https://zhangyiconge6.github.io/safeshare-support/support.html`

Hosting repository: `zhangyiconge6/safeshare-support`.

## Recommended GitHub Pages setup

The existing Spinertia release uses a dedicated GitHub Pages repository with stable `privacy.html` and `support.html` routes. SafeShare can follow the same pattern without sharing Spinertia's repository or URLs:

1. Create a dedicated repository for the SafeShare public pages.
2. Copy the contents of this directory to the publishing branch root.
3. Enable GitHub Pages for that branch and root directory.
4. Confirm that both public URLs use HTTPS and require no login.
5. Verify `#zh-Hans` and `#english` anchors on both pages.
6. Add the final URLs to App Store Connect only after the public pages pass the deployment checklist below.

Do not point SafeShare to the Spinertia URLs.

## Required replacements before deployment

Confirmed release values:

- Support email: `gdni_support@163.com`
- GitHub repository: `zhangyiconge6/safeshare-support`
- Privacy Policy URL: `https://zhangyiconge6.github.io/safeshare-support/privacy.html`
- Support URL: `https://zhangyiconge6.github.io/safeshare-support/support.html`

## Deployment checklist

- [x] Replace both support email placeholders with the confirmed address.
- [x] Confirm Simplified Chinese and English contact details match.
- [ ] Confirm effective date remains consistent with the frozen in-app policy.
- [ ] Confirm no product or privacy facts changed after this source pack was prepared.
- [ ] Open `privacy.html#zh-Hans` and `privacy.html#english` from the public URL.
- [ ] Open `support.html#zh-Hans` and `support.html#english` from the public URL.
- [ ] Check the pages on a narrow phone viewport and a desktop viewport.
- [ ] Confirm all internal links use the public site and return HTTP 200.
- [ ] Confirm HTTPS works without login, redirects, consent walls, or region restrictions.
- [ ] Confirm the public pages contain no analytics, advertising, tracking, or third-party scripts.
- [ ] Paste the final Privacy Policy URL and Support URL into the matching App Store Connect fields.

## Local preview

From the repository root:

```sh
python3 -m http.server 8767 --directory release/app-store-web
```

Then open `http://localhost:8767/`.

## Source-of-truth boundary

The privacy language is based on the frozen SafeShare V1.0 in-app Privacy Policy and verified release facts. These web files do not change the app, its localization, or its behavior. If SafeShare's data handling changes in a future version, review both languages and the App Store privacy disclosure before publishing an updated policy.
