# Gattillo Global — Logo & Brand Mark Usage

Rule set for when to use the full logo lockup, the wordmark, the tagline, and the GG symbol across the website (and other Gattillo Global collateral). Adopted 2026-08-19, revised 2026-08-19 after a detailed section-by-section review.

## The three levels

1. **GG** — the icon/symbol. Secondary brand device.
2. **GATTILLO GLOBAL.** — the corporate brand (wordmark).
3. **"WE POWER ENTERTAINMENT."** — the positioning statement / brand promise.

Don't default to stacking all three on every page — that reads as a sales brochure, not a contemporary global brand. The **full lockup** (all three together, as the one master-logo graphic) is reserved for exactly two places: the **homepage hero** and the **footer**. Everywhere else uses GG + wordmark only, with no tagline.

## Where each element goes

- **Header, every page**: GG symbol + GATTILLO GLOBAL, compact. The consistent corporate identifier. No tagline, no full logo.
- **Homepage hero**: the full lockup image (GG + wordmark + tagline, as one graphic), large. Below it, a headline that says what the company *does* — not a restatement of the tagline, since the logo already said that. Supporting copy underneath explains the specifics.
- **Footer, every page**: the full lockup image — the one other place it belongs, bookending the experience with the hero.
- **GG symbol alone**: a sparse decorative device — mobile navigation, a small accent next to a section kicker, or an oversized/very-low-opacity watermark behind a section's negative space. 2-3 such appearances on a long page, not more. Treat it as a signature, not decoration.
- **Content sections** (The Standard, How We Work, Vision, Tony's bio, Our Partners page content): no full logo, no standalone tagline text. GG-as-watermark is fine in a couple of sections with room to breathe (Vision, the closing CTA); Tony's section and the partner logos on the Our Partners page should have no additional branding competing with them.

## The GG mark itself

The GG symbol is the actual overlapping-G monogram from the master logo (`Business-Docs/LOGOs/GattilloGlobal_logo_transparency.png`) — not a placeholder or a stylized initial. It was cropped from the real transparent source (`Business-Docs/LOGOs/email-signatures/gattillo-logo-black-transparent-full.png`, the one file in the logo folder with genuine alpha transparency) at the natural gap between the icon and the "GATTILLO" wordmark, then recolored per background:

- `concepts/premiere-red/img/gg-icon-bone.png` (+ a copy at repo-root `assets/`) — bone/cream (`#EDE6D8`), for the site's dark backgrounds. Used in headers, the mobile menu, and as the small/oversized decorative device.
- `concepts/premiere-red/img/gg-icon-black.png` (+ a copy at repo-root `assets/`) — original black, kept spare for any future light-background use.

Don't recreate the mark as CSS text/shape (e.g. a colored box with "GG" letters) — always reference these image assets so it stays the real logo geometry.

## The full lockup asset

`concepts/premiere-red/img/gattillo-full-lockup-bone.png` — the whole master logo (GG + wordmark + tagline), cropped to its content bounding box from the same transparent source as the GG icon. Icon and wordmark pixels are recolored to bone `#EDE6D8`; the tagline and its underline swoosh keep the master logo's red, snapped to the site's `--red: #E8492F` for consistency. This is the only asset used for the hero and footer — don't substitute a live-text recreation of the tagline next to it (that was an earlier, since-reverted approach: a `.f-tagline` text element styled red/bold/underline was tried first and replaced by the real lockup image once it became clear the review wanted the actual graphic, not an approximation).

## Deployment note — why assets live inside `concepts/premiere-red/`

**www.gattilloglobal.com (production) is a Vercel deployment whose project root is `concepts/premiere-red/`, not the repo root.** GitHub Pages (`vince-yul.github.io/gattillo-global-website/`) serves the whole repo, so a path like `../../assets/gg-icon-bone.png` from `concepts/premiere-red/index.html` works there — but on the production Vercel deployment that same file is served at the domain root, so `../../assets/...` 404s (nothing exists above the served root). Learned this the hard way once already.

Fix: any asset used by `concepts/premiere-red/*.html` must live inside `concepts/premiere-red/` itself (e.g. `concepts/premiere-red/img/...`) and be referenced with a path relative to that folder, never reaching up past it with `../`. The root `Website/index.html` (internal concept-picker, GitHub Pages only, not on the custom domain) is the one page that can still use `assets/...` at the repo root.

## Current implementation

- **Hero** (`index.html`): `.hero-logo` — the full lockup image, above a new headline ("Connecting world-class IP with the people who bring entertainment to life.") that replaced the old "We power entertainment." h1, since the logo now says that.
- **Header**, all three pages: GG icon `<img>` + live "GATTILLO GLOBAL." text, no tagline.
- **Footer**, all three pages: `.f-logo` — the full lockup image, replacing the earlier GG+wordmark+separate-tagline-text combo.
- **GG watermark**: a large, ~5% opacity GG icon behind the Vision section's statement and behind the closing "Let's talk." CTA — both sections already have generous negative space, so it sits without redesigning them. A small (~15px) GG icon also sits inline next to the "How We Work" kicker.
- **The Standard**: numerals read `01/02/03` (previously plain `1/2/3`) — the existing large-faint-turns-red-on-hover treatment already was the "recognizable numbered device with restrained red" the review asked for; only the zero-padding changed.
- **How We Work**: the existing gate-line + red-lit progression dots already serves as the section's visual-progression device; only the small GG accent (above) was added.
- **Tony's section**: role label reads "The Founder Behind The Network" (was "Founder & CEO") — reframes him as the founder of something bigger than himself, without touching his factual bio or photo. No logo next to his photo.
- **Our Partners page**: unchanged — GG + wordmark in the nav, no full logo in the content, the BoldMove Nation / Imply logos remain the visual heroes.
- **Nav label fix**: the "Who We Work With" nav link's raw HTML fallback text had drifted from its own i18n dictionary value (dict already said "Who We Work With"; the hardcoded fallback still said "Partners" in `index.html` and `partners.html`) — this was the real source of the "Partners vs. Our Partners" ambiguity a crawler or no-JS view would see. Fixed so source and rendered output agree.
- Favicon (data-URI SVG in `<head>`) stays a single bold "G" glyph — deliberately simplified since the overlapping-G icon is too fine-detailed to read at 16–32px.
- The pitch deck (`gattillo-china-innovation-deck.html`) uses the full master logo once on its closing slide — normal for a single-viewing deck, not subject to the hero/footer-only rule above.

## Not done yet — needs client input

Showing actual partner/client/IP-holder logos on the homepage's "Who We Work With" section (currently text-only: "Names you already know," Studios & Rights Holders, Parks & FECs, etc.) — needs client-supplied logo assets and clearance to display them, which isn't in hand. Flagged for a future pass once that's available.
