# Web Design Audit, Gattillo Global v4 (2026-07-19)

Scope: index.html + contact.html at 127.0.0.1:8641, captured at 1440px and 390px. Deep pass against the master web design brief, findings fixed in place.

## Headline
The v2 gold build had solid token discipline (9 colors, 2 families, 2 radii) but failed on hierarchy rules, contrast, and a real layout bug. All findings below were fixed and re-verified in the browser.

## Hard rule violations found and fixed
1. Layout bug: inside the hero flex column, .wrap's auto margins made it shrink-wrap to 859px and float centered. The whole hero read squished. Fixed with #hero .wrap width 100 percent, verified wrap now 1240px at x=100.
2. Primary buttons used the accent color as fill (brief: primary is near-white on dark, brand color is for accents only). Buttons are now bone with red hover fill; red stays in kickers, rules, numerals, chips, focus rings.
3. Body text under 16px in gates, rows, and ledger entries. All body copy now floors at 16px.
4. Meta text at 0.34 alpha bone failed contrast (about 2.7:1). Added a bone-meta token at 0.55 alpha (about 5:1) for all small labels; 0.34 kept only for decorative aria-hidden numerals.
5. Red accent #E0402A was about 4.1:1 for small red text on stage. Brightened to #E8492F (about 5:1).
6. No focus-visible styles, no skip link. Both added on both pages.
7. Contact form was two-column (brief: single column, no exceptions). Now single column.
8. Missing text-wrap balance on headings and pretty on paragraphs. Added.

## Direction changes from Max's review
- Accent: marquee gold replaced with premiere red. Gold read finance; red reads red carpet and marquee neon.
- Positioning: copy reframed from "we make products" to partnerships. Section order now hero, Partners (Names you already know), The Standard (what every partnership must be), How We Work (three gates), Vision, Contact.
- Hero: sentence case, no hollow stroke, full height with large internal gaps; category strip below the CTA removed (it duplicated the Partners section and crowded the button).
- Section rhythm: generous padding (110 to 176px) with moderate type. Air comes from spacing, not billboard type.

## Signals after fixes
Colors 9, families 2, radii 2 (pill + circle), root tokens 12, no horizontal overflow at 390px, no console errors, reduced motion respected, fonts self-hosted with swap.

## Remaining gaps for a future pass
- Type-only site; real floor photography or licensed-IP art would lift it a tier.
- Nav has no active-section state on scroll.
- FORM_ENDPOINT still empty; form falls back to mailto.

## v5: imagery pass (codex / ChatGPT images)
Two images generated with the codex CLI image tool, art-directed to the site palette (near-black, bone, #E8492F red), cinematic 35mm style, film grain, strictly no readable text, no logos, no recognizable characters, no people.
- assets/floor-wide.jpg (1536x1024, 277KB): full-bleed "floor after dark" band between the ticker and Partners, caption set below the image, never on it.
- assets/deck-detail.jpg (1024x1536, 211KB): red joystick and glowing buttons with marquee bulbs, placed in the Partners sticky column.
PNG sources in assets/src/. Both img tags carry width/height and lazy loading. Verified loaded and rendered at 1440px.
