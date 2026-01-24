# Horizon Theme (Customized)

> **Theme:** Horizon v3.2.1 by Shopify  
> **Repository:** ahmedgamalalzatary/ahmed-alzatary  

A customized Shopify Theme 2.0 based on Horizon, featuring section-based architecture, Web Components, and custom promotional sections.

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/ahmedgamalalzatary/ahmed-alzatary.git
cd ahmed-alzatary

# Start local development
shopify theme dev

# Push to Shopify store
shopify theme push

# Validate theme
shopify theme check
```

### Prerequisites
- [Shopify CLI](https://shopify.dev/docs/themes/tools/cli)
- Shopify Partner account or development store

---

## 📁 Project Structure

```
├── assets/              # 70+ JS/CSS files
│   ├── component.js     # Base Component class for Web Components
│   ├── gift-guide.css   # Custom Gift Guide styles
│   ├── products-guide.css
│   └── ...
├── blocks/              # 90+ block components
├── config/
│   ├── settings_data.json
│   └── settings_schema.json
├── layout/
│   ├── theme.liquid     # Main layout
│   └── password.liquid  # Password page layout
├── locales/             # 25+ languages supported
├── sections/            # 40+ section components
│   ├── gift-guide.liquid      # Custom promotional banner
│   ├── products-guide.liquid  # Product grid with hotspots
│   ├── hero.liquid
│   ├── carousel.liquid
│   └── ...
├── snippets/            # 90+ reusable partials
└── templates/           # JSON page templates
    ├── index.json
    ├── product.json
    ├── collection.json
    └── ...
```

---

## 🎨 Custom Sections

### Gift Guide Banner (`sections/gift-guide.liquid`)
Hero banner with promotional content featuring:
- Logo and tagline header bar
- Main heading with description
- Animated CTA buttons
- Mobile responsive hamburger menu
- Footer sustainability message

### Products Guide Grid (`sections/products-guide.liquid`)
Product showcase grid featuring:
- 6 configurable product blocks
- Circular "+" hotspot overlays
- Popup product details on click
- Responsive: 3 columns (desktop) / 1 column (mobile)
- Auto-hides empty product blocks

---

## 🛠️ Technical Architecture

### Web Components
All interactive elements extend the `Component` base class:

```javascript
// assets/component.js
export class Component extends DeclarativeShadowElement {
  refs = {};           // Child element references via ref=""
  requiredRefs;        // Validation for required refs
  // Handles declarative shadow DOM hydration
}
```

### Key JavaScript Modules

| File | Purpose |
|------|---------|
| `component.js` | Base class for all Web Components |
| `cart-drawer.js` | Slide-out cart functionality |
| `product-form.js` | Add to cart handling |
| `variant-picker.js` | Product variant selection |
| `predictive-search.js` | Live search suggestions |
| `facets.js` | Collection filtering |
| `slideshow.js` | Image carousels |
| `media-gallery.js` | Product media handling |
| `quick-add.js` | Quick add to cart modals |

---

## 🌐 Internationalization

Supported languages (25+):
- **Primary:** English (en.default.json)
- **European:** German, French, Spanish, Italian, Dutch, Portuguese, Swedish, Danish, Norwegian, Finnish, Polish, Czech, Greek, Hungarian, Romanian, Croatian, Slovak, Slovenian, Lithuanian, Bulgarian
- **Asian:** Japanese, Korean, Chinese (Simplified/Traditional), Thai, Vietnamese, Indonesian
- **Other:** Turkish, Russian, Brazilian Portuguese

---

## 🎯 Design System

### Brand Colors
| Color | Hex | CSS Variable |
|-------|-----|--------------|
| Yellow | `#FFF544` | Primary accent |
| Black | `#000000` | Text, backgrounds |
| Blue | `#0D499F` / `#000F9F` | Links, CTAs |
| Red | `#B20F36` | Alerts, errors |
| Gray | `#AFAFB7` | Secondary text |

### Typography
- **Primary Font:** Jost
- Font loaded via `snippets/fonts.liquid`

### Breakpoints
| Breakpoint | Width | Usage |
|------------|-------|-------|
| Mobile | < 749px | Single column layouts |
| Tablet | 750px - 989px | Transitional |
| Desktop | ≥ 990px | Multi-column layouts |

---

## 📄 Page Templates

| Template | Purpose |
|----------|---------|
| `index.json` | Homepage with hero, collections, products |
| `product.json` | Product detail pages |
| `collection.json` | Collection listing pages |
| `cart.json` | Shopping cart |
| `blog.json` | Blog listing |
| `article.json` | Blog post detail |
| `page.json` | Static pages |
| `page.contact.json` | Contact page with form |
| `search.json` | Search results |
| `404.json` | Error page |

---

## ⚙️ Theme Settings

Configurable via `config/settings_schema.json`:
- **Logo & Favicon** - Desktop/mobile sizing, inverse logo
- **Colors** - Full color scheme customization with alpha support
- **Typography** - Font families and sizing
- **Layout** - Page width, card hover effects
- **Animations** - View transitions, page transitions

---

## 📋 Development Guidelines

### JavaScript
- ✅ Vanilla JS only (NO jQuery)
- ✅ Web Components extending `Component` class
- ✅ Event delegation pattern
- ✅ Declarative shadow DOM support

### CSS
- ✅ CSS custom properties
- ✅ BEM-like naming
- ✅ Mobile-first responsive
- ✅ Max-width: 1440px container

### Liquid
- ✅ Use `{% liquid %}` for multi-line logic
- ✅ `snake_case` variable naming
- ✅ Section schema at bottom
- ✅ Comment blocks for complex logic

---

## 🔗 Resources

- [Shopify Theme Docs](https://shopify.dev/docs/themes)
- [Horizon Theme Support](https://support.shopify.com/)
- [Liquid Reference](https://shopify.dev/docs/api/liquid)

---

## 👥 Contributing

1. Create feature branch from `development`
2. Follow code standards above
3. Run `shopify theme check` before committing
4. Submit PR to `development` branch

---

**Built on Horizon v3.2.1** · Customized for ECOM
