# Accessibility

MkDocs Material provides accessibility-friendly defaults. This page summarizes the configuration and best practices used in this POC.

## Configuration

### Theme Features

The following Material theme features improve accessibility:

- **Keyboard navigation** — All interactive elements are keyboard-accessible
- **Skip links** — "Skip to content" for screen reader users
- **Semantic structure** — Proper heading hierarchy and landmark roles
- **Color contrast** — Material palette meets WCAG contrast guidelines

### Color Scheme

The POC uses the **slate** (dark) and **default** (light) schemes. Both provide sufficient contrast. The theme toggle allows users to choose their preference.

## Best Practices

1. **Heading hierarchy** — Use H1 → H2 → H3 in order; don’t skip levels.
2. **Link text** — Prefer descriptive link text (e.g., "Getting Started guide" instead of "click here").
3. **Images** — Provide `alt` text for meaningful images.
4. **Tables** — Use header cells (`| Header |`) for table headers.
5. **Code blocks** — Use language tags for syntax highlighting and better context.

## Linkable Headers

All headers in the documentation generate anchor links. Hover over a heading to see the link icon and copy the URL. For example:

- [Configuration](#configuration) — Links to the Configuration section above
- [Best Practices](#best-practices) — Links to the Best Practices section

## Responsive Design

The Material theme is responsive and adapts to different screen sizes:

- **Desktop** — Full navigation, search, and sidebar
- **Tablet** — Collapsible navigation
- **Mobile** — Optimized layout and touch targets

## Resources

- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
