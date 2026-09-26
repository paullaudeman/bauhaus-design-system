# Bauhaus

The design system behind [laudeman.io](https://laudeman.io). The palette is ink, paper and rust.

A poster rather than an engineering drawing: a heavy stacked name, a rust square and a black circle
as composition, oversized numerals, hard black rules, solid offset shadows and a lightly dusted paper
ground. It is an alternate to [Blueprint](https://github.com/paullaudeman/blueprint-design-system):
same content, two readings. That one is a drawing, this one is a poster.

### → [See the system](https://paullaudeman.github.io/bauhaus-design-system/)

That page is built from this repo's own `tokens.css`. The dust under it is the real
`--paper-grain`, the shadows are the real `--shadow-*`, and if you tab through it the focus rings are
the real `--ink`. It is the system demonstrating itself, not a picture of it. EN/DE.

```css
/* Palette - ink, paper, rust */
--ink:         #141414;   /* type, rules, the circle          15.91:1 */
--paper:       #f2eee5;   /* ground - warm, not white */
--rust:        #b5462f;   /* the one accent                    4.67:1 */
--rust-on-ink: #e07a5f;   /* rust on an inverted block         6.24:1 */
--slate:       #4a4640;   /* secondary, metadata                8.09:1 */

/* Hard shadows - a second printed block, never blurred */
--shadow-sm:   3px 3px 0 var(--ink);
--shadow:      5px 5px 0 var(--ink);
--shadow-rust: 9px 9px 0 var(--rust);
```

Contrast ratios are WCAG, against `--paper` (`--rust-on-ink` against `--ink`). Full token set:
[`tokens.css`](tokens.css).

---

## The idea

**Form follows function, built from primary parts.** The Bauhaus (Weimar 1919, Dessau 1925, briefly
Berlin until 1933) stripped design down to geometric shapes, a few strong colours, and type used as
structure rather than decoration. This system takes that vocabulary and mixes in the Swiss and
constructivist poster traditions that grew out of it.

**Bauhaus-inspired, not textbook Bauhaus.** The departures are listed, not hidden.

| Principle | Where it shows up |
|-----------|-------------------|
| Primary geometry | Portrait circle, rust square, black circle |
| Few colours, used as signals | Ink and one rust accent on paper |
| Geometric sans | Futura in print, Jost on screen |
| Asymmetric, grid-built layout | Heavy name left, geometry right; a numeral rail beside every section |
| Type as structure | Stacked name, oversized numerals, 3px rules |
| Function over ornament | The numbers strip carries information, not decoration |

## The choices

- **Square and circle.** Kandinsky's 1923 Bauhaus questionnaire paired the square with red, the
  circle with blue, the triangle with yellow. The rust square follows him. The circle is black on
  purpose: blue is out of this palette.
- **Rust, not Bauhaus red.** Rust reads like oxidised Bauhaus red: the same signal, turned down to an
  earth tone.
- **Warm paper, lightly dusted.** It reads as print and glares less. The dust is procedural SVG:
  a faint mottle plus sparse dark specks from thresholded noise. Not an image, no licence.
- **Futura, and Jost.** Futura (Paul Renner, 1927) is the geometric sans of the era. Renner was never
  at the Bauhaus, but it is the face everyone associates with it. Jost is its open-source web cousin.
- **Heavy and tight, light and open.** Display type at 900, tracked tight. Small uppercase labels at
  700, tracked open.
- **Grayscale portrait.** So the accent stays the only colour on the page.
- **The numbers strip.** The data is the design. A figure appears only if the page's own text states it.
- **No underlined links.** The bold name is the link.

## Where it departs

| Departure | Why |
|-----------|-----|
| Rust instead of primary red | No bright colours, anywhere |
| Warm paper instead of white | Print feel, less glare |
| Uppercase display name | The least Bauhaus choice. Herbert Bayer pushed for all lowercase; uppercase is Swiss and constructivist poster hierarchy. |
| Hard offset shadows | Not Bauhaus at all: a neo-brutalist web move. Kept because a solid offset block reads as a second pass through the press, not as soft depth. |
| Black circle instead of blue | Blue is not in the palette |
| No square without a portrait | On a document with no photo the square has no job, so it goes |

## Rules

- **One accent.** Rust, and nothing else.
- **Weight is hierarchy.** 3px for frames and breaks, 1.5px for chips and table rows, 6px rust beside
  one closing line.
- **Square corners.** `--radius: 0`. The circle is the only curve.
- **Hard shadows only.** Solid ink, offset, zero blur. No gradients.
- **Uppercase is for display and labels.** Never running text.
- **A number is earned.** The strip shows only figures the text states.

## Four things that will bite you

**`--rust` sits at 4.67:1 on `--paper`.** That clears WCAG AA for body text by a hair. Lighten it at
all and small rust text fails. Use it for numerals, shapes and bold display type.

**Focus is ink, not rust.** Rust is red-family, so a rust focus ring reads as an error state. Focus is
`--ink` at `--rule-heavy`.

**Hard shadows need room.** The offset sits outside the box. Inside an `overflow: auto` wrapper it is
clipped, and flush against a neighbour it collides. Leave the offset as margin.

**The grayscale filter.** Put the square and circle inside the filtered portrait, or draw the circle
as its `box-shadow`, and the filter drains the rust out of them too. Keep them as siblings of the
image.

---

## How this page is built

```html
<link rel="stylesheet" href="tokens.css">
```

The type is [Jost](https://github.com/indestructible-type/Jost), open source under the SIL Open Font
License, on screen and in print. Futura stays in the stack as the fallback it was drawn after.

## License

© 2026 Paul Laudeman. **All rights reserved** - see [LICENSE](LICENSE).

Published to be read, not reused. Read it, link to it, quote it with attribution. For anything
else - using the tokens, the rules or the compositions in your own work - get in touch via
[laudeman.io](https://laudeman.io).

Type is [Jost](https://github.com/indestructible-type/Jost), SIL Open Font License - licensed by its
author, not by this repo. Futura and Avenir Next are named in the font stacks only; they are
commercial typefaces and are not distributed here.

---

[Live reference](https://paullaudeman.github.io/bauhaus-design-system/) &middot; [laudeman.io](https://laudeman.io)

*Recorded September 2026.*
