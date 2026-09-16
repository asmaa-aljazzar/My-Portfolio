# Portfolio CSS File Structure

```text
portfolio/
│
├── index.html
├── project.html
├── style.css
│
├── css/
│   ├── variables.css
│   ├── base.css
│   ├── navbar.css
│   ├── hero.css
│   ├── technologies.css
│   ├── about.css
│   ├── projects.css
│   ├── cards.css
│   ├── contact.css
│   ├── project-details.css
│   ├── footer.css
│   ├── animations.css
│   ├── accessibility.css
│   └── responsive.css
│
└── images/
```

---

## `variables.css`

**What reusable values does my design use?**

Use this file for:

- Colors
- Fonts
- Spacing
- Border radius
- Shadows
- Reusable sizes
- Other CSS custom properties

Example:

```css
:root {
    --primary-color: #6b4f3b;
    --background-color: #f5efe8;
    --text-color: #222;

    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 32px;

    --radius-sm: 8px;
    --radius-md: 16px;
}
```

---

## `base.css`

**What basic rules should apply to the whole website?**

Use this file for:

- CSS reset
- `body` styles
- Default typography
- Default image behavior
- Default links
- Default buttons
- Global box sizing

Example:

```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--background-color);
    color: var(--text-color);
}

img {
    max-width: 100%;
    display: block;
}

a {
    color: inherit;
    text-decoration: none;
}

button,
input,
textarea {
    font: inherit;
}
```

---

## `navbar.css`

**What should the navigation bar look and behave like?**

Use this file for:

- Navbar layout
- Logo/name
- Navigation links
- Link spacing
- Hover states
- Active states
- Navbar-specific positioning

---

## `hero.css`

**What should the first / landing section look like?**

Use this file for:

- Name
- Job title
- Short introduction
- Profile image
- Social icons
- Hero layout
- Hero spacing
- Hero-specific buttons

---

## `technologies.css`

**How should the technologies / skills strip look?**

Use this file for:

- Technology labels
- Skill badges
- Technology layout
- Spacing
- Borders
- Hover effects

---

## `about.css`

**What should the About Me section look like?**

Use this file for:

- About section layout
- Heading
- About text
- Background
- Spacing
- Alignment

---

## `projects.css`

**How should the overall Projects section be arranged?**

Use this file for:

- Projects section layout
- Projects grid
- Section heading
- Section spacing
- GitHub / More Projects button
- Overall project arrangement

Example:

```css
.projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--space-lg);
}
```

---

## `cards.css`

**What should each reusable project card look like?**

Use this file for:

- Project card container
- Project image
- Status
- Tags
- Card borders
- Card spacing
- Card hover effects
- Card links

Example:

```css
.project-card {
    border-radius: var(--radius-md);
    overflow: hidden;
}

.project-card__image {
    width: 100%;
}

.project-card__tags {
    display: flex;
    gap: var(--space-sm);
}
```

---

## `contact.css`

**What should the Contact section and form look like?**

Use this file for:

- Contact section layout
- Form layout
- Labels
- Inputs
- Textarea
- Submit button
- Form spacing
- Focus styles specific to the form

---

## `project-details.css`

**What should an individual project page look like?**

Use this file for:

- Project title
- Main screenshot
- Screenshot gallery
- Technology section
- Description
- How-To section
- More Information section
- GitHub button
- Other Projects button

Use the same file for multiple project pages if they share the same layout.

---

## `footer.css`

**What should the footer look like?**

Use this file for:

- Name
- Social icons
- Copyright
- Footer layout
- Footer spacing
- Footer alignment

---

## `animations.css`

**What reusable animations does the website use?**

Use this file for:

- `@keyframes`
- Fade-in
- Slide-in
- Floating effects
- Reveal animations
- Other reusable animation classes

Example:

```css
@keyframes fade-in {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.fade-in {
    animation: fade-in 0.6s ease;
}
```

> Keep animations that belong only to one component inside that component's CSS file.

---

## `accessibility.css`

**What accessibility-specific styles does the website need?**

Use this file for:

- Visible focus states
- Skip links
- Visually hidden content
- Reduced-motion support
- High-contrast support

Example:

```css
:focus-visible {
    outline: 3px solid currentColor;
    outline-offset: 3px;
}

@media (prefers-reduced-motion: reduce) {
    * {
        animation: none;
        transition: none;
        scroll-behavior: auto;
    }
}
```

---

## `responsive.css`

**What needs to change on different screen sizes?**

Use this file for:

- Mobile media queries
- Tablet media queries
- Desktop adjustments
- Grid changes
- Font-size changes
- Navigation changes
- Spacing changes
- Layout changes

Example:

```css
@media (max-width: 768px) {
    .projects-grid {
        grid-template-columns: 1fr;
    }
}
```

---

## `style.css`

**Which CSS files does the website load?**

This is the main CSS entry file.

It imports all the other CSS files so the HTML only needs one stylesheet link.

Example:

```css
@import url("./css/variables.css");
@import url("./css/base.css");

@import url("./css/navbar.css");
@import url("./css/hero.css");
@import url("./css/technologies.css");
@import url("./css/about.css");

@import url("./css/projects.css");
@import url("./css/cards.css");

@import url("./css/contact.css");
@import url("./css/project-details.css");

@import url("./css/footer.css");

@import url("./css/animations.css");
@import url("./css/accessibility.css");
@import url("./css/responsive.css");
```

Then inside the HTML:

```html
<link rel="stylesheet" href="style.css">
```

---

# Mental Structure

```text
variables
    ↓
Reusable design values

base
    ↓
Global website defaults

sections / components
    ↓
Navbar, Hero, About, Projects, Cards, Contact, etc.

animations
    ↓
Reusable motion effects

accessibility
    ↓
Accessibility-specific styles

responsive
    ↓
Screen-size overrides
```

## Rule of Thumb

- **Global reusable value** → `variables.css`
- **Whole-site default rule** → `base.css`
- **Specific section** → its own section file
- **Reusable component** → component file
- **Reusable animation** → `animations.css`
- **Accessibility-specific styling** → `accessibility.css`
- **Media-query override** → `responsive.css`
