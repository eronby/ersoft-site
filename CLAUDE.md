# ER SOFT website — project context

Static one-page business site for **ER SOFT** (Eron Bylykbashi), a Microsoft Dynamics 365
Business Central / NAV developer & consultant (10+ years). Domain: **ersoft-ks.com** (registered at Porkbun).

## Files
- `index.html` — the whole site (inline CSS + JS, no build step). Sections: hero, Services,
  Work with me (freelance / contract / full-time / part-time), About, Contact form, footer.
- `CNAME` — `ersoft-ks.com` for GitHub Pages custom domain.
- `.nojekyll` — tells GitHub Pages to serve files as-is.

## How it works
- Bilingual EN / SQ (Albanian). English text lives in the HTML (`data-i18n` / `data-i18n-html` keys);
  Albanian strings are in the `T.sq` object in the `<script>`. Any new text needs a key + SQ translation.
  Language choice is saved in localStorage; defaults to SQ if browser language is Albanian.
- Contact form posts via fetch to FormSubmit: `https://formsubmit.co/ajax/contact@ersoft-ks.com`
  (no backend). First submission triggers an activation email to that address — must be confirmed.
- Colors are CSS variables in `:root`, with a dark-mode override via `prefers-color-scheme`.

## Hosting plan (decided)
GitHub Pages (public repo, branch `main`, root). Porkbun DNS:
- delete default ALIAS + `*` CNAME pointing to pixie.porkbun.com
- A @ → 185.199.108.153 / 109.153 / 110.153 / 111.153
- CNAME www → <github-username>.github.io
- Then enable "Enforce HTTPS" in repo Settings → Pages; verify the domain in GitHub profile Settings → Pages.

## Open TODOs
- [ ] Replace LinkedIn placeholder `https://www.linkedin.com/in/YOUR-PROFILE` (id="linkedin") with real URL
- [ ] Create GitHub repo, push these files, enable Pages + custom domain
- [ ] Porkbun DNS records (above)
- [ ] Set up Porkbun email forwarding for contact@ersoft-ks.com → Gmail
- [ ] Send a test form message and confirm FormSubmit activation email
- [ ] Optional: add a photo/logo, Open Graph image, privacy note for the form
