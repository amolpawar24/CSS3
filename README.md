# CSS3

A comprehensive CSS3 learning and reference repository — covering everything from absolute beginner fundamentals to modern, advanced CSS. Built as a personal documentation project and a practical reference for frontend development and interview preparation.

---

## Table of Contents

1. [CSS Fundamentals](#1-css-fundamentals)
2. [CSS Selectors](#2-css-selectors)
3. [CSS Colors](#3-css-colors)
4. [Backgrounds](#4-backgrounds)
5. [Gradients](#5-gradients)
6. [Typography](#6-typography)
7. [Box Model](#7-box-model)
8. [Border](#8-border)
9. [Outline](#9-outline)
10. [Display](#10-display)
11. [Positioning](#11-positioning)
12. [Overlay Techniques](#12-overlay-techniques)
13. [Overflow](#13-overflow)
14. [Visibility](#14-visibility)
15. [Flexbox](#15-flexbox)
16. [Alignment](#16-alignment)
17. [CSS Grid](#17-css-grid)
18. [Tables](#18-tables)
19. [Lists](#19-lists)
20. [Images](#20-images)
21. [Filters](#21-filters)
22. [Shadows](#22-shadows)
23. [Transitions](#23-transitions)
24. [2D Transforms](#24-2d-transforms)
25. [3D Transforms](#25-3d-transforms)
26. [Animations](#26-animations)
27. [Pseudo-Classes](#27-pseudo-classes)
28. [Pseudo-Elements](#28-pseudo-elements)
29. [CSS Variables](#29-css-variables)
30. [CSS Units](#30-css-units)
31. [CSS Functions](#31-css-functions)
32. [Media Queries](#32-media-queries)
33. [Container Queries](#33-container-queries)
34. [Logical Properties](#34-logical-properties)
35. [Aspect Ratio](#35-aspect-ratio)
36. [Cursor](#36-cursor)
37. [User Select](#37-user-select)
38. [Pointer Events](#38-pointer-events)
39. [Scrolling](#39-scrolling)
40. [Accessibility-Related CSS](#40-accessibility-related-css)
41. [CSS Media Features](#41-css-media-features)
42. [Cascade and Specificity](#42-cascade-and-specificity)
43. [Cascade Layers](#43-cascade-layers)
44. [CSS Nesting](#44-css-nesting)
45. [Modern CSS Features](#45-modern-css-features)
46. [CSS Reset and Normalization](#46-css-reset-and-normalization)
47. [CSS Architecture](#47-css-architecture)
48. [Responsive Design](#48-responsive-design)
49. [Common UI Components](#49-common-ui-components)
50. [CSS Effects](#50-css-effects)
51. [CSS Debugging](#51-css-debugging)
52. [CSS Best Practices](#52-css-best-practices)
53. [Property Reference](#53-property-reference)
54. [Flexbox vs Grid](#54-flexbox-vs-grid)
55. [Position vs Flexbox vs Grid](#55-position-vs-flexbox-vs-grid)
56. [Transform vs Transition vs Animation](#56-transform-vs-transition-vs-animation)
57. [Repository Structure](#57-repository-structure)
58. [Learning Progress](#58-learning-progress)
59. [How to Use the Repository](#59-how-to-use-the-repository)
60. [Learning Goals](#60-learning-goals)
61. [Author](#61-author)
62. [Future Improvements](#62-future-improvements)

---

## 1. CSS Fundamentals

**What is CSS?** CSS (Cascading Style Sheets) is the language used to describe the presentation of an HTML document — layout, colors, spacing, typography, and visual behavior.

**Why CSS is used:** it separates content (HTML) from presentation, enables consistent styling across pages, and makes interfaces responsive and maintainable.

**CSS Syntax** — a rule is made of a selector and a declaration block:

```css
selector {
  property: value; /* declaration */
}
```

- **Rule** — the selector + declaration block together
- **Property** — what aspect you're styling (`color`, `margin`, etc.)
- **Value** — the setting applied to that property
- **Declaration** — a single `property: value;` pair
- **Comment** — `/* like this */`, ignored by the browser

**Ways to apply CSS:**

| Method | Description |
|---|---|
| Inline CSS | `style` attribute directly on an element |
| Internal CSS | `<style>` block inside the HTML `<head>` |
| External CSS | Separate `.css` file linked via `<link>` |

**Cascade and inheritance:** the *cascade* determines which rule wins when multiple rules target the same element (based on source order, specificity, and importance). *Inheritance* means some properties (mostly text-related, like `color` and `font-family`) are automatically passed from parent to child elements unless overridden.

**Initial and default values:** every CSS property has a spec-defined *initial value* used when no value is set or inherited.

**Global keywords:**

| Keyword | Meaning |
|---|---|
| `inherit` | Use the parent element's computed value |
| `initial` | Reset to the property's spec-defined initial value |
| `unset` | Acts as `inherit` for inherited properties, `initial` otherwise |
| `revert` | Reset to the browser's default (user-agent) stylesheet value |
| `revert-layer` | Reset to the value from a previous cascade layer |

---

## 2. CSS Selectors

**Basic selectors**

| Selector | Example | Matches |
|---|---|---|
| Universal | `*` | Every element |
| Element | `p` | All `<p>` elements |
| Class | `.card` | Elements with `class="card"` |
| ID | `#header` | The element with `id="header"` |

**Grouping**

```css
h1, h2, h3 {
  font-family: sans-serif;
}
```

**Combinators**

| Combinator | Syntax | Meaning |
|---|---|---|
| Descendant | `A B` | B anywhere inside A |
| Child | `A > B` | B is a direct child of A |
| Adjacent sibling | `A + B` | B immediately follows A |
| General sibling | `A ~ B` | B follows A, same parent |

**Attribute selectors**

| Selector | Matches |
|---|---|
| `[attr]` | Has the attribute, any value |
| `[attr=value]` | Exact value match |
| `[attr~=value]` | Value in a space-separated list |
| `[attr\|=value]` | Value or value followed by `-` (e.g. language codes) |
| `[attr^=value]` | Value starts with |
| `[attr$=value]` | Value ends with |
| `[attr*=value]` | Value contains |

**Advanced selectors**

| Selector | Purpose |
|---|---|
| `:is()` | Matches any selector in a list, simplifies grouping |
| `:where()` | Same as `:is()` but with zero specificity |
| `:not()` | Excludes elements matching the argument |
| `:has()` | Matches an element if it contains a match for the argument (a "parent selector") |

```css
/* :has() example — style a card only if it contains an image */
.card:has(img) {
  border: 1px solid #ddd;
}
```

---

## 3. CSS Colors

**Named colors** — keywords like `red`, `blue`, `green`, `transparent`, and `currentColor` (which resolves to the element's computed `color` value).

**HEX**

| Format | Example | Notes |
|---|---|---|
| `#RGB` | `#f00` | Shorthand, no alpha |
| `#RGBA` | `#f00a` | Shorthand with alpha |
| `#RRGGBB` | `#ff0000` | Full form, no alpha |
| `#RRGGBBAA` | `#ff0000aa` | Full form with alpha |

**RGB**

```css
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5); /* rgb() also accepts alpha directly in modern syntax */
```

**HSL** — Hue, Saturation, Lightness; intuitive for adjusting shades of the same color:

```css
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);
```

**Modern color functions**

| Function | Purpose |
|---|---|
| `lab()` | CIE Lab color space — perceptually uniform |
| `lch()` | Lightness, Chroma, Hue variant of Lab |
| `oklab()` | Improved perceptually uniform color space |
| `oklch()` | Lightness, Chroma, Hue variant of OKLab — increasingly popular for design systems |
| `color()` | Specify a color in a named color space (e.g. `display-p3`) |

**Color concepts**

- **Alpha transparency** — the transparency channel of a color itself (e.g. `rgba`, `#RRGGBBAA`)
- **Opacity** — the `opacity` property affects the whole element (and its children), not just color
- **`currentColor`** — reuses the element's text color in another property (e.g. `border-color: currentColor`)
- **Color interpolation** — how gradients and transitions blend between colors (affected by color space)
- **Relative colors** — newer syntax to derive a new color from an existing one (e.g. `hsl(from var(--base) h s calc(l - 10%))`), supported in recent browsers

**When to use which format:** HEX for fixed design tokens copied from design tools; RGB/HSL when you need readable, adjustable values (HSL is easiest for tweaking lightness); `oklch()`/`oklab()` when perceptual consistency across a color palette matters (e.g. generating shades).

---

## 4. Backgrounds

| Property | Purpose |
|---|---|
| `background` | Shorthand for all background properties |
| `background-color` | Solid background color |
| `background-image` | One or more images/gradients |
| `background-repeat` | `repeat`, `no-repeat`, `repeat-x`, `repeat-y` |
| `background-position` | Position of the image (e.g. `center`, `top left`) |
| `background-size` | `cover`, `contain`, or explicit dimensions |
| `background-attachment` | `scroll`, `fixed`, `local` |
| `background-origin` | Positioning area: `border-box`, `padding-box`, `content-box` |
| `background-clip` | How far the background extends: `border-box`, `padding-box`, `content-box`, `text` |
| `background-blend-mode` | Blends multiple backgrounds/colors (e.g. `multiply`, `overlay`) |

**Multiple backgrounds** — stack images/gradients by separating with commas (first listed is on top):

```css
.hero {
  background:
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url("hero.jpg") center/cover no-repeat;
}
```

This same pattern is the standard way to create a **background overlay** on an image.

---

## 5. Gradients

| Type | Function | Key concepts |
|---|---|---|
| Linear | `linear-gradient()` | Direction/angle, color stops |
| Radial | `radial-gradient()` | Shape (`circle`/`ellipse`), size, position, color stops |
| Conic | `conic-gradient()` | `from` angle, position, color stops |

```css
.linear { background: linear-gradient(90deg, #2563eb, #7c3aed); }
.radial { background: radial-gradient(circle at center, #fff, #ccc); }
.conic  { background: conic-gradient(from 90deg, red, yellow, green, red); }
```

**Repeating gradients** — `repeating-linear-gradient()`, `repeating-radial-gradient()`, `repeating-conic-gradient()` tile the gradient pattern, useful for stripes and patterned backgrounds.

---

## 6. Typography

**Font properties**

| Property | Purpose |
|---|---|
| `font` | Shorthand for font properties |
| `font-family` | Typeface stack, with fallbacks |
| `font-size` | Text size |
| `font-weight` | Boldness (e.g. `400`, `700`, `bold`) |
| `font-style` | `normal`, `italic`, `oblique` |
| `font-variant` | Typographic variants (e.g. small caps) |
| `font-stretch` | Condensed/expanded variants |
| `font-size-adjust` | Keeps x-height consistent across fallback fonts |
| `font-feature-settings` | Low-level OpenType feature control |
| `font-kerning` | Enables/disables kerning |
| `font-optical-sizing` | Adjusts glyph shapes for the rendered size (variable fonts) |
| `font-variation-settings` | Fine control over variable font axes |

**Text properties**

`color`, `text-align`, `text-align-last`, `text-indent`, `text-transform` (`uppercase`/`lowercase`/`capitalize`), `text-decoration` and its longhands (`text-decoration-line`, `-color`, `-style`, `-thickness`), `text-underline-offset`, `text-shadow`, `text-overflow` (commonly `ellipsis`), `text-rendering`, `text-size-adjust`.

**Spacing:** `letter-spacing`, `word-spacing`, `line-height`.

**White space and wrapping:** `white-space` (controls wrapping/collapsing of spaces), `word-break`, `overflow-wrap`, `hyphens` (enables automatic hyphenation).

```css
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

---

## 7. Box Model

Every element is rendered as a box:

```text
Margin
 └── Border
      └── Padding
           └── Content
```

| Property | Purpose |
|---|---|
| `width` / `height` | Content dimensions |
| `min-width` / `max-width` | Width constraints |
| `min-height` / `max-height` | Height constraints |
| `margin` (+ `-top/right/bottom/left`) | Space outside the border |
| `padding` (+ `-top/right/bottom/left`) | Space between border and content |
| `border` | Element's edge — see [Border](#8-border) |
| `box-sizing` | How width/height are calculated |

**`box-sizing`**

- `content-box` (default) — `width`/`height` apply to content only; padding and border are added on top
- `border-box` — `width`/`height` include padding and border, which makes sizing far more predictable

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

**Margin collapsing** — vertical margins between adjacent block-level elements (or a parent and its first/last child, in some cases) can collapse into a single margin equal to the larger of the two, rather than summing.

---

## 8. Border

| Property | Purpose |
|---|---|
| `border` | Shorthand: width, style, color |
| `border-width`, `border-style`, `border-color` | Individual shorthand pieces |
| `border-top/right/bottom/left` | Per-side shorthand |
| Individual widths/styles/colors | e.g. `border-top-width`, `border-left-color` |
| `border-radius` | Rounded corners (shorthand) |
| `border-top-left-radius`, etc. | Per-corner radius |
| `border-image`, `border-image-source/slice/width/outset/repeat` | Use an image as a border |

```css
.card {
  border: 1px solid #e2e8f0;
  border-radius: 12px;
}
```

---

## 9. Outline

| Property | Purpose |
|---|---|
| `outline` | Shorthand: width, style, color |
| `outline-width`, `outline-style`, `outline-color` | Individual pieces |
| `outline-offset` | Gap between the outline and the element's edge |

**Border vs outline:** `border` is part of the box model and affects layout size; `outline` is drawn outside the box, doesn't affect layout, and can't have individually-styled sides. Outlines are commonly used for accessible focus indicators since they don't shift surrounding content.

---

## 10. Display

| Value | Behavior |
|---|---|
| `block` | Full-width box, starts on a new line |
| `inline` | Flows with text, ignores width/height |
| `inline-block` | Flows inline but respects width/height |
| `none` | Removed from layout entirely |
| `flex` / `inline-flex` | Establishes a flex formatting context |
| `grid` / `inline-grid` | Establishes a grid formatting context |
| `table`, `table-row`, `table-cell` | Table-like layout without table markup |
| `contents` | Element's box disappears; children behave as if the parent didn't exist |
| `flow-root` | Establishes a new block formatting context (contains floats cleanly) |

---

## 11. Positioning

| Value | Behavior |
|---|---|
| `static` | Default; normal document flow, offsets ignored |
| `relative` | Offset from its normal position; still occupies original space |
| `absolute` | Removed from flow; positioned relative to nearest positioned ancestor |
| `fixed` | Positioned relative to the viewport; stays put when scrolling |
| `sticky` | Toggles between relative and fixed based on scroll position |

**Offsets:** `top`, `right`, `bottom`, `left`, and the shorthand `inset` (plus logical variants `inset-block`, `inset-inline`, `inset-block-start`, `inset-block-end`, `inset-inline-start`, `inset-inline-end`).

**Containing block:** the reference box an absolutely/fixed positioned element is placed relative to — typically the nearest ancestor with a `position` other than `static`.

**Stacking context and `z-index`:** elements with a positioned value and a `z-index` create a stacking context. `z-index` only compares elements within the *same* stacking context — a high `z-index` inside a low-stacking parent still stays beneath other contexts.

---

## 12. Overlay Techniques

A dedicated pattern reference for building overlays — a very common real-world UI need.

**Core pattern:** a relatively positioned parent with an absolutely positioned child that fills it.

```css
.container {
  position: relative;
}

.overlay {
  position: absolute;
  inset: 0;
  z-index: 2;
}
```

| Technique | How |
|---|---|
| Background overlay | Semi-transparent `background: rgba(...)` on an absolute layer |
| Gradient overlay | `background: linear-gradient(rgba(0,0,0,0.6), transparent)` |
| Image overlay | Overlay layer stacked above an `<img>` or background image |
| Pseudo-element overlay | Use `::before`/`::after` with `position: absolute; inset: 0;` instead of an extra element |
| Text overlay | Absolutely positioned text layer over an image |
| Dark / color overlay | Solid or gradient `rgba()`/`hsla()` layer for contrast |
| Hover overlay | Overlay revealed via `:hover` and `opacity`/`transition` |
| Modal overlay | Fixed, full-screen dimmed layer behind a centered dialog |
| Full-screen / fixed overlay | `position: fixed; inset: 0;` so it stays in place while scrolling |

```css
/* pseudo-element image overlay on hover */
.thumb {
  position: relative;
  overflow: hidden;
}

.thumb::after {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.4);
  opacity: 0;
  transition: opacity 0.2s ease;
}

.thumb:hover::after {
  opacity: 1;
}
```

```css
/* full-screen modal overlay */
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.6);
  z-index: 100;
}
```

---

## 13. Overflow

| Property | Purpose |
|---|---|
| `overflow` | Shorthand for both axes |
| `overflow-x` / `overflow-y` | Per-axis control |
| `overflow-wrap` | Allows breaking long words to prevent overflow |
| `text-overflow` | How clipped text is signaled (commonly `ellipsis`) |
| `clip` | Legacy clipping property (largely superseded by `clip-path`) |

**Values:** `visible` (default, content can spill out), `hidden` (clipped, no scrolling), `scroll` (always shows scrollbars), `auto` (scrollbars only when needed).

**Common patterns:** text ellipsis (see [Typography](#6-typography)), scroll containers (`overflow: auto` with a fixed height/width), horizontal overflow for carousels (`overflow-x: auto`), vertical overflow for scrollable panels (`overflow-y: auto`).

---

## 14. Visibility

| Property | Effect | Keeps layout space? | Interactive? |
|---|---|---|---|
| `visibility: hidden` | Hides the element visually | Yes | No |
| `opacity: 0` | Fully transparent | Yes | Yes (still clickable/focusable by default) |
| `display: none` | Removes from rendering entirely | No | No |

Choosing between them depends on whether you need to animate visibility (`opacity` transitions smoothly; `display` cannot), preserve layout space (`visibility`/`opacity`), or fully remove the element from the accessibility tree and layout (`display: none`).

---

## 15. Flexbox

One-dimensional layout for arranging items along a single main axis (row or column).

**Container properties**

| Property | Purpose |
|---|---|
| `display: flex` / `inline-flex` | Enables flex layout |
| `flex-direction` | `row`, `row-reverse`, `column`, `column-reverse` |
| `flex-wrap` | `nowrap`, `wrap`, `wrap-reverse` |
| `flex-flow` | Shorthand for direction + wrap |
| `justify-content` | Alignment along the main axis |
| `align-items` | Alignment along the cross axis |
| `align-content` | Aligns wrapped lines (multi-row) |
| `gap`, `row-gap`, `column-gap` | Space between items |

**Item properties**

| Property | Purpose |
|---|---|
| `order` | Visual reorder without changing markup |
| `flex-grow` | How much an item grows to fill space |
| `flex-shrink` | How much an item shrinks under pressure |
| `flex-basis` | Item's starting size before growing/shrinking |
| `flex` | Shorthand for grow, shrink, basis |
| `align-self` | Overrides `align-items` for one item |

**Main axis vs cross axis:** in `flex-direction: row`, the main axis is horizontal and the cross axis is vertical (and swapped for `column`). `justify-content` always acts on the main axis; `align-items`/`align-self` always act on the cross axis.

```css
/* Perfect centering */
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* Simple navbar */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Responsive card row */
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
.cards > .card {
  flex: 1 1 240px;
}
```

---

## 16. Alignment

Alignment properties look similar but apply in different contexts — this is one of the most common sources of confusion in CSS.

**Flexbox**

| Property | Axis | Applies to |
|---|---|---|
| `justify-content` | Main axis | All items as a group |
| `align-items` | Cross axis | All items as a group |
| `align-content` | Cross axis | Wrapped lines (only matters with `flex-wrap`) |
| `align-self` | Cross axis | A single item, overrides `align-items` |

**Grid**

| Property | Axis | Applies to |
|---|---|---|
| `justify-items` | Inline (row) axis | All items, within their cell |
| `align-items` | Block (column) axis | All items, within their cell |
| `place-items` | Both | Shorthand for `align-items justify-items` |
| `justify-content` | Inline axis | The whole grid within its container |
| `align-content` | Block axis | The whole grid within its container |
| `place-content` | Both | Shorthand for `align-content justify-content` |
| `justify-self` / `align-self` | Either | A single item, overrides the `-items` version |
| `place-self` | Both | Shorthand for `align-self justify-self` |

**General alignment:** `text-align` aligns inline content (text) within a block; `vertical-align` affects inline or table-cell elements only — it is *not* a general layout alignment tool and doesn't work on block/flex/grid items.

**The core distinction to remember:**

- `justify-*` / `align-*` **without** `-content` or `-self` → aligns items as individuals *within their own space*
- `*-content` → aligns the group of items, or extra space, *within the container*
- `*-self` → overrides alignment for *one specific item*

---

## 17. CSS Grid

Two-dimensional layout for arranging items in rows and columns simultaneously.

**Grid container**

| Property | Purpose |
|---|---|
| `display: grid` / `inline-grid` | Enables grid layout |
| `grid-template-columns` / `-rows` | Defines explicit tracks |
| `grid-template-areas` | Named layout regions |
| `grid-template` | Shorthand for rows/columns/areas |
| `grid-auto-columns` / `-rows` | Sizing for implicitly created tracks |
| `grid-auto-flow` | Placement algorithm: `row`, `column`, `dense` |
| `gap`, `row-gap`, `column-gap` | Space between tracks (`grid-row-gap`/`grid-column-gap` are legacy aliases) |

**Alignment:** `justify-items`, `align-items`, `place-items`, `justify-content`, `align-content`, `place-content` — see [Alignment](#16-alignment).

**Grid items**

| Property | Purpose |
|---|---|
| `grid-column` (+ `-start`/`-end`) | Column placement/span |
| `grid-row` (+ `-start`/`-end`) | Row placement/span |
| `grid-area` | Shorthand placement, or a named area reference |
| `justify-self` / `align-self` / `place-self` | Per-item alignment |

**Grid functions:** `repeat(count, size)` for repeating tracks, `minmax(min, max)` for flexible track sizing, and the keywords `auto-fit`/`auto-fill` (used with `repeat()`) to create responsive grids without media queries.

**Key concepts:** *grid lines* are the dividing lines that form the structure; *tracks* are the rows/columns between lines; *cells* are single intersections; *areas* are named or spanning rectangular regions; the *explicit grid* is what you define with `grid-template-*`, while the *implicit grid* is auto-generated for content that overflows it.

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
}
```

See [Flexbox vs Grid](#54-flexbox-vs-grid) for guidance on which to choose.

---

## 18. Tables

| Property | Purpose |
|---|---|
| `border-collapse` | Merges adjacent cell borders (`collapse`) or keeps them separate (`separate`) |
| `border-spacing` | Gap between cell borders (when not collapsed) |
| `caption-side` | Position of the `<caption>` element |
| `empty-cells` | Whether borders/backgrounds show on empty cells |
| `table-layout` | `auto` (content-based) or `fixed` (faster, predictable column widths) |
| `vertical-align` | Vertical alignment of cell content |

```css
table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  border: 1px solid #e2e8f0;
  padding: 0.5rem 0.75rem;
  text-align: left;
}

thead {
  background-color: #f8fafc;
}
```

---

## 19. Lists

| Property | Purpose |
|---|---|
| `list-style` | Shorthand for type, position, image |
| `list-style-type` | Marker style (`disc`, `decimal`, `none`, etc.) |
| `list-style-position` | `inside` or `outside` the content box |
| `list-style-image` | Custom image as the marker |
| `::marker` | Pseudo-element for styling the marker itself (color, font-size) |

---

## 20. Images

| Property | Purpose |
|---|---|
| `object-fit` | How replaced content (image/video) fills its box: `cover`, `contain`, `fill`, `none`, `scale-down` |
| `object-position` | Positions the content within its box, similar to `background-position` |
| `aspect-ratio` | Enforces a width-to-height ratio |
| `image-rendering` | Hints for scaling algorithm (e.g. `pixelated` for crisp pixel art) |

**Responsive images:** typically `width: 100%; height: auto;` combined with `max-width`, or the HTML `srcset`/`sizes` attributes for serving different resolutions.

**Image cropping/positioning:** `object-fit: cover` with a fixed-size container is the standard way to crop an `<img>` to fill a box without distortion.

**Background images vs `<img>`:** use `<img>` for meaningful, content-bearing images (accessible via `alt` text, indexable); use CSS background images for purely decorative visuals that aren't part of the page's content.

---

## 21. Filters

| Function | Effect |
|---|---|
| `blur(px)` | Gaussian blur |
| `brightness(%)` | Lightens/darkens |
| `contrast(%)` | Adjusts contrast |
| `drop-shadow(...)` | Shadow that follows the element's alpha shape (unlike `box-shadow`) |
| `grayscale(%)` | Desaturates |
| `hue-rotate(deg)` | Shifts hues around the color wheel |
| `invert(%)` | Inverts colors |
| `opacity(%)` | Alternative to the `opacity` property |
| `saturate(%)` | Adjusts color intensity |
| `sepia(%)` | Sepia tone |
| `none` | No filter applied |

```css
.photo { filter: grayscale(100%); }
.photo:hover { filter: grayscale(0%) brightness(1.05); }

/* combining multiple filters */
.dramatic { filter: contrast(120%) saturate(150%) brightness(90%); }
```

**`backdrop-filter`** applies filter effects to whatever is *behind* an element (through its transparent/translucent background) — the basis of the "glassmorphism" effect:

```css
.glass {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}
```

---

## 22. Shadows

| Property | Purpose |
|---|---|
| `box-shadow` | Shadow around an element's box |
| `text-shadow` | Shadow behind text |

`box-shadow` accepts `offset-x offset-y blur-radius spread-radius color`, and the `inset` keyword for an inner shadow. Multiple shadows can be comma-separated to build layered depth (soft ambient shadow + tighter contact shadow), and the same technique produces glow effects using a bright, saturated color with a larger blur radius.

```css
.card {
  box-shadow: 0 1px 2px rgba(0,0,0,0.06), 0 8px 24px rgba(0,0,0,0.08);
}

.glow {
  box-shadow: 0 0 20px rgba(37, 99, 235, 0.6);
}

.inset {
  box-shadow: inset 0 2px 4px rgba(0,0,0,0.15);
}
```

---

## 23. Transitions

| Property | Purpose |
|---|---|
| `transition` | Shorthand for all transition properties |
| `transition-property` | Which property/properties to animate |
| `transition-duration` | How long the transition takes |
| `transition-timing-function` | Acceleration curve |
| `transition-delay` | Wait time before starting |
| `transition-behavior` | Controls whether discrete properties (like `display`) can transition (modern browsers) |

**Timing functions:** `ease` (default), `linear`, `ease-in`, `ease-out`, `ease-in-out`, `steps(n)` (discrete jumps), `cubic-bezier(x1,y1,x2,y2)` (fully custom curve).

```css
.button {
  transition: background-color 0.25s ease-in-out, transform 0.2s ease;
}
.button:hover {
  background-color: #1d4ed8;
  transform: translateY(-2px);
}
```

---

## 24. 2D Transforms

| Function | Effect |
|---|---|
| `translate(x, y)` / `translateX()` / `translateY()` | Moves an element |
| `scale(x, y)` / `scaleX()` / `scaleY()` | Resizes an element |
| `rotate(deg)` | Rotates around its origin |
| `skew(x, y)` / `skewX()` / `skewY()` | Slants an element |
| `matrix()` | Combines multiple 2D transforms into one matrix |

`transform-origin` sets the pivot point for scaling/rotating (default is the element's center).

```css
.card:hover {
  transform: translateY(-4px) scale(1.02);
}
```

---

## 25. 3D Transforms

| Function / Property | Purpose |
|---|---|
| `translateZ()` / `translate3d()` | Moves along/including the Z axis |
| `scale3d()` | Scales in three dimensions |
| `rotateX()` / `rotateY()` / `rotateZ()` / `rotate3d()` | Rotation around a given axis |
| `perspective` | Distance from viewer to the Z=0 plane — creates depth |
| `perspective-origin` | Vanishing point position |
| `transform-style: preserve-3d` | Keeps children in the same 3D space as the parent |
| `backface-visibility` | Whether an element is visible when rotated away from the viewer |

```css
/* Simple 3D flip card */
.flip-card {
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  inset: 0;
  backface-visibility: hidden;
}

.flip-card-back {
  transform: rotateY(180deg);
}
```

---

## 26. Animations

| Property | Purpose |
|---|---|
| `@keyframes` | Defines the animation's stages |
| `animation` | Shorthand for all animation properties |
| `animation-name` | Links to a `@keyframes` name |
| `animation-duration` | Length of one cycle |
| `animation-timing-function` | Acceleration curve (same options as transitions) |
| `animation-delay` | Wait before starting |
| `animation-iteration-count` | Number of repeats, or `infinite` |
| `animation-direction` | `normal`, `reverse`, `alternate`, `alternate-reverse` |
| `animation-fill-mode` | State before/after playing: `none`, `forwards`, `backwards`, `both` |
| `animation-play-state` | `running` or `paused` |
| `animation-composition` | How multiple animations on the same property combine (modern browsers) |

```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

.fade-in {
  animation: fadeIn 0.4s ease-out both;
}

.spinner {
  animation: spin 1s linear infinite;
}
```

Common patterns built from these building blocks: fade in, slide in, bounce (`ease` with `alternate`), rotate/scale accents, hover-triggered animations, and infinite loading indicators (as above).

---

## 27. Pseudo-Classes

| Category | Selectors |
|---|---|
| Interaction | `:hover`, `:active`, `:focus`, `:focus-visible`, `:focus-within` |
| Link state | `:link`, `:visited` |
| Form state | `:checked`, `:disabled`, `:enabled`, `:required`, `:optional`, `:valid`, `:invalid`, `:in-range`, `:out-of-range`, `:read-only`, `:read-write`, `:placeholder-shown`, `:default` |
| Structural | `:first-child`, `:last-child`, `:only-child`, `:nth-child()`, `:nth-last-child()`, `:first-of-type`, `:last-of-type`, `:only-of-type`, `:nth-of-type()`, `:empty` |
| Document | `:root`, `:target` |
| Logical/combinator | `:not()`, `:is()`, `:where()`, `:has()` |

```css
input:invalid { border-color: crimson; }
li:nth-child(odd) { background: #f8fafc; }
```

---

## 28. Pseudo-Elements

| Pseudo-element | Purpose |
|---|---|
| `::before` / `::after` | Inserts generated content before/after an element's content |
| `::first-letter` | Styles the first letter of a block |
| `::first-line` | Styles the first rendered line |
| `::selection` | Styles user-highlighted text |
| `::placeholder` | Styles input placeholder text |
| `::marker` | Styles list item / summary markers |
| `::file-selector-button` | Styles the button part of `<input type="file">` |

`::before` and `::after` require the `content` property to render (even `content: "";` for a purely visual layer) and are inserted as the element's first/last child in the render tree — they don't exist in the actual DOM.

```css
.tooltip::after {
  content: attr(data-tooltip);
  position: absolute;
  /* ... */
}
```

---

## 29. CSS Variables

Custom properties store reusable values, typically defined on `:root` for global scope or on a specific selector for component/theme scope.

```css
:root {
  --primary-color: #2563eb;
  --spacing: 1rem;
}

.button {
  background-color: var(--primary-color);
  padding: var(--spacing);
}

.button--danger {
  --primary-color: #dc2626; /* component-level override */
}
```

`var()` accepts an optional fallback: `var(--accent, #000)` uses `#000` if `--accent` isn't defined. This mechanism is also the standard approach for **dark mode**, redefining the same variable names inside a `[data-theme="dark"]` selector or a `prefers-color-scheme` media query.

---

## 30. CSS Units

**Absolute:** `px`, `cm`, `mm`, `in`, `pt`, `pc`

**Relative:** `%`, `em` (relative to parent font-size), `rem` (relative to root font-size), `ex`, `ch` (width of the `0` character)

**Viewport:** `vw`, `vh`, `vmin`, `vmax`

**Modern viewport units:** `svh`/`svw` (small viewport, excludes dynamic browser UI), `lvh`/`lvw` (large viewport, assumes UI is hidden), `dvh`/`dvw` (dynamic, updates live as browser UI shows/hides) — these solve the classic mobile-browser "100vh is taller than the visible screen" problem.

**When to use which:** `px` for fixed, precise values (borders, small icons); `%` for sizing relative to a parent container; `rem` for typography and spacing that should scale consistently with the user's root font-size setting; `em` when a value should scale with its *own* element's font-size (e.g. padding that grows with text); `vw`/`vh` for full-viewport sections and rarely for fluid typography (usually paired with `clamp()`).

---

## 31. CSS Functions

| Function | Purpose |
|---|---|
| `var()` | Reads a custom property |
| `calc()` | Mixes units in a single expression |
| `min()` | Smallest of a list of values |
| `max()` | Largest of a list of values |
| `clamp(min, preferred, max)` | Fluid value with a floor and ceiling |
| `minmax()` | Grid track sizing range |
| `repeat()` | Repeats grid track definitions |
| `url()` | References an external resource |
| `attr()` | Reads an HTML attribute's value (mainly used with `content`) |
| Color functions | `rgb()`, `hsl()`, `oklch()`, etc. (see [CSS Colors](#3-css-colors)) |
| Gradient functions | `linear-gradient()`, `radial-gradient()`, etc. (see [Gradients](#5-gradients)) |

```css
.container {
  width: calc(100% - 2rem);
}

h1 {
  font-size: clamp(1.5rem, 4vw, 3rem); /* fluid, responsive typography */
}
```

---

## 32. Media Queries

```css
@media (max-width: 768px) {
  .nav { flex-direction: column; }
}
```

**Common features:** `max-width`/`min-width`, `orientation` (`portrait`/`landscape`), `resolution`, `hover` (does the input support hovering?), `pointer` (`fine`/`coarse`), `prefers-color-scheme` (`light`/`dark`), `prefers-reduced-motion`.

**Mobile-first design:** write base styles for small screens, then use `min-width` queries to add complexity for larger viewports. **Breakpoints** are the viewport widths where layout changes are triggered — commonly chosen based on common device widths, though content-driven breakpoints (where the design itself starts to break) are considered more robust than fixed device sizes.

---

## 33. Container Queries

```css
.card-wrapper {
  container-type: inline-size;
  container-name: card;
}

@container card (min-width: 400px) {
  .card {
    flex-direction: row;
  }
}
```

| Property | Purpose |
|---|---|
| `container-type` | Enables querying (`inline-size`, `size`, `normal`) |
| `container-name` | Optional name to target specific containers |
| `container` | Shorthand for name + type |
| `@container` | Rule that applies styles based on the container's size |

**Media Queries vs Container Queries:** media queries respond to the *viewport's* size; container queries respond to a specific *container's* size, regardless of where it sits on the page — this makes components truly reusable and responsive independent of their placement.

---

## 34. Logical Properties

| Physical equivalent | Logical property |
|---|---|
| `margin-left`/`margin-right` | `margin-inline` |
| `margin-top`/`margin-bottom` | `margin-block` |
| `padding-left`/`padding-right` | `padding-inline` |
| `padding-top`/`padding-bottom` | `padding-block` |
| `border-left`/`border-right` | `border-inline` |
| `border-top`/`border-bottom` | `border-block` |
| `left`/`right` (offsets) | `inset-inline` |
| `top`/`bottom` (offsets) | `inset-block` |
| `width` | `inline-size` |
| `height` | `block-size` |
| `min-width`/`max-width` | `min-inline-size`/`max-inline-size` |
| `min-height`/`max-height` | `min-block-size`/`max-block-size` |

Logical properties are expressed relative to the text's **writing mode** (inline = the direction text flows; block = the direction lines stack) rather than fixed physical directions. This means a single stylesheet automatically adapts correctly for right-to-left languages (e.g. Arabic, Hebrew) or vertical writing modes, without needing separate LTR/RTL overrides.

---

## 35. Aspect Ratio

```css
.video-wrapper {
  aspect-ratio: 16 / 9;
}
```

Common use cases: keeping video/iframe embeds proportional without JavaScript, reserving image space before it loads (preventing layout shift), and enforcing consistent card or thumbnail proportions in a grid.

---

## 36. Cursor

Common values: `default`, `pointer`, `text`, `move`, `grab`, `grabbing`, `not-allowed`, `wait`, `help`, `crosshair`, `zoom-in`, `zoom-out`.

```css
.draggable { cursor: grab; }
.draggable:active { cursor: grabbing; }
```

---

## 37. User Select

| Value | Effect |
|---|---|
| `none` | Text can't be selected |
| `text` | Normal text selection |
| `all` | Selecting anywhere in the element selects all of its content |
| `auto` | Browser default behavior |

Commonly used to prevent accidental text selection on interactive UI (buttons, drag handles) via `user-select: none`.

---

## 38. Pointer Events

| Value | Effect |
|---|---|
| `auto` | Normal behavior — element receives pointer events |
| `none` | Element is ignored by the pointer entirely (clicks pass through to whatever is beneath it) |

```css
/* Overlay that shouldn't block clicks on content beneath it */
.decorative-overlay {
  position: absolute;
  inset: 0;
  pointer-events: none;
}
```

---

## 39. Scrolling

| Property | Purpose |
|---|---|
| `overflow` / `overflow-x` / `overflow-y` | Enables scrolling (see [Overflow](#13-overflow)) |
| `scroll-behavior` | `smooth` enables animated scrolling for in-page jumps |
| `scroll-snap-type` | Enables snap scrolling on a container, and its axis/strictness |
| `scroll-snap-align` | Where a child snaps to (`start`, `center`, `end`) |
| `scroll-snap-stop` | Forces stopping at each snap point (`always`) |
| `overscroll-behavior` | Controls scroll chaining (e.g. preventing a modal's scroll from also scrolling the page behind it) |

```css
.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
}
.carousel > * {
  scroll-snap-align: start;
}
```

---

## 40. Accessibility-Related CSS

- **`:focus` / `:focus-visible`** — ensure interactive elements have a clearly visible focus state; `:focus-visible` lets you show strong focus rings for keyboard users without necessarily showing them on every mouse click.
- **`prefers-reduced-motion`** — respect users who've asked the OS to minimize motion, by reducing or disabling non-essential animations.
- **`forced-colors`** — a media feature for adapting to Windows High Contrast Mode and similar forced-color settings.
- **Visually-hidden techniques** — CSS patterns to hide content visually while keeping it available to screen readers (clipping to a 1px box rather than using `display: none`, which removes it from the accessibility tree too).
- **Sufficient color contrast** — text and meaningful UI should meet contrast guidelines (e.g. WCAG AA) against their background.
- **Avoiding color-only communication** — don't rely on color alone to convey meaning (e.g. error states); pair it with an icon, label, or pattern.

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.001ms !important;
    transition-duration: 0.001ms !important;
  }
}
```

> This section covers CSS-level techniques only and is not a complete accessibility guide — accessibility also depends heavily on semantic HTML, ARIA usage, and testing with real assistive technology.

---

## 41. CSS Media Features

Features usable inside `@media` (and some inside `@container`): `width`, `height`, `orientation`, `resolution`, `hover`, `pointer`, `any-hover`, `any-pointer`, `prefers-color-scheme`, `prefers-reduced-motion`, `prefers-contrast`, `forced-colors`.

`hover`/`pointer` vs `any-hover`/`any-pointer`: the plain versions describe the *primary* input; the `any-` versions describe whether *any available* input supports that capability (useful for devices with both touch and a mouse/trackpad).

---

## 42. Cascade and Specificity

**The cascade** resolves conflicting declarations using, in order: origin and importance → layer order → specificity → source order (later wins ties).

**Specificity** is calculated as a tuple of (inline styles, ID selectors, class/attribute/pseudo-class selectors, element/pseudo-element selectors):

| Selector | Specificity |
|---|---|
| `style="..."` (inline) | Highest |
| `#header` | 1 ID |
| `.card.active` | 2 classes |
| `div.card` | 1 element, 1 class |
| `p` | 1 element |

```css
/* Specificity example: .card.active (0,2,0) beats .card (0,1,0) regardless of order */
.card { color: black; }
.card.active { color: blue; }
```

**Inheritance** passes certain property values down from parent to child automatically (see [Fundamentals](#1-css-fundamentals)).

**`!important`** overrides normal cascade ordering for that declaration, but can still be beaten by another `!important` declaration with higher specificity — it should be used sparingly, as it makes styles harder to override predictably.

**Cascade layers (`@layer`)** — see next section.

---

## 43. Cascade Layers

```css
@layer reset, components, utilities;

@layer reset {
  * { margin: 0; padding: 0; }
}

@layer components {
  .button { padding: 0.5rem 1rem; }
}

@layer utilities {
  .mt-4 { margin-top: 1rem; }
}
```

**Why they exist:** without layers, managing specificity across a reset, a component library, and utility classes often devolves into specificity wars and `!important` overrides. Layers let you control precedence *by group* rather than by writing increasingly specific selectors.

**Layer order:** layers declared earlier have lower priority than layers declared later, regardless of selector specificity *within* those layers — specificity only matters for resolving conflicts inside the same layer. Unlayered styles have the highest priority of all.

**Practical use:** typically ordered `reset → base → components → utilities`, so utility classes can reliably override component styles without needing extra specificity.

---

## 44. CSS Nesting

Native CSS nesting lets related rules be grouped without a preprocessor.

```css
.card {
  color: black;

  &:hover {
    color: blue;
  }

  .card-title {
    font-weight: 600;
  }
}
```

The `&` refers to the parent selector explicitly, which is required when combining with a pseudo-class directly (`&:hover`) but optional for descendant selectors. Native nesting is supported in current versions of all major browsers; for projects that need to support older browsers, a preprocessor like Sass can be used instead with the same syntax patterns.

---

## 45. Modern CSS Features

A quick index of newer CSS capabilities referenced throughout this document:

| Feature | Section |
|---|---|
| CSS Nesting | [§44](#44-css-nesting) |
| Container Queries | [§33](#33-container-queries) |
| Cascade Layers | [§43](#43-cascade-layers) |
| `:has()`, `:is()`, `:where()` | [§2](#2-css-selectors), [§27](#27-pseudo-classes) |
| `clamp()`, `min()`, `max()` | [§31](#31-css-functions) |
| Logical Properties | [§34](#34-logical-properties) |
| Modern viewport units | [§30](#30-css-units) |
| Modern color spaces (`oklch`, `lab`) | [§3](#3-css-colors) |
| `aspect-ratio` | [§35](#35-aspect-ratio) |
| `backdrop-filter` | [§21](#21-filters) |
| Scroll Snap | [§39](#39-scrolling) |
| `content-visibility` | Rendering optimization — skips rendering work for off-screen content (`content-visibility: auto`), improving initial load performance for long pages |

---

## 46. CSS Reset and Normalization

Browsers ship with default styles (margins on `<body>`, list bullets, heading sizes, etc.) that differ slightly between browsers. A **CSS reset** removes or neutralizes these defaults so styling starts from a consistent baseline; **normalization** (e.g. normalize.css) instead makes defaults *consistent* across browsers rather than removing them entirely.

```css
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

Combined with `box-sizing: border-box` globally (see [Box Model](#7-box-model)), this is the most common minimal starting point for a new stylesheet.

---

## 47. CSS Architecture

Practices for keeping stylesheets maintainable as a project grows:

- **Reusable classes** over one-off, single-use styles
- **Component-based CSS** — scope styles to a component's root class
- **Utility classes** — small, single-purpose classes (e.g. `.mt-4`, `.text-center`) for common adjustments
- **Naming conventions** — consistent, predictable class naming
- **BEM methodology** — `.block__element--modifier` naming to make relationships explicit and reduce nesting-based specificity
- **Avoiding unnecessary specificity** — prefer classes over ID selectors and deep nesting in stylesheets
- **CSS variables** for shared design tokens (see [§29](#29-css-variables))
- **Organizing stylesheets** — logical file/section structure (reset, base, components, utilities, layout)
- **Scalable CSS** — patterns that stay maintainable as the number of components grows, rather than accumulating overrides

---

## 48. Responsive Design

- **Mobile-first vs desktop-first** — start from the smallest viewport and add complexity upward (mobile-first) versus starting from the largest and constraining downward (desktop-first); mobile-first is the more common modern default.
- **Fluid layouts** — percentage/`fr`-based sizing instead of fixed pixel widths
- **Flexible units** — `%`, `rem`, `vw`/`vh`, `clamp()` instead of hardcoded pixels where appropriate
- **Responsive typography** — `clamp()` for fluid font sizes (see [§31](#31-css-functions))
- **Responsive images** — `object-fit`, `srcset`, `max-width: 100%`
- **Responsive Flexbox/Grid** — `flex-wrap`, `repeat(auto-fit, minmax(...))`
- **Breakpoints** — see [§32](#32-media-queries)
- **Container Queries** — component-level responsiveness, see [§33](#33-container-queries)

---

## 49. Common UI Components

Reference patterns and concepts for building typical interface pieces using the properties covered above:

| Component | Key techniques used |
|---|---|
| Buttons | Padding, `border-radius`, transitions, `:hover`/`:focus-visible` |
| Cards | Box model, `box-shadow`, `border-radius`, Flexbox/Grid |
| Navbar | Flexbox, `position: sticky` |
| Hero section | Background overlay, Flexbox/Grid centering |
| Forms & input fields | Pseudo-classes (`:focus`, `:invalid`), spacing, transitions |
| Dropdown | `position: absolute`, `:hover`/`:focus-within`, transitions |
| Modal | Fixed overlay, centered Flexbox/Grid, `z-index` |
| Tooltip | `::after`/`::before`, `position: absolute`, `attr()` |
| Badge | Inline-block, `border-radius`, small padding |
| Alert | Border-left accent, background tint, spacing |
| Tabs | Flexbox, `:has()`/sibling selectors or scripted active state |
| Accordion | `max-height`/`grid-template-rows` transition, `details`/`summary` |
| Image gallery | CSS Grid, `object-fit` |
| Pricing cards | Grid/Flexbox, box-shadow, hover transforms |
| Responsive grid | `repeat(auto-fit, minmax(...))` |
| Loading spinner | `@keyframes` rotation (see [§26](#26-animations)) |
| Skeleton loader | Animated gradient background (`background-position` keyframes) |
| Toggle switch | Styled checkbox + `::before` thumb, transitions |

> These are documented as techniques and patterns rather than a guarantee that a finished example exists for every component in the current repository — see [Repository Structure](#57-repository-structure).

---

## 50. CSS Effects

Effects achievable by combining the properties above:

- **Hover effects** — transitions on `transform`, `box-shadow`, `color`
- **Glow effects** — saturated `box-shadow`/`text-shadow` with large blur (see [§22](#22-shadows))
- **Glassmorphism** — translucent background + `backdrop-filter: blur()` (see [§21](#21-filters))
- **Neumorphism** — soft dual shadows (light + dark) on a flat background to simulate extrusion
- **Gradients** — see [§5](#5-gradients)
- **Image overlays** — see [§12](#12-overlay-techniques)
- **Text gradients** — `background: linear-gradient(...)` clipped to text via `background-clip: text` and `color: transparent`
- **Blur effects / drop shadows** — see [§21](#21-filters)
- **Card hover effects** — combined `transform` + `box-shadow` transitions
- **Button animations** — transitions and/or `@keyframes` on state change
- **Loading animations** — see [§26](#26-animations)
- **2D/3D transforms** — see [§24](#24-2d-transforms), [§25](#25-3d-transforms)

```css
.text-gradient {
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
}
```

---

## 51. CSS Debugging

- **Browser DevTools** — the primary tool for inspecting and debugging CSS live
- **Inspect Element** — view an element's applied rules and DOM position
- **Computed styles panel** — see the final resolved value of every property, after the cascade
- **Box Model inspector** — visualize margin/border/padding/content sizes directly
- **Flexbox inspector** — overlay showing main/cross axis and alignment for flex containers
- **Grid inspector** — overlay showing track lines, gaps, and named areas
- **Responsive/device mode** — simulate different viewport sizes and device pixel ratios
- **Checking specificity** — DevTools show which rule "won" and which were overridden
- **Checking inherited styles** — computed panel indicates which values came from inheritance
- **Checking overflow** — DevTools can highlight elements causing unexpected scroll/overflow
- **Checking positioning** — inspect offset values and containing blocks directly
- **Checking `z-index`/stacking contexts** — DevTools (e.g. Chrome's 3D view) can visualize stacking order

---

## 52. CSS Best Practices

- Use semantic HTML as the foundation; CSS should style meaning, not replace it
- Prefer reusable classes over repeated inline or overly specific styles
- Avoid excessive specificity — keep selectors as simple as they can be
- Avoid unnecessary `!important`; reach for cascade layers or better specificity management instead
- Use CSS variables for values reused across a project (color palette, spacing scale)
- Use logical properties where internationalization matters
- Use responsive, relative units instead of hardcoded pixels where appropriate
- Keep stylesheets organized by clear structure (reset, base, layout, components, utilities)
- Use consistent naming conventions
- Optimize selectors for readability and maintainability, not just brevity
- Respect accessibility — focus states, contrast, and semantic structure
- Respect `prefers-reduced-motion` for users sensitive to animation
- Keep components self-contained and easy to reuse without side effects

---

## 53. Property Reference

A high-level index by category — see the linked sections above for full property lists and explanations.

| Category | Key Properties |
|---|---|
| Box Model | `width`, `height`, `margin`, `padding`, `border`, `box-sizing` |
| Layout | `display`, `position`, `inset`, `z-index` |
| Flexbox | `flex-direction`, `flex-wrap`, `justify-content`, `align-items` |
| Grid | `grid-template-columns`, `grid-template-rows`, `grid-area` |
| Typography | `font-family`, `font-size`, `font-weight`, `line-height` |
| Background | `background`, `background-image`, `background-size` |
| Transform | `transform`, `transform-origin` |
| Animation | `animation`, `@keyframes` |
| Transition | `transition`, `transition-duration` |
| Effects | `filter`, `backdrop-filter`, `box-shadow` |
| Responsive | `@media`, `@container` |
| Variables | `--custom-property`, `var()` |

---

## 54. Flexbox vs Grid

| Feature | Flexbox | Grid |
|---|---|---|
| Dimension | One-dimensional | Two-dimensional |
| Primary use | Components, single rows/columns, distributing space along one axis | Overall page layout, complex multi-row/column structures |
| Axis control | Main + cross axis, content-driven sizing | Explicit rows and columns, layout-driven sizing |
| Alignment | Excellent (see [§16](#16-alignment)) | Excellent (see [§16](#16-alignment)) |
| Responsive layout | Yes, via `flex-wrap` and `flex` sizing | Yes, via `repeat(auto-fit, minmax())` and media/container queries |

**When to choose which:** reach for Flexbox when arranging items in a single row or column where content size should drive layout (navbars, button groups, card content). Reach for Grid when you need explicit control over both rows and columns at once (full page layouts, dashboards, image galleries) — Grid and Flexbox are also commonly combined, using Grid for the outer page structure and Flexbox inside individual components.

---

## 55. Position vs Flexbox vs Grid

| Use case | Best tool |
|---|---|
| Placing one element precisely relative to another (badges, tooltips, overlays) | Positioning (`relative` + `absolute`) |
| Arranging a row/column of items with flexible spacing | Flexbox |
| Building a full page or component layout with rows and columns | Grid |
| Keeping an element fixed while scrolling (headers, modals) | Positioning (`fixed`/`sticky`) |

A simple way to decide: if you're moving one element out of the normal flow relative to a specific reference point, use **positioning**. If you're distributing multiple items along one direction, use **Flexbox**. If you're structuring a layout in both directions at once, use **Grid**. These tools are frequently combined rather than used in isolation.

---

## 56. Transform vs Transition vs Animation

| Concept | What it does | Needs a trigger? | Needs `@keyframes`? |
|---|---|---|---|
| `transform` | Visually changes an element's position/size/rotation without affecting layout | No — it's a static property | No |
| `transition` | Smoothly animates a property change *between two states* | Yes — a state change (e.g. `:hover`) | No |
| `animation` | Plays a defined, potentially multi-step sequence, with or without a trigger | No — can run automatically | Yes |

```css
/* transform: a static visual change */
.rotated { transform: rotate(10deg); }

/* transition: animates the change between two states */
.button { transition: transform 0.2s ease; }
.button:hover { transform: scale(1.05); }

/* animation: a self-contained, multi-step sequence */
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}
.badge { animation: pulse 2s ease-in-out infinite; }
```

In short: `transform` changes *what* an element looks like, `transition` controls *how* a property change is animated between two states, and `animation` defines a *self-running sequence* of multiple states over time.

---

## 57. Repository Structure

**Current structure** (verified from the repository):

```text
CSS3/
├── CSS3.html   # Practice and example code
└── README.md   # Repository documentation
```

**Planned structure** — as the repository grows, examples are intended to be organized into topic-based folders along these lines:

```text
CSS3/
│
├── FUNDAMENTALS/
├── SELECTORS/
├── COLORS/
├── BACKGROUNDS/
├── TYPOGRAPHY/
├── BOX-MODEL/
├── BORDERS/
├── OUTLINE/
├── DISPLAY/
├── POSITION/
├── OVERFLOW/
├── FLEXBOX/
├── GRID/
├── ALIGNMENT/
├── TABLES/
├── LISTS/
├── IMAGES/
├── FILTER/
├── SHADOWS/
├── TRANSITIONS/
├── TRANSFORMS/
│   ├── 2D/
│   └── 3D/
├── ANIMATIONS/
├── PSEUDO-CLASSES/
├── PSEUDO-ELEMENTS/
├── VARIABLES/
├── UNITS/
├── FUNCTIONS/
├── MEDIA-QUERIES/
├── CONTAINER-QUERIES/
├── RESPONSIVE-DESIGN/
├── LOGICAL-PROPERTIES/
├── ACCESSIBILITY/
├── MODERN-CSS/
└── PROJECTS/
```

> These folders do not currently exist in the repository. This is a target structure for future organization, not a description of the present state.

---

## 58. Learning Progress

Status is intentionally neutral where completion can't be verified from the repository's current contents.

```markdown
- [ ] Fundamentals
- [ ] Selectors
- [ ] Colors
- [ ] Backgrounds
- [ ] Gradients
- [ ] Typography
- [ ] Box Model
- [ ] Border & Outline
- [ ] Display & Positioning
- [ ] Overlay Techniques
- [ ] Overflow & Visibility
- [ ] Flexbox
- [ ] Alignment
- [ ] CSS Grid
- [ ] Tables & Lists
- [ ] Images
- [ ] Filters & Shadows
- [ ] Transitions
- [ ] 2D / 3D Transforms
- [ ] Animations
- [ ] Pseudo-Classes & Pseudo-Elements
- [ ] CSS Variables
- [ ] Units & Functions
- [ ] Media & Container Queries
- [ ] Logical Properties
- [ ] Accessibility-Related CSS
- [ ] Cascade, Specificity & Layers
- [ ] CSS Nesting
- [ ] Modern CSS Features
- [ ] Responsive Design
- [ ] UI Components
```

**Status:** Topics planned / being documented. This checklist will be updated to reflect actual progress as examples are added to the repository.

---

## 59. How to Use the Repository

```bash
git clone https://github.com/amolpawar24/CSS3.git
cd CSS3
```

Open the HTML file(s) directly in a browser to see the CSS in action, or open the project in a code editor (e.g. VS Code) to read through the source. Editing values and refreshing the browser is the fastest way to build intuition for how each property behaves.

---

## 60. Learning Goals

This repository aims to help learners:

- Understand CSS fundamentals thoroughly, not just superficially
- Master layout systems — Flexbox, Grid, and positioning
- Build responsive, adaptive interfaces
- Understand modern CSS features as they gain browser support
- Create animations, transitions, and visual effects confidently
- Build reusable, maintainable components
- Improve overall frontend development skills
- Prepare for CSS and frontend technical interviews
- Practice through concrete, working examples rather than theory alone

---

## 61. Author

**Amol Pawar**
Frontend Developer | React.js Developer | MERN Stack Developer

This repository is part of my ongoing web development learning and documentation journey.

- GitHub: [@amolpawar24](https://github.com/amolpawar24)

---

## 62. Future Improvements

- Organize examples into the planned topic-based folder structure
- Add more real-world CSS examples beyond isolated property demos
- Expand the UI component library with working, documented examples
- Add more animation and effect examples
- Add more responsive layout examples
- Include small CSS challenges/exercises
- Add mini-projects that combine multiple concepts
- Continue expanding coverage of advanced and modern CSS
