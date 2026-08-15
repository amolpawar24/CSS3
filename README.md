# CSS3

A personal, hands-on repository for learning and practicing CSS3 — from core fundamentals to modern layout and styling techniques.

This repository is part of my web development learning journey and serves as a reference I can revisit while building real projects.

---

## Table of Contents

- [About This Repository](#about-this-repository)
- [Topics Covered](#topics-covered)
- [Detailed Topic Categories](#detailed-topic-categories)
  - [1. Fundamentals](#1-fundamentals)
  - [2. Selectors](#2-selectors)
  - [3. Colors and Backgrounds](#3-colors-and-backgrounds)
  - [4. Typography and Text](#4-typography-and-text)
  - [5. Box Model](#5-box-model)
  - [6. Display](#6-display)
  - [7. Positioning](#7-positioning)
  - [8. Overflow](#8-overflow)
  - [9. Flexbox](#9-flexbox)
  - [10. CSS Grid](#10-css-grid)
  - [11. Responsive Design](#11-responsive-design)
  - [12. Transitions](#12-transitions)
  - [13. 2D Transforms](#13-2d-transforms)
  - [14. 3D Transforms](#14-3d-transforms)
  - [15. Animations](#15-animations)
  - [16. Pseudo-Classes](#16-pseudo-classes)
  - [17. Pseudo-Elements](#17-pseudo-elements)
  - [18. CSS Variables](#18-css-variables)
  - [19. Specificity and Cascade](#19-specificity-and-cascade)
  - [20. CSS Units](#20-css-units)
  - [21. CSS Functions](#21-css-functions)
  - [22. Gradients](#22-gradients)
  - [23. Borders and Shadows](#23-borders-and-shadows)
  - [24. Images and Media](#24-images-and-media)
  - [25. Cursor and Visibility](#25-cursor-and-visibility)
  - [26. Advanced Modern CSS](#26-advanced-modern-css)
- [Repository Structure](#repository-structure)
- [How to Use](#how-to-use)
- [Learning Goals](#learning-goals)
- [Technologies Used](#technologies-used)
- [Learning Progress](#learning-progress)
- [Future Improvements](#future-improvements)
- [Author](#author)
- [Support](#support)

---

## About This Repository

This repo is where I document CSS3 concepts as I learn and practice them — through short explanations and working code examples. The goal isn't just to collect syntax, but to build a habit of writing and testing CSS until it becomes second nature.

It's organized as a growing reference, so topics are added and expanded incrementally rather than all at once.

---

## Topics Covered

| Category | Examples |
|---|---|
| Fundamentals | Syntax, ways to apply CSS, comments |
| Selectors | Basic, grouping, combinator, attribute, and advanced selectors |
| Colors & Backgrounds | Color models, background properties |
| Typography | Fonts, text spacing, text effects |
| Box Model | Content, padding, border, margin, sizing |
| Display & Positioning | Display types, position schemes, z-index |
| Overflow | Handling content overflow |
| Flexbox | Flex container and item properties |
| CSS Grid | Grid container and item properties |
| Responsive Design | Media queries, mobile-first design |
| Transitions & Animations | Smooth state changes and keyframe animations |
| Transforms | 2D and 3D transformations |
| Pseudo-classes & Pseudo-elements | Interactive and generated content styling |
| CSS Variables | Custom properties and reusable values |
| Specificity & Cascade | How CSS rules are resolved |
| Units & Functions | Length units, `calc()`, `clamp()`, etc. |
| Gradients | Linear, radial, conic gradients |
| Advanced Modern CSS | Nesting, container queries, `:has()`, logical properties |

> Note: Not every property listed above may be fully covered yet. This repository is a work in progress, and coverage expands as I add more examples.

---

## Detailed Topic Categories

### 1. Fundamentals
Introduction to CSS, CSS syntax rules, and the three ways to apply styles:

- **Inline CSS** — applied directly on an HTML element via the `style` attribute
- **Internal CSS** — defined inside a `<style>` block in the HTML document
- **External CSS** — defined in a separate `.css` file and linked via `<link>`

```css
/* This is a CSS comment */
selector {
  property: value;
}
```

### 2. Selectors
Covers how to target HTML elements for styling:

| Selector Type | Example |
|---|---|
| Universal | `* { }` |
| Element | `p { }` |
| Class | `.card { }` |
| ID | `#header { }` |
| Grouping | `h1, h2, h3 { }` |
| Descendant | `div p { }` |
| Child | `div > p { }` |
| Sibling | `h1 + p`, `h1 ~ p` |
| Attribute | `input[type="text"] { }` |

### 3. Colors and Backgrounds
Color value formats (HEX, RGB/RGBA, HSL/HSLA) and background properties such as `background-color`, `background-image`, `background-repeat`, `background-position`, `background-size`, `background-attachment`, and `background-clip`.

### 4. Typography and Text
Text and font styling properties including `font-family`, `font-size`, `font-weight`, `font-style`, `line-height`, `letter-spacing`, `word-spacing`, `text-align`, `text-decoration`, `text-transform`, `text-shadow`, `text-overflow`, `white-space`, `word-break`, and `overflow-wrap`.

### 5. Box Model
Every HTML element is a rectangular box made up of:

```
┌───────────────────────────────┐
│            margin              │
│   ┌─────────────────────────┐  │
│   │         border           │  │
│   │   ┌─────────────────┐   │  │
│   │   │     padding      │   │  │
│   │   │  ┌───────────┐   │   │  │
│   │   │  │  content  │   │   │  │
│   │   │  └───────────┘   │   │  │
│   │   └─────────────────┘   │  │
│   └─────────────────────────┘  │
└───────────────────────────────┘
```

Includes `width`, `height`, `min-width`, `max-width`, `min-height`, `max-height`, and `box-sizing` (`content-box` vs `border-box`).

### 6. Display
Common display values: `block`, `inline`, `inline-block`, `none`, `flex`, `grid`, and other relevant display types, along with how each affects layout flow.

### 7. Positioning
Position schemes: `static`, `relative`, `absolute`, `fixed`, and `sticky`, along with the offset properties `top`, `right`, `bottom`, `left`, and stacking order via `z-index`.

### 8. Overflow
Managing content that exceeds its container using `overflow`, `overflow-x`, `overflow-y`, and their values `visible`, `hidden`, `scroll`, and `auto`.

### 9. Flexbox
One-dimensional layout system.

**Container properties:** `display: flex`, `flex-direction`, `flex-wrap`, `flex-flow`, `justify-content`, `align-items`, `align-content`, `gap`, `row-gap`, `column-gap`

**Item properties:** `order`, `flex-grow`, `flex-shrink`, `flex-basis`, `flex`, `align-self`

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
}
```

### 10. CSS Grid
Two-dimensional layout system covering `grid-template-columns`, `grid-template-rows`, `grid-template-areas`, `grid-template`, `grid-auto-columns`, `grid-auto-rows`, `grid-auto-flow`, `grid-column` (and `-start`/`-end`), `grid-row` (and `-start`/`-end`), `grid-area`, `gap`, alignment properties (`justify-items`, `align-items`, `place-items`, `justify-content`, `align-content`, `place-content`, `justify-self`, `align-self`, `place-self`).

**Flexbox vs Grid:** Flexbox is best suited for one-dimensional layouts (a single row or column), while Grid is designed for two-dimensional layouts (rows and columns together).

### 11. Responsive Design
Responsive Web Design principles, mobile-first vs desktop-first approaches, flexible layouts, responsive images, breakpoints, media queries, and applying responsive techniques to Flexbox and Grid layouts.

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

### 12. Transitions
Smooth animation between property states using `transition-property`, `transition-duration`, `transition-timing-function`, `transition-delay`, and the `transition` shorthand.

```css
.button {
  background-color: royalblue;
  transition: background-color 0.3s ease-in-out;
}

.button:hover {
  background-color: darkblue;
}
```

### 13. 2D Transforms
`translate()`, `translateX()`, `translateY()`, `scale()`, `scaleX()`, `scaleY()`, `rotate()`, `skew()`, `skewX()`, `skewY()`, and `matrix()`.

### 14. 3D Transforms
`translateZ()`, `translate3d()`, `rotateX()`, `rotateY()`, `rotateZ()`, `rotate3d()`, `scale3d()`, `perspective`, `transform-style`, and `backface-visibility`.

### 15. Animations
Keyframe-based animation using `@keyframes`, `animation-name`, `animation-duration`, `animation-timing-function`, `animation-delay`, `animation-iteration-count`, `animation-direction`, `animation-fill-mode`, `animation-play-state`, and the `animation` shorthand.

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.element {
  animation: fadeIn 1s ease-in-out;
}
```

### 16. Pseudo-Classes
`:hover`, `:active`, `:focus`, `:visited`, `:checked`, `:disabled`, `:enabled`, `:first-child`, `:last-child`, `:nth-child()`, `:nth-of-type()`, `:not()`, `:is()`, `:where()`, `:has()`, `:focus-within`, and `:focus-visible`.

### 17. Pseudo-Elements
Commonly used pseudo-elements such as `::before`, `::after`, `::first-line`, `::first-letter`, `::selection`, `::placeholder`, and `::marker`.

### 18. CSS Variables
Custom properties, defining reusable values on `:root`, referencing them with `var()`, and providing fallback values.

```css
:root {
  --primary-color: #2563eb;
}

.button {
  background-color: var(--primary-color, #000);
}
```

### 19. Specificity and Cascade
How conflicting CSS rules are resolved: the cascade, specificity calculation, inheritance, and the specificity order — inline styles, IDs, classes/attributes/pseudo-classes, elements/pseudo-elements — plus the effect of `!important`.

### 20. CSS Units
Absolute and relative units: `px`, `%`, `em`, `rem`, `vw`, `vh`, `vmin`, `vmax`, `ch`, `ex`, and modern viewport units like `dvh`, `svh`, and `lvh`.

### 21. CSS Functions
`calc()`, `min()`, `max()`, `clamp()`, `var()`, `url()`, `repeat()`, and `minmax()`.

### 22. Gradients
`linear-gradient()`, `radial-gradient()`, and `conic-gradient()`.

### 23. Borders and Shadows
`border`, `border-width`, `border-style`, `border-color`, `border-radius`, `box-shadow`, and `text-shadow`.

### 24. Images and Media
`object-fit`, `object-position`, `aspect-ratio`, and background-related image properties (`background-image`, `background-size`, `background-position`, `background-repeat`).

### 25. Cursor and Visibility
`cursor`, `opacity`, `visibility`, and `display: none`.

### 26. Advanced Modern CSS
Newer CSS features including CSS Nesting, Container Queries, Logical Properties, modern selectors (`:is()`, `:where()`, `:has()`), `aspect-ratio`, `clamp()`, CSS Custom Properties, `prefers-color-scheme`, and `prefers-reduced-motion`.

---

## Repository Structure

**Current structure:**

```
CSS3/
├── CSS3.html   # Practice and example code
└── README.md   # Repository documentation
```

**Planned structure** (as the repository grows, examples will be organized into topic-based folders similar to this):

```
CSS3/
├── FUNDAMENTALS/
├── SELECTORS/
├── COLORS/
├── BACKGROUNDS/
├── TYPOGRAPHY/
├── BOX-MODEL/
├── DISPLAY/
├── POSITION/
├── OVERFLOW/
├── FLEXBOX/
├── GRID/
├── RESPONSIVE-DESIGN/
├── MEDIA-QUERIES/
├── TRANSITIONS/
├── TRANSFORMS/
│   ├── 2D/
│   └── 3D/
├── ANIMATIONS/
├── PSEUDO-CLASSES/
├── PSEUDO-ELEMENTS/
├── CSS-VARIABLES/
├── SPECIFICITY/
├── UNITS/
├── FUNCTIONS/
├── GRADIENTS/
└── ADVANCED-CSS/
```

> This is a target structure, not the current state of the repository. Folders will be added as topics are practiced and documented in more depth.

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/amolpawar24/CSS3.git
   ```
2. Open the HTML file(s) in a browser to see the CSS in action.
3. Open the project in a code editor (e.g., VS Code) to read through the CSS and experiment with the properties.
4. Modify values and reload the browser to see how each property affects the output — this is the fastest way to build intuition for CSS behavior.

---

## Learning Goals

- Build a strong, practical understanding of CSS3 from the ground up
- Practice layout systems (Flexbox and Grid) until they feel intuitive
- Get comfortable with responsive design and mobile-first thinking
- Explore modern CSS features as they become widely supported
- Maintain a personal reference I can return to while building real projects

---

## Technologies Used

- **HTML5** — markup structure for examples
- **CSS3** — core focus of this repository

---

## Learning Progress

This repository reflects an ongoing learning process. Topics are added and refined over time rather than completed all at once — think of it as a living document rather than a finished course.

---

## Future Improvements

- Split examples into topic-based folders as outlined in the planned structure
- Add more real-world, project-style examples alongside isolated property demos
- Expand coverage of modern CSS features (Container Queries, Nesting, Logical Properties)
- Add a live preview/demo link for select examples

---

## Author

**Amol Pawar**
Frontend Developer | React.js Developer | MERN Stack Developer

This repository is part of my ongoing web development learning and documentation journey.

- GitHub: [@amolpawar24](https://github.com/amolpawar24)

---

## Support

If you find this repository useful for your own CSS learning, feel free to star it or share feedback via an issue.