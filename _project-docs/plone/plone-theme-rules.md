
# Theme Rules for Volto Frontend

This document outlines the color palette, styles, and conventions for a consistent theme in the Volto React frontend of the Educational Content Platform. It builds on Semantic UI React (core design system) with customizations via LESS/CSS Modules, as per the tech stack. Rules ensure accessibility (e.g., contrast ratios), responsiveness, and consistency across features (e.g., standards tagging, dashboard). Use Volto's theme engine for overrides; inherit from light theme where applicable.

## Color Palette
- **Primary Color**: #007eb6 (Main actions, buttons, headers; e.g., login/submit).
- **Secondary Color**: #40a6d1 (Accents, links, secondary buttons; e.g., search filters).
- **Success Green**: #21ba45 (Positive feedback, e.g., successful sync).
- **Warning Yellow**: #f1c40f (Alerts, e.g., draft state).
- **Error Red**: #db2828 (Errors, e.g., permission denied).
- **Neutral Gray**: #767676 (Text, borders; light: #f8f8f8; dark: #1b1c1d).
- **Background**: #ffffff (Default; dark mode: #1b1c1d if implemented).
- **Best Practices**: Ensure WCAG contrast (e.g., text on primary ≥4.5:1); use variables in LESS for easy overrides.
- **Pitfalls**: Avoid low-contrast combos; test on different devices.

## Typography
- **Font Family**: 'Source Sans Pro', sans-serif (Semantic UI default; fallback to system fonts).
- **Sizes**: 
  - Headings: H1 2.5rem, H2 2rem, H3 1.5rem (responsive scaling via em/rem).
  - Body: 1rem (16px base).
  - Small: 0.875rem (captions, metadata).
- **Styles**: Bold for emphasis; italic for quotes; line-height 1.5 for readability.
- **Best Practices**: Use rem for scalability; support RTL flipping.
- **Pitfalls**: Fixed px sizes breaking responsiveness; insufficient line spacing on mobile.

## Spacing and Layout
- **Grid System**: Semantic UI Grid (12-column responsive).
- **Margins/Padding**: 1rem base (scale: 0.5rem small, 2rem large).
- **Borders**: 1px solid #ddd (radius: 4px for cards/buttons).
- **Best Practices**: Use flexbox in Volto components for alignment; media queries for breakpoints (mobile <768px, tablet 768-992px, desktop >992px).
- **Pitfalls**: Inconsistent spacing causing crowded UIs; ignoring Volto's block wrappers.

## Components and Styles
- **Buttons**: Primary: bg #007eb6, text white; hover: lighten 10%.
- **Cards/Blocks**: White bg, shadow subtle; use Volto blocks for composition.
- **Forms**: Labels bold, inputs bordered; validation: green/red borders.
- **Best Practices**: Extend Semantic UI classes; use CSS Modules for scoping.
- **Pitfalls**: Overriding global styles breaking consistency; not testing dark mode if added.

## Accessibility and Responsiveness
- Ensure ARIA attributes; high contrast modes.
- Mobile: Stack elements vertically; touch-friendly targets (≥48px).

Apply these rules to all new features for consistency, testing with Volto tools. 