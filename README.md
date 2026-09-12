# RoleDaemon™ homepage

A production-ready static homepage for [RoleDaemon.com](https://roledaemon.com), deployable directly to GitHub Pages with no build step.

## Publish on GitHub Pages

1. Create the organization-site repository `RoleDaemon/RoleDaemon.github.io` (recommended), or use another repository in the organization.
2. Copy every file and folder from this package to the repository root, commit, and push to `main`.
3. Open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then select `main` and `/(root)`. Save.
4. Under **Custom domain**, enter `roledaemon.com` and save. Keep the included `CNAME` in the publishing root.
5. After DNS resolves and GitHub provisions the certificate, enable **Enforce HTTPS**.

The included `.nojekyll` file tells GitHub Pages to serve the package as plain static files.

## Cloudflare DNS

In Cloudflare **DNS → Records**, add these **DNS only** records (gray cloud) while GitHub provisions the site and certificate:

| Type | Name | Target |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `RoleDaemon.github.io` |

Remove conflicting `A`, `AAAA`, `ALIAS`, `ANAME`, or `CNAME` records for `@` or `www`. GitHub also recommends verifying the domain at the organization level before attaching it, which helps prevent domain takeover.

Official references: [publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site), [custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages), and [HTTPS/DNS records](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https).

## Local preview

Open `index.html` directly or serve the folder with any static HTTP server. No dependencies are required.

## Customize

- Edit product copy in `index.html`.
- Replace `assets/mascot.png` while preserving the filename.
- Replace `assets/social-card.png` after major messaging changes.
- Palette tokens live at the top of `styles.css`.

## Brand palette

Core: `#0F084B`, `#26408B`, `#3D60A7`, `#81B1D5`, `#A0D2E7`.

Semantic only: warning `#FFB000`, error `#FF5A5F`, success `#38D996`, information `#5CC8FF`.

