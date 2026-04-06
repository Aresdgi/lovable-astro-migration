# Lovable → Astro migration checklist

Use this when the migration is non-trivial or when you need a systematic audit before editing.

## 1. Confirm the source

- Is the source clearly a Lovable export?
- Is the frontend React + Tailwind + Vite?
- Is there already an Astro target?
- Is the task in-place migration or source-to-target merge?

## 2. Inventory the source surface area

### Routing and pages
- list every route/page
- identify shared wrappers and repeated page sections
- note 404/error/loading/empty states

### Components
- identify reusable presentational components
- identify interactive components
- identify components with mixed static + interactive concerns

### Styling
- Tailwind config/theme
- global CSS
- CSS variables
- custom utilities/components
- font imports and weights
- spacing and breakpoint patterns
- gradients, shadows, overlays, borders, blur, opacity treatments

### Assets
- logos
- icons
- photos/illustrations
- background textures
- videos
- fonts
- favicons and social images

### Behavior
- forms
- stateful widgets
- tabs/accordions/drawers/modals
- carousels/sliders
- filtering/sorting/search
- animations/transitions
- browser-only APIs

### Integration points
- environment variables
- fetch/API calls
- auth hooks
- analytics
- CMS/content dependencies
- third-party widgets

## 3. Extract the visual language

Before rewriting components, identify:

- type scale
- heading/body/button styles
- primary/secondary/accent colors
- button variants
- card patterns
- input and form patterns
- section spacing rhythm
- container widths and grid behavior
- mobile/tablet/desktop breakpoints in practice

If needed, keep a short “do not lose” list for the most distinctive visuals.

## 4. Decide component destination

### Convert to `.astro`
Use for:

- presentational sections
- content-heavy layouts
- static marketing blocks
- wrappers and shells with no runtime state
- repeated structural patterns

### Keep as React islands
Use for:

- components with state/effects
- browser APIs
- forms with live client-side behavior
- highly interactive widgets
- third-party React-bound components

### Split mixed components
If a component combines static layout and small interactive controls:

- move the shell to Astro
- isolate the interactive fragment as a React island
- hydrate the smallest possible surface

## 5. Port the styling layer first

Before deeply refactoring markup:

- migrate Tailwind config/theme tokens
- migrate global CSS and CSS variables
- migrate fonts and asset references
- preserve responsive utilities that control layout

If visual fidelity matters, styling parity is not a cleanup detail. It is core migration work.

## 6. Check Astro-specific architecture

- file-based routing fits the source IA
- layouts are reused instead of copied
- islands use the lightest suitable `client:*` directive
- assets are referenced correctly from `public/` or the chosen asset strategy
- no unused React hooks/imports remain in converted files
- no whole-page hydration remains unless genuinely necessary

## 7. Preserve content and SEO signals

- titles and meta descriptions
- heading hierarchy
- semantic landmarks
- canonical/OG/Twitter metadata if present
- alt text and meaningful image usage

Do not accidentally downgrade semantics while chasing framework conversion.

## 8. Final migration review

The migration should be considered complete only if:

- the Astro result still feels like the original Lovable design
- static sections are genuinely in Astro
- interactive behavior still works where needed
- assets, fonts, and visual polish survived the move
- the final structure is coherent and maintainable
- there are no obvious SPA leftovers or broken assumptions
