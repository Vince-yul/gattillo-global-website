# Gattillo Global — Logo & Brand Mark Usage

Rule set for when to use the full logo lockup, the wordmark, the tagline, and the GG symbol across the website (and other Gattillo Global collateral). Adopted 2026-08-19.

## The three levels

1. **GG** — the icon/symbol. Secondary brand device.
2. **GATTILLO GLOBAL.** — the corporate brand (wordmark).
3. **"WE POWER ENTERTAINMENT."** — the positioning statement / brand promise.

Don't default to stacking all three ("GATTILLO GLOBAL / WE POWER ENTERTAINMENT.") on every page — that reads as a sales brochure, not a contemporary global brand. Split them so visitors learn to recognize Gattillo Global as the company and "We power entertainment." as what it stands for.

## Where each element goes

- **Header, every page**: GG symbol + GATTILLO GLOBAL, compact. This is the consistent corporate identifier. No tagline here.
- **Homepage hero**: "WE POWER ENTERTAINMENT." featured prominently as the positioning statement, followed by one short line explaining what it means. Elsewhere, use the tagline selectively, only where it adds meaning — it does not need to accompany the wordmark every time.
- **GG symbol alone**: use as a secondary device — favicon, mobile navigation, footer detail, subtle backgrounds, section transitions, social avatars. Treat it as a signature, not decoration; don't stamp it everywhere.
- **Footer, every page**: the complete signature — GG + GATTILLO GLOBAL + "We power entertainment." — since the footer is the one place the full lockup belongs.

## The GG mark itself

The GG symbol is the actual overlapping-G monogram from the master logo (`Business-Docs/LOGOs/GattilloGlobal_logo_transparency.png`) — not a placeholder or a stylized initial. It was cropped from the real transparent source (`Business-Docs/LOGOs/email-signatures/gattillo-logo-black-transparent-full.png`, the one file in the logo folder with genuine alpha transparency) at the natural gap between the icon and the "GATTILLO" wordmark, then recolored per background:

- `assets/gg-icon-bone.png` / `concepts/premiere-red/img/gg-icon-bone.png` — bone/cream (`#EDE6D8`), for the site's dark backgrounds. This is the one actually used on every page (duplicated in both locations — see deployment note below).
- `assets/gg-icon-black.png` / `concepts/premiere-red/img/gg-icon-black.png` — original black, kept for any future light-background use.

Don't recreate the mark as CSS text/shape (e.g. a colored box with "GG" letters) — always reference these image assets so it stays the real logo geometry.

## Deployment note — why the icon is duplicated in two folders

**www.gattilloglobal.com (production) is a Vercel deployment whose project root is `concepts/premiere-red/`, not the repo root.** GitHub Pages (`vince-yul.github.io/gattillo-global-website/`) serves the whole repo, so a path like `../../assets/gg-icon-bone.png` from `concepts/premiere-red/index.html` works there — but on the production Vercel deployment that same file is served at the domain root, so `../../assets/...` 404s (nothing exists above the served root). Learned this the hard way: the icon looked fine on GitHub Pages and locally but was broken on the real production domain.

Fix: any asset used by `concepts/premiere-red/*.html` must live inside `concepts/premiere-red/` itself (e.g. `concepts/premiere-red/img/...`) and be referenced with a path relative to that folder, never reaching up past it with `../`. The root `Website/index.html` (internal concept-picker, GitHub Pages only, not on the custom domain) is the one page that can still use `assets/...` at the repo root.

## Current implementation

- `concepts/premiere-red/index.html`, `contact.html`, `partners.html` — header/footer use `<img class="gg-mark" src="img/gg-icon-bone.png">` (path relative to `concepts/premiere-red/`) beside the `GATTILLO GLOBAL.` wordmark; footer pairs it with the `.f-tagline` "We power entertainment." line below; mobile menu (`index.html`) shows a small GG mark next to the "Entertainment & Amusement" footer line.
- Root `index.html` (concept-picker, GitHub Pages only) uses `<img class="gg-mark" src="assets/gg-icon-bone.png">`.
- Favicon (data-URI SVG in `<head>`) is a single bold "G" glyph on the dark stage color — a separate, deliberately simplified mark (the overlapping-G icon is too fine-detailed to read at 16–32px); left as-is.
- Homepage hero ("We power / entertainment.") already carries the tagline prominently and nowhere else does the full stacked lockup appear.
- The pitch deck (`gattillo-china-innovation-deck.html`) uses the full master logo image once on its closing slide — normal for a single-viewing deck, not subject to the "don't repeat on every page" rule above.
