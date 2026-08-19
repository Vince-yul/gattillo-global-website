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

- `assets/gg-icon-bone.png` — bone/cream (`#EDE6D8`), for the site's dark backgrounds. This is the one actually used on every page.
- `assets/gg-icon-black.png` — original black, kept for any future light-background use.

Don't recreate the mark as CSS text/shape (e.g. a colored box with "GG" letters) — always reference these image assets so it stays the real logo geometry.

## Current implementation

- `concepts/premiere-red/index.html`, `contact.html`, `partners.html`, and root `index.html` — header/footer use `<img class="gg-mark" src=".../assets/gg-icon-bone.png">` beside the `GATTILLO GLOBAL.` wordmark; footer pairs it with the `.f-tagline` "We power entertainment." line below; mobile menu (`index.html`) shows a small GG mark next to the "Entertainment & Amusement" footer line.
- Favicon (data-URI SVG in `<head>`) is a single bold "G" glyph on the dark stage color — a separate, deliberately simplified mark (the overlapping-G icon is too fine-detailed to read at 16–32px); left as-is.
- Homepage hero ("We power / entertainment.") already carries the tagline prominently and nowhere else does the full stacked lockup appear.
- The pitch deck (`gattillo-china-innovation-deck.html`) uses the full master logo image once on its closing slide — normal for a single-viewing deck, not subject to the "don't repeat on every page" rule above.
