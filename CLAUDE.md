# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Shopify Theme 2.0** based on the Horizon v3.2.1 theme. It's a pure Shopify theme with no Node.js build process.

## Commands

```bash
shopify theme dev          # Local development server
shopify theme push         # Deploy to Shopify
shopify theme check        # Theme validation/linting
```

## Architecture

### Web Components Pattern
- Base class `Component` in `assets/component.js` extends `DeclarativeShadowElement`
- All interactive components use this pattern: `cart-drawer.js`, `product-form.js`, `variant-picker.js`, etc.
- Uses a ref system for child element references

### Section-Based Structure (Theme 2.0)
- JSON templates in `templates/` reference sections by type
- Sections in `sections/` have schemas at bottom defining customizer settings
- Blocks in `blocks/` are prefixed with `_` and compose larger sections

### Key JavaScript Modules
| File | Purpose |
|------|---------|
| `component.js` | Base Web Component class |
| `cart-drawer.js` | Slide-out cart |
| `product-form.js` | Add to cart handling |
| `variant-picker.js` | Product variant selection |
| `predictive-search.js` | Live search |
| `facets.js` | Collection filtering |

## Code Style

### JavaScript
- Vanilla JS with Web Components (no jQuery)
- Components extend the `Component` base class

### CSS
- CSS custom properties with BEM-like naming
- Mobile-first responsive design

### Liquid
- Use `{% liquid %}` for multi-line logic blocks
- `snake_case` variable naming
- Comments with `{%- comment -%}` blocks

## Design System

**Colors:** Yellow (#FFF544), Black (#000000), Blue (#0D499F), Red (#B20F36), Gray (#AFAFB7)

**Font:** Jost

**Breakpoints:**
- Mobile: < 749px
- Tablet: 750-989px
- Desktop: ≥ 990px

## Custom Sections

Two custom sections were created for this project:
- `sections/gift-guide.liquid` - Hero banner with promotional content
- `sections/products-guide.liquid` - Product grid with circular hotspot overlays
- Template `page.assignment.json` uses these sections
