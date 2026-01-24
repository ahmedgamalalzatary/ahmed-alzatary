# AGENTS.md - Shopify Theme Development

## Build/Test Commands
- **Local dev:** `shopify theme dev` (requires Shopify CLI)
- **Push theme:** `shopify theme push`
- **Check theme:** `shopify theme check` (linting/validation)

## Architecture
- **Shopify Theme 2.0** with JSON templates and section-based architecture
- `layout/` - Base layouts (theme.liquid, password.liquid)
- `sections/` - Reusable section components (.liquid)
- `snippets/` - Smaller reusable partials
- `assets/` - JS/CSS files (uses Web Components with `Component` base class)
- `templates/` - JSON templates for page types
- `config/` - Theme settings schema
- `locales/` - i18n translations

## Code Style
- **JavaScript:** Vanilla JS only (NO jQuery), use Web Components extending `Component` class
- **CSS:** CSS custom properties, BEM-like naming, mobile-first responsive
- **Liquid:** Use `{% liquid %}` for multi-line logic, snake_case for variables
- **Sections:** Include schema at bottom with settings, blocks, and presets
- **Colors:** Yellow #FFF544, Black #000000, Blue #0D499F, Red #B20F36, Gray #AFAFB7
- **Font:** "Jost" for custom sections
- **Breakpoints:** Mobile < 749px, Desktop >= 990px
