# Design scan — Reggae Pot Jamaican Grill (concept 2, "Dancehall")

**Niche:** Jamaican / Caribbean restaurant, order-first
**Group:** Magister Clients
**Date:** 2026-09-17
**Build:** `redesign/mockup-dancehall.html` (source `redesign/_dh-template.html`)

Ron's brief: *"gawa pa tayo ng isa pa, same focus different design. yung reggae themed
talaga. dapat jamaican feels."* Same job as concept 1 — make ordering online the obvious
next step — in a completely different visual world.

## References (Step 0)

Palettes and typefaces below were **measured off the live pages** with `getComputedStyle`,
not read from a roundup.

1. **https://misslilys.com** — 1970s Jamaican dancehall-poster register.
   Measured: black `#000000`, yellow `#FDD309`, green `#0B7635` and `#0FA54A`, deep blue
   `#183F69`, cream `#EDE7D6`, brown `#672A17`. Cooper Black for display, Oswald 500 at 48px
   for section heads, Montserrat 300/400/700 for body. Page is built from `c-split` and
   `c-tout-overlay` repeated: saturated colour-blocked split panels alternating down the page,
   not a hero-then-cards stack.
   **Taken:** the alternating colour-block split rhythm, black used as a structural colour
   rather than a background, and a fat retro display face carrying the personality.

2. **https://chubbysjamaican.com** — MICHELIN-listed Toronto Jamaican kitchen.
   Measured: pale mint ground `#CFE8D2` dominant, crimson accent `#BC344A`, navy `#16436F`,
   ITC Cushing Std serif for body, PDU condensed for labels.
   **Taken:** a warm non-white ground rather than white, and the discipline of letting real
   candid photography carry the identity with no decorative overlays. Their mint is NOT taken;
   Reggae Pot's ground comes from its own logo.

3. **https://rodneysjerk.com** — Iowa City jerk and BBQ.
   Measured: fire red `#E11F28`, dark maroon `#490A07`, olive `#4F5D4A` and `#3E4B38`,
   off-white `#F5F2EF`. H1 "Savor Island Heat Here"; offers named plainly as section heads.
   **Taken:** heat-led headline language and a hot red reserved for the ordering action.

**Not taken from any of them:** their copy, their palettes as palettes, their facts, their
logos. Reggae Pot's colours come from `assets/logo/reggae-pot-logo-full.png` (see RP-L-008):
green `#00903C`, yellow `#FCF000`, flame red `#B43C3C`, black.

## Divergence check

`.claude/memory/design-registry.json` currently holds **0 entries**, so there is no recorded
sibling to diverge from. The real constraint is concept 1 in this same folder, which Ron has
already seen: `mockup-soulkitchen.html`. This build differs from it on **all six axes**.

| Axis | Concept 1 (SoulKitchen) | Concept 2 (Dancehall) |
|---|---|---|
| Palette | cream `#FBF7EE` ground, colour as accents | black ground, saturated green / yellow / red **colour blocks** |
| Fonts | Anton + Archivo + Caveat | Alfa Slab One + Karla + Barlow Condensed |
| Layout family | centred editorial column plus a bento wall | alternating full-bleed **split panels**, photo one side, flat colour the other |
| Motion register | clip-open, blur-to-sharp, slow settle | **poster snap** — short, no blur, each panel enters from its own side |
| Signature | green-yellow-red flag rule under each head | **hand-painted signboard plates** and ticket-stub edges |
| References used | SoulKitchen (ThemeForest) | Miss Lily's, Chubby's, Rodney's |

**Verdict:** PASS. Six of six axes differ from the only build Ron could compare it against.

## Lessons checked

Grepped `.claude/memory/lessons.md` before the first line of this build. Carried in:

- **L-103** — a container `a` colour rule swallows buttons. Every link colour rule in this
  build is scoped `:not(.btn)`.
- **L-112 / L-264** — reveal failsafe, and the failsafe must rescue only what is on screen or
  it defeats scroll-triggered motion.
- **L-145 / L-215** — no stranded last row. Split panels are pairs, so rows always complete.
- **L-152** — `overflow-x: clip`, never `hidden`.
- **L-154** — headless Chrome mis-sizes below ~600px; verify narrow widths at 500 and up.
- **L-182** — inventory sections after any structural edit.
- **L-238** — `1fr` is `minmax(auto,1fr)`; use `minmax(0,1fr)` on every grid track.
- **L-244** — `width`/`height` attributes beat CSS `aspect-ratio` without `height:auto`.
- **L-260** — never animate opacity from 0 with a fill mode; a hidden tab freezes the timeline.
- **L-261** — headless freezes transitions; measure with transitions disabled.
- **L-262** — contrast off a screenshot: worst case is the closest luminance, read the real
  render width, build the hide-list from the target list.
- **L-265** — always pair `background-color` with `background-image`.
- **RP-L-008** — the logo file is the palette; logo green fails white small text at 4.15:1.
- **RP-L-009** — the food clip is 1280x720; never stretch it full-bleed.
- **RP-L-010** — 15 distinct photographs exist and they all come from one afternoon.

## Anti-generic gates

Checked before build, re-checked after render. Above the fold names the business, the food,
both cities and the ordering action. One primary action per view: red is ordering and nothing
else uses it. Contrast measured on the composited pixels, not assumed. The logo ships as
supplied and is never recoloured. Local proof: both addresses, both phone numbers and real
opening hours. Not a template swap: concept 2 shares no layout, palette, typeface or motion
with concept 1.
