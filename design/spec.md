# Immediate Sense — Design Spec

## Typography

**Font:** Source Serif 4 (Google Fonts)
- Import: `https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,wght@0,300;0,400;0,700;1,300&display=swap`
- This is the only font used across the entire site. No sans-serif fallbacks in the UI.

| Role | Weight | Notes |
|---|---|---|
| Hero wordmark | 700 | Large display, tight tracking (-0.03em) |
| Nav wordmark | 700 | Small, minimal tracking |
| Body / descriptions | 300 | Always light weight for prose |
| Section labels | 400 | Spaced caps, uppercase |
| Metadata | 300 | Spaced caps, uppercase |

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

Green (`--leaf`) is **structural only**. It never appears on text.

Approved uses:
- Top bar: 5px full-width bar at the very top of the page
- Footer background: full green footer with white text

Do not use green on:
- Any text element
- Borders, rules, or dividers within the content area
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
- Title: 700 weight, 2rem
- Meta: 300 weight, spaced caps, `--light`
- "Available" status: `--leaf`, 600 weight

### Footer
- Background: `--leaf`
- Wordmark: white (`#faf7f2`), 700 weight
- Copyright: white at 50% opacity, 300 weight

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
