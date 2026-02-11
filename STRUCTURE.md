# Project Structure

This document outlines the directory structure and organization of the ionoi-sites project.

## Directory Layout

```
ionoi-sites/
├── public/                 # Static assets (images, fonts, icons)
│   ├── templates/         # Template preview images
│   └── assets/            # Shared static resources
│
├── src/                   # Source code
│   ├── components/        # Reusable React components
│   │   ├── builder/      # Drag-and-drop builder components
│   │   ├── editor/       # Content editing components
│   │   ├── templates/    # Template-specific components
│   │   └── ui/           # Generic UI components
│   │
│   ├── templates/         # Business template definitions
│   │   ├── coffee-shop/
│   │   ├── restaurant/
│   │   ├── bike-shop/
│   │   ├── retail/
│   │   └── service/
│   │
│   ├── lib/              # Utility functions and helpers
│   │   ├── api/         # API client for ionoi-such
│   │   ├── builders/    # Site builder logic
│   │   └── utils/       # General utilities
│   │
│   ├── styles/           # Global styles and themes
│   │   ├── globals.css
│   │   ├── themes/
│   │   └── variables/
│   │
│   ├── pages/            # Application pages/routes
│   ├── hooks/            # Custom React hooks
│   ├── context/          # React context providers
│   └── types/            # TypeScript type definitions
│
├── docs/                 # Documentation
├── tests/                # Test suites
└── scripts/              # Build and deployment scripts
```

## Component Organization

### Builder Components (`src/components/builder/`)
- Drag-and-drop interface
- Component palette
- Layout grid system
- Preview renderer

### Template Components (`src/components/templates/`)
- Menu systems
- Product catalogs
- Service listings
- Contact forms
- Gallery layouts

### UI Components (`src/components/ui/`)
- Buttons, inputs, modals
- Navigation elements
- Cards and containers
- Loading states

## Template Structure

Each template in `src/templates/` follows this pattern:

```
template-name/
├── index.tsx              # Template entry point
├── config.json            # Template metadata
├── components/            # Template-specific components
├── styles/               # Template-specific styles
└── preview.png           # Template preview image
```

## Naming Conventions

- **Components**: PascalCase (e.g., `SiteBuilder.tsx`)
- **Utilities**: camelCase (e.g., `formatCurrency.ts`)
- **Styles**: kebab-case (e.g., `button-primary.css`)
- **Constants**: UPPER_SNAKE_CASE (e.g., `API_BASE_URL`)

## Module Resolution

Use path aliases for cleaner imports:

```typescript
import { Button } from '@/components/ui/Button'
import { useSiteBuilder } from '@/hooks/useSiteBuilder'
import { TemplateConfig } from '@/types/template'
```

## State Management

- Local component state: `useState`
- Cross-component state: React Context
- Server state: React Query or SWR
- Form state: React Hook Form

## Styling Approach

TBD - Options under consideration:
- Tailwind CSS (utility-first)
- CSS Modules (scoped styles)
- Styled Components (CSS-in-JS)
- Combination approach

## Integration Points

### ionoi-such Payment Integration

Location: `src/lib/api/ionoi-such.ts`

Handles:
- Payment page generation
- QR code creation
- Transaction monitoring
- Crypto wallet connections

### Deployment Pipeline

Location: `scripts/deploy/`

Handles:
- Site build process
- Domain configuration
- SSL certificate provisioning
- CDN distribution

---

*This structure will evolve as the project develops. Keep this document updated with architectural changes.*