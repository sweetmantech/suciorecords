# Sucio Records design reference

One visual language for everything Sucio Records puts in front of people: the website, one-sheets, proposals, flyers and social posts. Before making anything new, read this file and link `assets/brand.css`. Don't copy values into a page.

## The world

**Organic creativity amid the concrete.** Cali, the street, a sewer grate with plants pushing through it. Lofi and abstract hip-hop made in little rooms. Every piece should feel like this:

- **Street and plants.** The concrete is dark drain blue. Life is moss, leaf and fern. The grate with plants growing through it (`assets/drain-band.svg`) is the signature image.
- **Paper and ink.** Warm paper backgrounds with a light grain, black ink type and outlines. Printed, not glossy.
- **Real people and real places.** Use photos from the label's Instagram and releases, never stock. Captions say who and where.
- **Loud titles, quiet details.** Big condensed uppercase titles. Small mono labels for facts like dates, catalog numbers and prices.

## Tokens (`assets/brand.css`)

| Token | Value | Use |
|---|---|---|
| `--paper` | `#e7e2d6` | Default background |
| `--paper-2` | `#dcd6c7` | Cards on paper, number boxes |
| `--ink` | `#161614` | Text, outlines, dark cards, footer |
| `--ink-soft` | `#4a4842` | Secondary text on paper |
| `--drain-deep` | `#0f2a3a` | Street and night sections (agenda, print headers) |
| `--drain` | `#1d4660` | Manifesto, grate, secondary dark |
| `--drain-wet` | `#2c6283` | Puddle shine, quiet details on dark |
| `--moss-deep` | `#3f5a2c` | Artist section, kicker text on paper |
| `--moss` | `#6f8f4e` | Button hover shadow, track numbers |
| `--leaf` | `#8fb26a` | Headings on dark, "on" status, highlight chips |
| `--sun` | `#f2c230` | Dates, kickers on dark, main CTA, badges. One sun element per view. |
| `--petal` | `#f0b6c4` | Rare flags ("page coming soon") |
| `--nequi` / `--whatsapp` | `#e5007d` / `#1f7a4d` | Payment and chat buttons only |
| `--muted-on-dark` | `#a9a597` | Labels and fine print on ink |
| `--radius` | `6px` | Cards, buttons, photos. Pills use `999px`. |

There's no light/dark switch. Pages alternate paper sections with drain and moss sections.

## Type

| Role | Font | Rules |
|---|---|---|
| Display | **Anton** (`--display`) | Uppercase, line-height .95. Titles, artist names, big numbers. Never body text. |
| Labels | **Space Mono** (`--mono`) | Uppercase, letter-spacing .06 to .14em, 11 to 14px. Kickers, dates, prices, chips, buttons, captions. |
| Body | **Work Sans** (`--body`) | 15 to 17px, line-height 1.55. Sentence case. |

Kickers (`.kicker`) sit above titles: `● PRÓXIMO EVENTO · CALI`. Separate items with ` · `.

## Components

- **Buttons (`.btn`).** Mono uppercase on solid ink. On hover the button lifts and leaves a moss offset shadow. Variants: `.ghost`, `.nequi`, `.wa`, plus a sun-filled main CTA (one per view).
- **Chips (`.chip`, `.chip.g`).** Pill labels for formats, track counts and genre.
- **Outlined cards.** `box-shadow: 0 0 0 1.5px var(--ink)` on paper or `--paper-2`. Use outlines, not soft shadows.
- **Offset print shadow.** Hero pieces like the flyer or a printed cover take a hard colored offset (`10px 10px 0 var(--drain)`), sometimes with a slight 1 or 2° rotation, like a poster stuck on a wall.
- **Drain band.** `assets/drain-band.svg` is the divider between paper and street. Place it where a page moves from paper into a drain-deep section.
- **Placeholders (`.ph`).** A red dashed outline marks any data not yet confirmed. Remove it once the data is confirmed. Never ship a page with `.ph` on it.

## Voice

- The site is in Spanish, in Cali's voice. Proposals for international patrons can be in English and keep Spanish names (*Bagazo*, *alcantarilla*).
- Use specific facts over adjectives: catalog numbers, dates, track counts, places, names. Link every release and artist.
- Don't use em dashes, hype words or claims you can't link to a source.

## Print pieces

Print pieces live in `print/`, link `../assets/brand.css`, and are rendered with Chrome headless (`--print-to-pdf --no-pdf-header-footer`) at A4, one page.

- Follow the site's order: a paper hero (logo, kicker, title, real photos), the drain band, then the drain-deep street for the work and the people, then back to paper for the ask. An ink footer closes the page.
- Pin each page section with `flex:none` so a full A4 page clips at the bottom instead of squashing the drain band.
- Use at least three real photos.
- Put the ask after the world: show the work and the people before any number.
- Close with an invitation and a next step, then contact details and the portfolio QR code (`assets/qr-portfolio.png` on a paper tile).
- Keep fine print in mono at 9 or 10px.

## Assets

The ink logo is `assets/logo-ink.png`. On dark backgrounds use `filter: invert(1)`. Release, artist and event photos live in `assets/`. Their sources are the label's and artists' Instagram accounts and Bandcamp. Check credits before reusing a photo outside the site.
