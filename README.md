# RoleDaemon website

Static dark-mode marketing site. Serve this directory as the web root. No build step or runtime dependencies.

The business model remains undecided. All product UI is explicitly illustrative, with fictional examples. Registration is disabled because no backend endpoint exists. No resumes or signup information are collected.

## Assets

Local Sora and Inter WOFF2 fonts and licenses; local Iconoir SVGs and license; outlined wordmarks, favicon/app icons, eight optimized mascot poses, responsive AVIF/WebP text-free hero artwork, social images, reusable HTML product previews and application-state designs. See assets/manifest.json. Large original PNGs are preserved in prior Git history, not loaded by the site.

## Validation

Local Lighthouse mobile: performance 99, accessibility 100, best practices 100, SEO 100. Initial load 139 KiB. Five requested widths checked: 320, 375, 768, 1024, 1440. No horizontal overflow. Mobile navigation and Escape focus restoration tested. Local links and assets checked. Console errors absent during browser checks. No live product functionality is implied by preview controls.

## Publication

This checkout contains the finished replacement. Authenticate Git as an account with write access to RoleDaemon/RoleDaemon.github.io, then from this directory run:

    git push origin HEAD:main

This is a normal fast-forward push; do not force. If main advances, fetch and reconcile changes before pushing. The previously created remote branch redesign/dark-intelligence points to the original baseline until the replacement is pushed.

GitHub Pages already deploys the main branch at the root. CNAME remains roledaemon.com; .nojekyll is preserved. Wait for the Pages build to succeed and verify the homepage, /privacy/, /contact/, and /assets/social/default-og.png.

## Existing domain problem

HTTP apex is working; HTTP www redirects to the apex. HTTPS certificate hostname verification fails for apex and www. This issue predates the redesign. DNS was inspected, not modified: four DNS-only apex A records 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153; DNS-only www CNAME roledaemon.github.io. No conflicting AAAA records were present. Cloudflare proxy is off, so its SSL setting does not serve the website certificate.

Sign in as the RoleDaemon repository owner and open https://github.com/RoleDaemon/RoleDaemon.github.io/settings/pages. Confirm main / (root), custom domain roledaemon.com, and inspect the certificate provisioning message. Allow GitHub to finish provisioning; resolve any specific validation error shown there. Enable Enforce HTTPS once available. Verify https://roledaemon.com and https://www.roledaemon.com with normal certificate checks; www should redirect to the canonical apex. Do not change these correct DNS records or bypass certificate verification to disguise the problem.

## Before registration opens

Implement a real endpoint and privacy disclosures before enabling the form. Document provider use, retention, export and deletion. Revisit product capability statements against the actual application. No licensing or delivery-model commitments should be added without a deliberate decision.
