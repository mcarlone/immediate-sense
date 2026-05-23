# Immediate Sense — Design Spec

## Typography

Two typefaces, both from Google Fonts:

- **Wordmark:** Titan One, 400. Title case. Used only for the "Immediate Sense" wordmark.
- **Supporting type:** Inter, 300 (400 for headings). Everything else.

Import (one line gets both):
`https://fonts.googleapis.com/css2?family=Titan+One&family=Inter:wght@300;400&display=swap`

| Role | Font | Weight | Notes |
|---|---|---|---|
| Hero wordmark | Titan One | 400 | Large display, two-color (see below) |
| Nav wordmark | Titan One | 400 | Small, two-color (see below) |
| Footer wordmark | Titan One | 400 | White on green, single color |
| Work item title | Inter | 400 | 2rem |
| Body / descriptions | Inter | 300 | Always light weight for prose |
| Section labels | Inter | 400 | Spaced caps, uppercase |
| Metadata | Inter | 300 | Spaced caps, uppercase |

### Wordmark color

The wordmark is two-color on light backgrounds:
- "Immediate" — `#111111`
- "Sense" — `#3d7a28` (`--wordmark-leaf`)

On the green footer the wordmark stays single-color white (`#faf7f2`).

---

## Color Palette

```css
--paper:  #faf7f2;   /* warm off-white background — do not use pure white */
--ink:    #18160f;   /* near-black with warm undertone — do not use #000 */
--mid:    #7a7268;   /* body text, descriptions */
--light:  #b8b0a4;   /* metadata, secondary labels */
--rule:   #e2ddd6;   /* dividers, borders */
--leaf:   #5c9e42;   /* green accent — structural use only, see rules below */
```

---

## Green Usage Rules

There are two greens, split by job:

- **`--leaf` (`#5c9e42`)** — green as a *fill or border*. Bright; reads well as a solid shape.
- **`--wordmark-leaf` (`#3d7a28`)** — green as *text*. Darker so it stays legible on the warm paper background.

Approved fill/border uses (`--leaf`):
- Top bar: 5px full-width bar at the very top of the page
- Footer background: full green footer with white text
- Hero left border (6px)
- Nav-link hover underline (2px border)

Approved text uses (`--wordmark-leaf`):
- Wordmark "Sense"
- Work-item title link on hover

Do not use green on:
- Body prose or descriptions
- Dividers/rules in the content area
- Backgrounds of sections or cards

---

## Layout

- Max content width: `640–900px` depending on section
- Base padding: `4rem` horizontal on all sections
- Hero padding: `8rem 4rem 7rem`
- Section padding: `6rem 4rem`
- Nav padding: `2.2rem 4rem`

---

## Components

### Top Bar
```html
<div class="top-bar"></div>
```
```css
.top-bar { height: 5px; background: var(--leaf); }
```

### Nav
- Wordmark left, links right
- Links: 300 weight, spaced caps, color `--mid`
- Hover: color shifts to `--ink`, 2px bottom border in `--leaf`

### Hero
- Wordmark breaks across two lines: `Immediate<br>Sense`
- Body copy: 300 weight, `--mid`, max-width 520px

### Section Labels
- Small spaced caps in `--light`
- No decorative elements (no ticks, no rules)

### Work Items
- Two-column grid: title/meta left, description right
- Title: Inter 400, 2rem
- Meta: Inter 300, spaced caps, `--light`
- "Available" status: `--light`, Inter 400 (same color as meta)

### Footer
- Background: `--leaf`
- Wordmark: Titan One, white (`#faf7f2`), single color
- Copyright: Inter, white at 50% opacity, 300 weight

---

## Tone Notes (for copy)

- Voice: dry, direct, no flourish
- Placeholder copy register: "We build software that earns its place — tools that solve hard problems without making a scene about it."
- Avoid: superlatives, mission-statement language, anything that sounds like a pitch deck
- The site signals credibility through restraint, not assertion

---

## What's Unresolved

- Tagline: "Sharp instincts, honestly doubted." is a candidate but not confirmed
- Copy throughout is placeholder — tone is right, specifics need real content
- No logo mark yet, wordmark only
