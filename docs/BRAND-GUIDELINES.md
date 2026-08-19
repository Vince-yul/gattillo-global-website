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

## Current implementation

- `concepts/premiere-red/index.html`, `contact.html`, `partners.html` — header uses a compact `.gg-mark` (red rounded-square "GG") beside the `GATTILLO GLOBAL.` wordmark; footer uses `.f-brand` (GG + wordmark stacked with the `.f-tagline` "We power entertainment." line below); mobile menu (`index.html`) shows a small GG mark next to the "Entertainment & Amusement" footer line.
- Favicon (data-URI SVG in `<head>`) is a single bold "G" glyph on the dark stage color — the existing simplified brand mark; left as-is.
- Homepage hero ("We power / entertainment.") already carries the tagline prominently and nowhere else does the full stacked lockup appear.
