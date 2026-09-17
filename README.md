# Reggae Pot Jamaican Grill — homepage redesign, two concepts

Two order-first homepage concepts for **Reggae Pot Jamaican Grill**, Centennial and Denver,
Colorado. Same job in both: make ordering online the obvious next step, ahead of phoning.

Open either file directly in a browser, or serve the folder:

```bash
python -m http.server 8080
```

## The two concepts

| File | Direction |
|---|---|
| `mockup-soulkitchen.html` | Light editorial. Cream ground, one dramatic plate at a time, a bento food wall, oversized display type. |
| `mockup-dancehall.html` | 1970s Jamaican dancehall poster. Black as structure, alternating saturated green, yellow and red slabs, hand-painted signboard plates, a running ticker. |

Both carry the same working parts:

- **Live tray builder.** 67 dishes with the real prices from the client's ordering storefront,
  a Centennial and Denver switch that changes the prices and the checkout destination, a
  running total kept in `localStorage`, and an open or closed pill computed from the published
  hours in `America/Denver`.
- **Real facts only.** Both addresses, both phone numbers and the opening hours come from the
  client's own locations page. Every price comes from the live storefront.
- **Four JSON-LD blocks**, one per type: two `Restaurant`, one `WebSite`, one `FAQPage`.
- **A printable menu**, `assets/reggae-pot-menu.pdf`, one Letter page with every item.

## Checked before publishing

Each concept was measured, not eyeballed, at 1920, 1440, 900 and 500px:

- zero contrast failures, including text measured on the real composited pixels over video
  and over photographs
- no horizontal overflow, one `h1`, no skipped heading levels, alt text on every image
- every scroll reveal lands; nothing is hidden without JavaScript running to restore it
- motion respects `prefers-reduced-motion`
- every asset returns HTTP 200

`_design-scan.md` records the three live reference sites the dancehall concept was reasoned
from, the divergence check against concept 1, and the build lessons carried in.

## Known gaps

- **No social proof.** No rating and no review anywhere, because none has been supplied. This
  is the largest remaining conversion gap.
- **One photo shoot.** Fifteen distinct photographs exist and all of them come from a single
  afternoon, so the lighting and the blue plates repeat. There are 90+ dishes on the menu.
- **Unconfirmed with the client:** delivery, reservations, whether prices may be published,
  and a typo on the client's own locations page that gives Centennial's Sunday hours as
  `11pm - 7pm`.

Built for Magister Digital. Not deployed; these are review builds.
