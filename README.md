# TrailNest: Responsive Web Design (Week 2)

A responsive, mobile-first website for a fictional guided-hiking company, built with **HTML and CSS only** for the Yuva Intern Week 2 task: *Implementation of Responsive Web Design*. The layout adapts cleanly to phones, tablets and desktops.

## Project Structure

```
project-week2/
├── index.html        # Semantic page structure
├── styles.css        # Mobile-first, responsive stylesheet
├── images/           # Lightweight SVG illustrations (scale without quality loss)
├── screenshots/      # Captures at 375px, 768px and 1280px
└── README.md         # Documentation (this file)
```

## How to Run

Open `index.html` in any modern browser, then resize the window or use DevTools device mode (F12, then Ctrl+Shift+M) to see the layout adapt.

## Methods Used

1. **Mobile-first approach:** base styles target small screens; `min-width` media queries add complexity as space grows.
2. **Flexible grids:** `repeat(auto-fit, minmax(min(100%, 260px), 1fr))` lets cards and quotes reflow into 1, 2 or 3 columns without extra breakpoints.
3. **Fluid images:** `img { max-width: 100%; height: auto; }`, `aspect-ratio` and `object-fit: cover` keep images proportional and prevent layout shift (width/height attributes are also set).
4. **Art direction:** the `<picture>` element serves a wide hero image on mobile and a squarer crop from 900px up.
5. **Fluid typography and spacing:** `clamp()` scales headings, body text, gaps and section padding smoothly between screen sizes.
6. **CSS custom properties:** colours, radius, spacing and font sizes are defined once in `:root`.
7. **Preference and capability queries:** `hover: hover`, `prefers-reduced-motion`, `orientation` with `max-height`, and `print`.
8. **Accessibility:** skip link, landmarks, labelled form field, alt text and visible focus styles.

## Breakpoints and Layout Adjustments

| Viewport | Breakpoint | What changes |
|----------|-----------|--------------|
| Phone (below 600px) | base styles | Single column, hamburger menu, hero image above text, stats in 2 columns, stacked form and footer |
| Large phone / small tablet | `min-width: 600px` | Signup form becomes one row; footer in 2 columns |
| Tablet | `min-width: 768px` | Hamburger replaced by horizontal navigation; stats in 4 columns; cards auto-fit to 2 to 3 columns |
| Small desktop | `min-width: 900px` | Two-column hero and "Why hike with us" section; hero uses square image; 4-column footer |
| Large desktop | `min-width: 1200px` | Wider side margins and larger hero spacing; content capped at 1140px |

## Examples of How the Design Adjusts

| Mobile (375px) | Tablet (768px) | Desktop (1280px) |
|:---:|:---:|:---:|
| ![Mobile](screenshots/mobile-375.png) | ![Tablet](screenshots/tablet-768.png) | ![Desktop](screenshots/desktop-1280.png) |

## Testing

- Tested in Chromium at 375px, 768px and 1280px viewports and by resizing continuously between them.
- Verified that there is no horizontal scrolling at any of these widths.
- Checked the hamburger menu, form fields and image scaling.

## Challenges and Solutions

| Challenge | Solution |
|-----------|----------|
| Too many breakpoints made CSS long | Used `auto-fit` + `minmax()` grids and `clamp()` so many elements adapt without media queries |
| Images stretching or distorting | `max-width: 100%`, `height: auto`, `aspect-ratio` and `object-fit: cover` |
| Layout shift while images load | Set `width` and `height` attributes and used `loading="lazy"` below the fold |
| Navigation on small screens | CSS-only hamburger menu using the `:checked` selector, replaced by a normal menu at 768px |
| Hero image too wide on desktop | `<picture>` with a different source from 900px up |

## Technologies

HTML5, CSS3 (Grid, Flexbox, custom properties, `clamp()`, media queries, `aspect-ratio`)

## Author

**Gaurav Prakash Gawade**, Yuva Intern, Week 2 Task
