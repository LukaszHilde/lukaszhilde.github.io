# HMDesign — binding rules

Visual system of Hildebrandt Management. Applies to web pages, A4 documents,
16:9 presentations and PDF material. Values are fixed and carried from tokens —
they are not the implementer's taste.

---

## 1. Hard rules

1. Colours **only** via `var(--hm-…)`. No new hex outside the token block.
2. Typeface is **Lato**, self-hosted. **Zero network requests** — no Google Fonts,
   no CDN, no external scripts or analytics. This is a privacy requirement.
3. `border-radius: 0`. Sharp corners, no exceptions.
4. Cards: `1px var(--hm-hairline)` border, **no shadow**. Shadow exists only under an
   A4 sheet or a slide in screen view.
5. **No emoji.** Allowed glyphs: `→` `✕` `✉`. List bullets are `→`, negation `✕`.
6. Headings Lato 900, sentence case. UPPERCASE only in eyebrows and labels
   (tracking .16–.18em, in the accent colour).
7. Green `--hm-green*` only for the sustainability thread. Max ~3 colours per composition.
8. No gradients, textures or decorative photography. No animation beyond link `:hover`.
9. The mark is **never drawn from memory** — it is typographic: orange square + Lato 900.
10. Any value outside the tokens needs a human decision. The tool **asks**, it does not choose.

---

## 2. Palette

| Token | Hex | Use |
|---|---|---|
| `--hm-orange` | `#eb5c25` | primary accent |
| `--hm-orange-deep` | `#c9481a` | hover / press |
| `--hm-black` | `#232120` | ink, logotype, strong sections |
| `--hm-white` | `#ffffff` | base surface |
| `--hm-grey-700` | `#48494b` | lead text, lists |
| `--hm-grey-600` | `#6a6b6d` | card copy |
| `--hm-grey-500` | `#919295` | footers, captions |
| `--hm-grey-400` | `#b4b5b7` | numbers, separators |
| `--hm-grey-300` | `#d1d3d3` | masthead rule, light text on black |
| `--hm-grey-200` | `#e4e5e5` | hairlines, card borders |
| `--hm-grey-100` | `#f6f7f7` | grey section background, table headers |
| `--hm-peach` | `#fdefe9` | **only** the light callout background |
| `--hm-green-deep` | `#034745` | sustainability only |
| `--hm-green` | `#12a537` | sustainability only |

Document accent is swapped in one line: `:root{ --hm-accent: … }`.
Allowed: orange, black, deep green. Nothing else. No warm beiges, no cool blue-greys.

---

## 3. Typography

Family: `--hm-font: 'Lato', Arial, Helvetica, sans-serif`.
Weights: 300 rarely · 400 body · 700 emphasis · 800 labels and card titles · 900 headings.

| Element | Value |
|---|---|
| Hero H1 | `clamp(38px, 6vw, 76px)`, weight 900, tracking `-.025em`, leading 1.04 |
| Section H2 | `36px`, tracking `-.01em`, leading 1.08 |
| Lead | `19px`, leading 1.5, `--hm-grey-700`, `max-width: 64ch` |
| Hero sub | `20px`, leading 1.5, `--hm-grey-300`, `max-width: 60ch` |
| Body | `16px`, leading 1.55, `--hm-grey-700`, `max-width: 66ch` |
| Eyebrow | `13px`, weight 800, tracking `.18em`, uppercase, accent |
| Card title | `18px`, weight 800 |
| Card text | `14.5px`, leading 1.5, `--hm-grey-600` |

Body never below 16 px. `text-wrap: balance` on headings, `pretty` on paragraphs.

---

## 4. Layout

- Column: `.wrap{max-width:1120px;margin:0 auto;padding:0 40px}`, `0 24px` on mobile.
- Section: `.section{padding:88px 0}`, `64px 0` on mobile.
- Section backgrounds: white, `--hm-grey-100`, `--hm-black`. Nothing else.
- Page rhythm: black hero → intro strip → alternating white / grey sections →
  one dark section → contact on black → footer on black.
- Grids: 3 cards on desktop, single column below 900 px. Table-like grids use
  `gap:1px` over a `--hm-hairline` background — lines instead of gutters.
- Accent bar 6 px at the top of the page; 2.5 mm in A4, 10 px in a deck.
- 62° diagonal in the hero's top-right corner: accent 12 px + white 18% 5 px.
- A4 `210×297 mm`, column margins 10 / 13 / 11 mm. Deck `1920×1080 px`, text never below 24 px.

---

## 5. Blocks

Class names come from the live site — keep them, do not invent new ones:
`.topbar` `.siteheader` `.nav` `.wordmark` `.eyebrow` `.hero` `.intro`
`.section--grey` `.section--dark` `.shead` `.grid` `.card` `.offer` `.ocard`
`.princ` `.pcell` `.callout` `.about` `.tag` `.contact` `.cbox` `.crow`
`.btn--primary` `.btn--ghost` `.btn--ghost-dark` `.footer`.

Full sheet: `referencja/hmdesign-web.css`. A new page is a new set of content in the
existing blocks, **not** a new stylesheet.

---

## 6. States and motion

Link `:hover` → accent, `color .15s ease`. Press → `--hm-orange-deep`.
`:focus-visible` → visible accent outline; keyboard operation is required.
Text selection: orange background, white text. No entrance animation, no parallax.

---

## 7. Voice

Short declarative sentences. The system is described impersonally
("AI prepares", "the human decides"). We do not promise — we describe what the system
does and **what it does not do**. Honesty about limits is part of the voice.
Concrete numbers instead of round claims. Sentence case in headings, never caps.
Inline separator: middle dot `·`. The client is a partner, not a "lead".

Copy is governed by the approved HM state in Notion ("HM — SYSTEM"). The client is
addressed directly ("you"), the author speaks in first person ("I prepare"). Legacy
product names ("TES+", "site-event workflow", "management view") are retired.
English follows the Polish structure and restraint; it is not a looser register.

---

## 8. Pitfall

A light card inside `.section--dark` inherits `color:#fff` from the section.
Every white surface inside a dark section must explicitly return to `var(--hm-black)`.

## 9. Acceptance criteria

- [ ] Sharp corners everywhere, no element carries a shadow.
- [ ] Zero network requests — verified in the Network tab.
- [ ] Every colour comes from `var(--hm-…)`.
- [ ] Sentence-case headings, uppercase tracked eyebrows.
- [ ] Bullets are `→`, no emoji.
- [ ] Text contrast ≥ 4.5:1.
- [ ] Readable at 360 px and when printed to PDF.
- [ ] Footer carries full contact: tel. 889 447 117, Gdańsk / Tricity.
- [ ] PL and EN versions structurally in sync.
