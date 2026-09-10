# MSS Dashboard Design System

**Design System:** UUIF 9.2 (SonicWall Enterprise UI Framework)  
**Version:** 1.0  
**Date:** 2026-09-04  
**Reference Host:** `uuif-9.2.eng.sonicwall.com`

---

## Overview

The MSS Dashboard is built on UUIF 9.2, SonicWall's enterprise design system. This document catalogs all components used in the MSS Dashboard prototype, their variants, structure, and usage patterns.

All components use CSS variable tokens for theming (color, spacing, typography, shadows, radius). The design system supports light and dark themes via the `data-theme="light"` attribute on the root `<html>` element.

---

## Color Tokens

### Text Colors
- `--uuif-text-primary` — Primary text (high contrast)
- `--uuif-text-secondary` — Secondary text (lower contrast)
- `--uuif-text-tertiary` — Tertiary text (minimal contrast)
- `--uuif-text-contrast` — High contrast (usually white on dark)
- `--uuif-text-disabled` — Disabled state text
- `--uuif-text-hover` — Text on hover
- `--uuif-text-selected` — Text when selected
- `--uuif-text-highlight` — Highlighted text

### Surface Colors
- `--uuif-surface-container` — Container background
- `--uuif-surface-bg` — Primary background
- `--uuif-surface-primary` — Primary surface
- `--uuif-surface-secondary` — Secondary surface
- `--uuif-surface-tertiary` — Tertiary surface
- `--uuif-surface-highlight` — Highlighted surface
- `--uuif-surface-hover` — Surface on hover
- `--uuif-surface-selected` — Surface when selected
- `--uuif-surface-disabled` — Disabled surface
- `--uuif-surface-contrast` — High contrast surface
- `--uuif-surface-model` — Modal/overlay surface

### Border Colors
- `--uuif-border-primary` — Primary border
- `--uuif-border-secondary` — Secondary border
- `--uuif-border-tertiary` — Tertiary border
- `--uuif-border-transparent` — Transparent border
- `--uuif-border-disabled` — Disabled border
- `--uuif-border-hover` — Border on hover
- `--uuif-border-selected` — Border when selected

### Brand Colors
- `--uuif-brand-navy` — SonicWall navy blue
- `--uuif-brand-blue` — SonicWall blue
- `--uuif-brand-orange` — SonicWall orange
- `--uuif-brand-green` — Brand green
- `--uuif-brand-red` — Brand red
- `--uuif-brand-yellow` — Brand yellow

### Status Colors
- `--uuif-status-normal` — Normal/informational state
- `--uuif-status-minor` — Minor/warning state (yellow)
- `--uuif-status-major` — Major/warning state (orange)
- `--uuif-status-high` — High/critical state (red)
- `--uuif-status-failed` — Failed/error state (red)

### Semantic Fills
- `--uuif-fill-blue-lightest` — Light blue fill
- `--uuif-fill-green-xxx-lighter` — Light green fill
- `--uuif-fill-yellow-xxx-lighter` — Light yellow fill
- `--uuif-fill-red-lightest` — Light red fill
- `--uuif-fill-green-x-darker` — Darker green fill
- `--uuif-fill-orange-x-darker` — Darker orange fill
- `--uuif-fill-red-x-darker` — Darker red fill

### Icon Colors
- `--uuif-icon-primary` — Primary icon color
- `--uuif-icon-secondary` — Secondary icon color
- `--uuif-icon-tertiary` — Tertiary icon color
- `--uuif-icon-hover` — Icon on hover

---

## Layout & Spacing Components

### App Shell
- **`uuif-app`** — Root container for page layout; establishes grid structure for nav rail + main content
  - Typically wraps the entire page
  - Works with `uuif-nav-rail` (left sidebar) and `uuif-main` (main content area)

### Main Content Area
- **`uuif-main`** — Main content container
- **`uuif-page-content`** — Content wrapper inside main
- **`uuif-page-head`** — Page header area (title, breadcrumbs)
- **`uuif-page-sub`** — Subheader or secondary content area

### Spacing Scale (vars: `--uuif-sp-1` through `--uuif-sp-12`)
- Used for padding, margins, and gaps throughout components
- Follows a consistent spacing scale: 4px, 8px, 12px, 16px, 20px, 24px, 28px, 32px, 36px, 40px, 44px, 48px

### Radius Tokens
- `--uuif-radius-4` — 4px border radius (subtle)
- `--uuif-radius-6` — 6px border radius
- `--uuif-radius-8` — 8px border radius (common)
- `--uuif-radius-12` — 12px border radius
- `--uuif-radius-22` — 22px border radius (medium pill)
- `--uuif-radius-pill` — Fully rounded (pill shape)

### Shadow Tokens
- `--uuif-shadow-sm` — Small shadow (subtle elevation)
- `--uuif-shadow-md` — Medium shadow (elevated)

---

## Typography Components & Tokens

### Font Tokens (format: `--uuif-font-{weight}-{size}`)

**Semibold weights:**
- `--uuif-font-semibold-14` — 14px semibold (headings, labels)
- `--uuif-font-semibold-13` — 13px semibold
- `--uuif-font-semibold-12` — 12px semibold (small headings)

**Bold weights:**
- `--uuif-font-bold-16` — 16px bold (page titles)

**Regular weights:**
- `--uuif-font-regular-16` — 16px regular (body)
- `--uuif-font-regular-14` — 14px regular (body)
- `--uuif-font-regular-13` — 13px regular (body, small)
- `--uuif-font-regular-12` — 12px regular (captions, meta)

---

## Navigation Components

### Navigation Rail
- **`uuif-nav-rail`** — Vertical navigation rail on left side
  - Contained within `uuif-app` grid
  - Contains `uuif-nav-logo`, `uuif-nav-item`, `uuif-nav-divider`, `uuif-nav-spacer`

- **`uuif-nav-logo`** — Logo area at top of nav rail
  - Typically SonicWall logo or partner branding

- **`uuif-nav-item`** — Individual navigation item
  - Modifier: `.is-selected` — Marks current active page
  - Typically contains icon + text label
  - Clickable navigation target

- **`uuif-nav-divider`** — Visual separator in nav rail

- **`uuif-nav-spacer`** — Flexible spacer to push nav items (e.g., push footer items to bottom)

### Secondary Navigation (Sub-Nav Panel)
- **`uuif-subnav`** — Collapsible secondary navigation panel (often on left, below nav rail or as sidebar)
  - Contains navigation links, product info, footer

- **`uuif-subnav-product`** — Product branding area within subnav

- **`uuif-subnav-wordmark`** — Product wordmark/logo within subnav
  - Modifier: `.uuif-subnav-wordmark--ondark` — Light logo on dark background
  - Modifier: `.uuif-subnav-wordmark--onlight` — Dark logo on light background

- **`uuif-subnav-hd`** — Subnav section header
- **`uuif-subnav-title`** — Title within subnav section
- **`uuif-subnav-section`** — Grouping section within subnav

- **`uuif-subnav-nav`** — Nav links container

- **`uuif-subnav-link`** — Individual subnav link
  - Modifier: `.is-active` — Current active link
  - Typically shows expanded content or current section

- **`uuif-subnav-foot`** — Footer area of subnav (logout, settings, etc.)

### Breadcrumb
- **`uuif-breadcrumb`** — Breadcrumb navigation
- **`uuif-crumb-sep`** — Separator between breadcrumb items

---

## Top Bar / Action Bar

- **`uuif-topbar`** — Top action bar, typically in header
  - Contains app title, icons, user menu, notifications

- **`uuif-topbar-flex`** — Flex container within topbar for layout

- **`uuif-topbar-icons`** — Icons section (notifications, settings, user menu)

- **`uuif-topbar-divider`** — Vertical divider in topbar

- **`uuif-top-bar__icon-btn`** — Icon button in topbar
  - Often used for notifications, user menu trigger, settings

- **`uuif-topbar-badge`** — Badge/notification count on icon
  - Shows unread count, alerts, etc.

- **`uuif-avatar`** — User avatar (circular image)
- **`uuif-avatar-wrap`** — Wrapper around avatar

---

## Card Component

- **`uuif-card`** — Container card with optional header, body, footer sections
  - Common modifier: `.ptile` — Card displayed as a "profile tile"

### Card Structure
```html
<div class="uuif-card">
  <div class="uuif-card-hd">
    <span class="uuif-card-title">Card Title</span>
    <span class="uuif-card-hd-actions">
      <!-- Action buttons, links -->
    </span>
  </div>
  <div class="uuif-card-bd">
    <!-- Main card content -->
  </div>
  <div class="uuif-card-ft">
    <!-- Footer content (less common) -->
  </div>
</div>
```

### Card Subcomponents
- **`uuif-card-hd`** — Card header (title + actions)
- **`uuif-card-title`** — Card title text
- **`uuif-card-hd-actions`** — Action buttons/links in header
- **`uuif-card-bd`** — Card body (main content)
  - Modifier: `.uuif-card-bd--flush` — Remove default padding (for full-bleed content like tables)
- **`uuif-card-ft`** — Card footer (less common)
  - Common modifier: `.treply` — Appears to be custom variant for ticket replies
- **`uuif-card-note`** — Footnote or note within card
- **`uuif-card-sub`** — Subheading or subtitle within card
- **`uuif-card-sub.num`** — Numeric value or count in subheading

---

## Button Component

- **`uuif-btn`** — Standard button
  - Base button styling with default size
  
### Button Modifiers
- **`.uuif-btn--sm`** — Small button
- **`.uuif-btn--primary`** — Primary action button (high emphasis)
- **`.uuif-btn--danger`** — Danger/destructive action button

### Custom Button Variants (in MSS Dashboard)
- **`.fpill`** — Pill-shaped filter button (full width, visible in filter bar)
- **`.sev-pill`** — Severity-based pill button (alert severity filter)
- **`.st-pill`** — State-based pill button (ticket state filter: "you", "mss", "parked")
  - Modifier: `.on` — Active/selected state for pill

---

## Data Components

### Count Block (KPI / Stat Tile)
- **`uuif-count`** — Container for a statistic or count
  - Modifier: `.uuif-count--warning` — Warning state (yellow)
  - Modifier: `.uuif-count--error` — Error state (red)

### Count Structure
```html
<div class="uuif-count uuif-count--warning">
  <span class="uuif-count-value num">12</span>
  <span class="uuif-count-unit">alerts</span>
  <span class="uuif-count-label">SOC alerts</span>
  <span class="uuif-count-sub">48,213 raw detections screened</span>
</div>
```

### Count Grid (Multiple Stats)
- **`uuif-count-grid`** — Container for multiple count blocks (responsive grid)
- **`uuif-count-head`** — Header for count section
- **`uuif-count-value`** — Numeric value (typically styled with `.num` class)
- **`uuif-count-label`** — Label for the count
- **`uuif-count-sub`** — Subtext or additional detail
- **`uuif-count-unit`** — Unit of measurement (e.g., "alerts", "devices")

### Table
- **`uuif-table`** — Data table for displaying tabular data
  - Modifier: `.svc-table` — Service offerings table variant
  - Used in cards with `.uuif-card-bd--flush` for full-width tables

- **`uuif-table-scroll`** — Wrapper for horizontally scrollable table

### Pagination
- **`uuif-pagination`** — Pagination controls or text (e.g., "12 SOC alerts · severity is the SOC's own classification")

### Progress
- **`uuif-progress`** — Progress bar or progress indicator

### Spinner
- **`uuif-spinner`** — Loading spinner (not visible in HTML, likely SVG or CSS animation)

---

## Status & Severity Components

### Severity Icon
- **`uuif-sev`** — Severity indicator icon
  - Modifier: `.uuif-sev--critical` — Critical severity (red)
  - Modifier: `.uuif-sev--major` — Major severity (orange)
  - Modifier: `.uuif-sev--minor` — Minor severity (yellow)
  - Modifier: `.uuif-sev--failed` — Failed state (red)

### Severity Cell (Table Cell)
- **`uuif-sev-cell`** — Severity cell in table
  - Modifier: `.ra-sev` — Custom variant (appears in MSS dashboard for alert rows)

### Severity Text
- **`uuif-sev-text`** — Text label for severity level
  - Modifier: `.uuif-sev-text--critical` — Critical severity text
  - Modifier: `.uuif-sev-text--major` — Major severity text
  - Modifier: `.uuif-sev-text--minor` — Minor severity text

### Status Dot
- **`uuif-dot`** — Small status indicator dot
  - Modifier: `.uuif-dot--normal` — Normal state (green or blue)

---

## Chip / Badge / Tag Components

- **`uuif-chip`** — Badge, tag, or status chip
  - Modifier: `.uuif-chip--success` — Success/positive state (green)
  - Modifier: `.uuif-chip--warning` — Warning state (yellow/orange)
  - Modifier: `.uuif-chip--error` — Error state (red)

### Chip Row (Multiple Chips)
- **`uuif-chip-row`** — Container for multiple chips
  - Modifier: `.uuif-chip-row--center` — Center-aligned chips

### Custom Chip Variants (MSS Dashboard)
- **`.custfilter-clear`** — Clear chip for removing customer filters
- **`.sa-chip`** — Service availability chip (warning state)
- **`.ra-state`** — Risk assessment state chip

---

## Input & Form Components

- **`uuif-input`** — Text input, select, or other form control
  - Modifier: `.custfilter-select` — Customer filter dropdown
  - Modifier: `.facet-select` — Faceted filter dropdown
  - Modifier: `.uuif-push-right` — Align input to right side of container

---

## Dropdown / Menu Components

- **`uuif-drop-menu`** — Dropdown menu container (user menu, action menu)

### Dropdown Menu Structure
```html
<div class="uuif-drop-menu">
  <span class="uuif-drop-menu-head">User Name</span>
  <a class="uuif-drop-menu-item" href="#">Menu Item</a>
  <a class="uuif-drop-menu-item" href="#">Menu Item</a>
</div>
```

- **`uuif-drop-menu-head`** — Header/title of dropdown menu
- **`uuif-drop-menu-item`** — Individual menu item (link or button)

---

## Overlay & Modal Components

- **`uuif-modal`** — Modal dialog container
  - Modifier: `.uuif-modal--sm` — Small modal
  - Modifier: `.uuif-modal--md` — Medium modal

---

## Toolbar & Filtering Components

- **`uuif-toolbar`** — Toolbar container for filter controls or actions
  - Modifier: `.ufilter` — Filter toolbar variant

- **`uuif-toolbar-label`** — Label within toolbar

- **`uuif-toolbar-note`** — Explanatory text or note in toolbar
  - Often shows active filters: "Showing X results for [filter criteria]"

---

## Utility & Layout Classes

### Grid
- **`uuif-grid-2`** — 2-column grid layout

### Text Utilities
- **`uuif-cell-note`** — Note text within a table cell (secondary text)
- **`uuif-empty`** — Empty state container (no results message)

### Chevron Icon
- **`uuif-chevron`** — Chevron icon (often for expandable sections or navigation)

### Flex Utilities
- **`uuif-push-right`** — Flexbox utility to push element to the right (used with inputs)

### Sizing
- **`.num`** — Applied to numeric values for tabular alignment

---

## Component Usage Patterns in MSS Dashboard

### Alert Dashboard
- Count blocks showing: Total SOC alerts, Raw detections screened
- Severity indicators for each alert
- Severity chips for filtering (Critical, Major, Minor)
- State pills for ticket routing: "Waiting on you", "With MSS", "Scheduled/on hold"

### Firewall Unit Listing
- Card grid showing 5 firewall units
- Each card shows unit ID, customer, onboarding status, health status
- Status pills showing "Onboarding in progress"

### Data Tables
- Customer list table
- Alert table with severity, source, type, created date
- Ticket table with state, service, title, created date
- Firewall inventory table with unit ID, model, customer, status

### Filtering & Search
- Customer dropdown filter
- Text search inputs with placeholder hints
- Filter pills to show active filters
- Clear filter buttons

### Multi-Tenant Navigation
- Customer selector dropdown showing 4 managed customers
- Scope selector to pivot between customers globally
- Breadcrumb showing current page path

---

## Design System Recommendations for Consistency

### Color Usage
1. **Status indicators** use the severity color palette: critical (red), major (orange), minor (yellow), normal (blue/green)
2. **Action buttons** use brand blue or navy
3. **Destructive buttons** use brand red
4. **Chip backgrounds** follow status semantics (green = success, yellow = warning, red = error)

### Spacing
- Cards use consistent `--uuif-sp-2` (8px) padding for content
- Table cells use `--uuif-sp-2` padding
- Sections are separated by `--uuif-sp-4` or `--uuif-sp-6` (16–24px)

### Typography
- Page titles: `--uuif-font-bold-16`
- Card titles: `--uuif-font-semibold-14`
- Body text: `--uuif-font-regular-14`
- Small text / captions: `--uuif-font-regular-12`

### Interactive States
- Hover: Use `.uuif-surface-hover` background
- Selected: Use `.uuif-surface-selected` background + `.uuif-border-selected` border
- Disabled: Use `.uuif-text-disabled` color + `.uuif-surface-disabled` background

---

## Custom Component Patterns in MSS Dashboard

Beyond UUIF base components, the MSS Dashboard uses these custom variants:

- **`.fpill`** — Pill-shaped filter buttons in filter toolbar
- **`.sev-pill`** — Severity-based pills (Critical, Major, Minor state buttons)
- **`.st-pill`** — State-based pills (Waiting on you, With MSS, Scheduled/on hold)
- **`.on`** — Active state modifier for pill buttons
- **`.ptile`** — Profile tile variant of card
- **`.treply`** — Ticket reply footer variant
- **`.ra-state`** — Risk assessment state display
- **`.sa-chip`** — Service availability warning chip
- **`.ra-sev`** — Risk assessment severity display

---

## Responsive Behavior

The design system uses responsive grid layouts:
- **Desktop**: 2-column, 3-column, or 4-column grids depending on component
- **Tablet**: Typically 2-column or single-column layouts
- **Mobile**: Single-column layout with stacked navigation

Tables use horizontal scrolling on smaller viewports via `.uuif-table-scroll` wrapper.

---

## Dark Mode Support

All components support light and dark themes via CSS variables. Switch themes by toggling `data-theme="light"` or `data-theme="dark"` on the `<html>` element.

---

## Next Steps for Design Consistency

1. **Audit** existing custom classes (`.fpill`, `.sev-pill`, etc.) and determine if they should be documented in UUIF or kept as MSS-specific overrides
2. **Document** component props and states that are not visible in the HTML prototype (e.g., loading states, error states, disabled states)
3. **Create** Figma library with all UUIF 9.2 components for design-to-code handoff
4. **Establish** naming conventions for custom variants to avoid collision with UUIF updates
5. **Test** theme switching (light/dark) across all components for contrast and readability

---

*Design System Documentation — MSS Dashboard using UUIF 9.2*
