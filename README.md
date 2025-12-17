Here is the comprehensive `README.md` file, strictly generated based on the HTML and CSS code provided.

---

# 🌐 Meet Landing Page

A high-fidelity, responsive landing page for "Meet," a group chat collaboration tool. This solution prioritizes a **Mobile-First** architecture, utilizing advanced CSS layout techniques such as CSS Grid, Flexbox, and mathematical geometry for precise layout overlaps.

## 🔗 Links

- **Live Site URL:** [Add your live site URL here]
- **Solution URL:** [Add your solution URL here]

## 💡 Overview

### The Challenge

The challenge was to build a responsive landing page that adapts to three distinct viewports (Mobile, Tablet, Desktop) while maintaining specific art direction for typography and layout overlaps.

### Key Features

- **Fluid Typography:** Uses `clamp()` functions for headings and body text to ensure smooth scaling between viewports.
- **Geometric Overlaps:** The timeline indicators ("01", "02") visually overlap sections using precise `calc()` mathematics.
- **Art-Directed Layouts:**
- **Mobile:** Stacked layout with a zoomed-in hero image (`115%` width).
- **Tablet:** Specific text wrapping and image expansion logic.
- **Desktop:** A "Holy Grail" 3-column split for the Hero section.

- **Controlled Typography:** Text elements utilize specific `max-width` (ch/rem) constraints to force line breaks exactly as per the design requirements.

## 🛠️ Technical Architecture

### Tech Stack

- **HTML5:** Semantic markup (e.g., `<main>`, `<section>`, `<header>`, `<footer>`).
- **CSS3:** Custom Properties (Variables), Flexbox, CSS Grid.
- **Fonts:** Google Fonts ("Red Hat Display").

### Project Structure

The CSS is organized into distinct logical sections:

1. **Setup & Variables:** Definition of colors, spacing, and math constants.
2. **Reset:** Standard box-sizing and margin resets.
3. **Utilities:** Button styles and Divider components.
4. **Layout Sections:** Header, Hero, Features, and Footer styles, grouped by component and viewport.

## 🎨 Design System

### Colors & Variables

The project uses CSS Custom Properties for maintainability.

| Token                    | Hex Value | Usage                      |
| ------------------------ | --------- | -------------------------- |
| `--color-text-primary`   | `#28283d` | Headings                   |
| `--color-text-secondary` | `#87879d` | Body Text                  |
| `--color-brand-cyan`     | `#4d96a9` | Primary Buttons            |
| `--color-brand-purple`   | `#855fb1` | Secondary Buttons / Footer |
| `--color-white`          | `#fafafa` | Text on dark backgrounds   |

### Typography

Typography is handled fluidly using `clamp()` to avoid "jumping" font sizes at breakpoints.

```css
--font-h1: clamp(2.5rem, 5vw + 1rem, 4rem);
--font-h2: clamp(2rem, 4vw + 1rem, 2.5rem);
--font-body: clamp(1rem, 0.5vw + 0.9rem, 1.125rem);
```

## 🧠 Engineering Highlights

### 1. Mathematical Footer Overlap

To ensure the "02" timeline circle sits exactly halfway on top of the footer background, a calculation is used. This allows the layout to remain perfect even if the `--circle-size` variable is changed.

```css
:root {
  --circle-size: 3.5rem;
}

.site-footer {
  /* Pulls the footer up by exactly half the circle's height */
  margin-top: calc(var(--circle-size) / -2);

  /* Adds padding to compensate for the pull-up */
  padding-top: calc(4rem + (var(--circle-size) / 2));
}
```

### 2. The "Zoomed" Mobile Hero

On mobile devices, the hero image is designed to bleed slightly off the edges or appear "zoomed in." This is achieved by setting the width to `115%`.

```css
.hero__visual--main {
  width: 115%;
  max-width: 28rem;
}

/* Prevents the 115% width from causing a horizontal scrollbar */
body {
  overflow-x: hidden;
}
```

### 3. Precision Text Wrapping

To achieve the exact line breaks specified in the design without using `<br>` tags (which can hinder accessibility), `max-width` constraints are applied to text blocks.

- **Footer Title:** Constrained to `15ch` (15 characters) to force "Experience more" and "together" onto two lines.
- **Tablet Override:** On tablet, this constraint is removed (`max-width: unset`) to allow the title to span a single line.

## ♿ Accessibility

- **ARIA Attributes:** Decorative elements like the timeline dividers use `aria-hidden="true"` so they are ignored by screen readers.
- **Focus States:** Buttons include `:focus-visible` styles (`outline: 3px solid`) for keyboard navigation.
- **Semantic HTML:** Usage of proper landmark tags (`<main>`, `<section>`, `<footer>`) ensures a navigable document structure.

## 👤 Author

**Frontend Mentor Student**

- **Focus:** Responsive Design, CSS Architecture, Accessibility.
