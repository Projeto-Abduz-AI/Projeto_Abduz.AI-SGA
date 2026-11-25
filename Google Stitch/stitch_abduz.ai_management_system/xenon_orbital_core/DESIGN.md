---
name: Xenon Orbital Core
colors:
  surface: '#0f131c'
  surface-dim: '#0f131c'
  surface-bright: '#353943'
  surface-container-lowest: '#0a0e17'
  surface-container-low: '#181b25'
  surface-container: '#1c1f29'
  surface-container-high: '#262a34'
  surface-container-highest: '#31353f'
  on-surface: '#dfe2ef'
  on-surface-variant: '#bbcabf'
  inverse-surface: '#dfe2ef'
  inverse-on-surface: '#2c303a'
  outline: '#86948a'
  outline-variant: '#3c4a42'
  surface-tint: '#4edea3'
  primary: '#4edea3'
  on-primary: '#003824'
  primary-container: '#10b981'
  on-primary-container: '#00422b'
  inverse-primary: '#006c49'
  secondary: '#4cd7f6'
  on-secondary: '#003640'
  secondary-container: '#03b5d3'
  on-secondary-container: '#00424e'
  tertiary: '#ffb95f'
  on-tertiary: '#472a00'
  tertiary-container: '#e29100'
  on-tertiary-container: '#523200'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#6ffbbe'
  primary-fixed-dim: '#4edea3'
  on-primary-fixed: '#002113'
  on-primary-fixed-variant: '#005236'
  secondary-fixed: '#acedff'
  secondary-fixed-dim: '#4cd7f6'
  on-secondary-fixed: '#001f26'
  on-secondary-fixed-variant: '#004e5c'
  tertiary-fixed: '#ffddb8'
  tertiary-fixed-dim: '#ffb95f'
  on-tertiary-fixed: '#2a1700'
  on-tertiary-fixed-variant: '#653e00'
  background: '#0f131c'
  on-background: '#dfe2ef'
  surface-variant: '#31353f'
typography:
  headline-xl:
    fontFamily: Space Grotesk
    fontSize: 40px
    fontWeight: '700'
    lineHeight: 48px
    letterSpacing: -0.03em
  headline-xl-mobile:
    fontFamily: Space Grotesk
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 34px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Space Grotesk
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-lg-mobile:
    fontFamily: Space Grotesk
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 26px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Space Grotesk
    fontSize: 16px
    fontWeight: '600'
    lineHeight: 22px
    letterSpacing: 0em
  body-lg:
    fontFamily: Geist
    fontSize: 15px
    fontWeight: '400'
    lineHeight: 22px
    letterSpacing: -0.01em
  body-md:
    fontFamily: Geist
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 18px
    letterSpacing: 0em
  body-sm:
    fontFamily: Geist
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
    letterSpacing: 0.01em
  label-lg:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 18px
    letterSpacing: 0.02em
  label-md:
    fontFamily: JetBrains Mono
    fontSize: 11px
    fontWeight: '500'
    lineHeight: 14px
    letterSpacing: 0.04em
  label-sm:
    fontFamily: JetBrains Mono
    fontSize: 10px
    fontWeight: '500'
    lineHeight: 12px
    letterSpacing: 0.06em
  telemetry-num:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 18px
    letterSpacing: 0.02em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-mobile: 0.5rem
  margin: 1.5rem
  margin-mobile: 0.75rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 0.75rem
  space-lg: 1rem
  space-xl: 1.5rem
---

## Brand & Style

This design system drives an extraterrestrial operations management portal engineered for hyper-scale mission control, agile incident tracking, and specimen pipeline workflows. It bridges high-density telemetry with a tactical deep-space aesthetic, pairing the exacting functional clarity of Palantir Foundry or Linear with an evocative speculative-fiction veneer.

The emotional tone balances absolute operational rigor, classified authority, and cold computational elegance. The UI communicates calm certainty amid complex, multi-variable operations.

The aesthetic philosophy fuses:
- **Deep Space Technical Minimalism:** Ultra-dark matte surfaces punctuated by fine gridlines and spectral glow indicators rather than decorative noise.
- **Glass-Border Precision:** Subtle sub-surface lucency, crisp 1px hair-line telemetry dividers, and targeted cyan/emerald field illumination.
- **Data-Dense Enterprise Ergonomics:** Maximized data density per viewport, strict vertical alignment, instant scannability, and contextual HUD (Heads-Up Display) data chips.

## Colors

The palette simulates orbital telemetry visual systems operating in complete optical void. The chromatic structure organizes interface layers by operational priority:

- **Surface System (Void Obsidian & Deep Slate):**
  - Canvas Base: `#090D16` (Deep Cosmos Void) creates infinite contrast.
  - Surface Primary / Tier 1 Container: `#0F172A` provides the structural canvas for agile boards, data tables, and kanban lane boundaries.
  - Surface Elevated / Tier 2 Container: `#1E293B` serves as the interactive resting state for cards, popovers, and contextual sidebars.
  - Hairline Border / Outlines: `rgba(148, 163, 184, 0.12)` guarantees crisp spatial separation without optical bloat.

- **Signal Spectrum (Active Alien Bioluminescence & Sensors):**
  - Primary Accent (`#10B981` Emerald Glow): Denotes successful abduction capture, completed sprint increments, nominal orbital paths, and primary execution calls to action.
  - Secondary Accent (`#06B6D4` / `#22D3EE` Neon Cyan): Represents active telemetry data, live tracking links, selected filters, and energetic sprint milestones.
  - Tertiary Accent (`#F59E0B` Warning Amber): Communicates planetary containment leaks, blocked workflow tickets, anomalous specimen vital signs, and priority escalation states.
  - Alert Crimson (`#EF4444`): Reserved exclusively for planetary defense intercepts, mission failures, and destructive purge operations.

- **Data Readout & Text Tiers:**
  - High Emphasis: `#F8FAFC` (Pure Starlight) for critical telemetry, metric cards, and ticket headers.
  - Medium Emphasis: `#94A3B8` (Lunar Dust) for column labels, technical specs, and subheadings.
  - Low Emphasis / Meta: `#475569` for deactivated indicators, breadcrumb separators, and grid lines.

## Typography

The typographic hierarchy uses a triad of specialized typefaces to balance narrative theme with mission-critical readability:

1. **Space Grotesk (Display & Section Headings):** Introduces technical geometry and engineered angles to high-level system modules, dashboard titles, and lane headers.
2. **Geist (Body Copy & Form Controls):** Delivers clean readability for specimen intake descriptions, user story scenarios, and fleet documentation.
3. **JetBrains Mono (Telemetry, Badges, Identifiers & Data Tables):** Provides tabular figures, strict vertical character stacking, and zero ambiguity between alphanumeric glyphs (`0` vs `O`, `1` vs `l`) across target coordinates, epoch timestamps, and sprint story-point tallies.

Typography rules:
- Always enforce tabular figures (`font-variant-numeric: tabular-nums`) across all grid metrics, timestamp readouts, and ticket IDs.
- Micro-labels, specimen tags, and sprint story statuses must appear in uppercase with expanded tracking via `label-sm` or `label-md`.

## Layout & Spacing

The layout is built for high information density, rapid scanning, and real-time incident collaboration:

- **Layout Model:** High-density fluid grid anchoring an enterprise multi-pane master-detail workflow. The canonical desktop layout features a collapsible 240px telemetry navigation strip, a fluid agile board or matrix table viewport, and a slide-over 440px specimen inspection inspector.
- **Rhythm & Grid:** Built on a tight 4px baseline sub-grid (`space-xs` = 4px, `space-sm` = 8px, `space-md` = 12px, `space-lg` = 16px, `space-xl` = 24px) that favors compact data density over expansive whitespace.
- **Responsive Adaptations:**
  - **Desktop (>1280px):** Full multi-column agility boards (5+ workflow lanes visible simultaneously) with fixed tabular headers and sticky metric summary bars.
  - **Tablet (768px - 1279px):** Kanban lanes collapse into swipeable horizontal panels with pinned lane tallies; specimen detail panels convert to full modal sheets.
  - **Mobile (<767px):** Single-column stack with segmented controls replacing multi-lane boards. Gutters compress to 8px (`gutter-mobile`), padding resets to 12px, and complex telemetry cards convert to stacked single-metric rows.

## Elevation & Depth

Visual depth is achieved without heavy natural shadows, using translucent glass layers, crisp hairline boundaries, and subtle electromagnetic illumination:

- **Layer 0 (Void Ground):** Background `#090D16` with faint synthetic coordinate matrix gridlines (`rgba(34, 211, 238, 0.03)` with 32px pitch).
- **Layer 1 (Sub-Panel Basins):** Surface `#0F172A` enclosed with 1px border `rgba(148, 163, 184, 0.08)`. Defines board lanes, table hulls, and telemetry docks.
- **Layer 2 (Draggable Artifacts & Work Cards):** Surface `#1E293B` at `90%` opacity backed by `backdrop-filter: blur(12px)`. Outlined by a crisp 1px border `rgba(148, 163, 184, 0.16)`.
- **Layer 3 (Floating Overlays, Command Palettes, Popovers):** Surface `#0F172A` with `backdrop-filter: blur(16px)` and an ambient sci-fi glow: `0 0 0 1px rgba(6, 182, 212, 0.25), 0 8px 32px -4px rgba(0, 0, 0, 0.65)`.
- **Focus & Selection Luminescence:** Focused states forego fuzzy drop shadows in favor of a crisp internal and external dual ring: `0 0 0 1px #090D16, 0 0 0 2px #10B981, 0 0 12px rgba(16, 185, 129, 0.35)`.

## Shapes

The interface embraces a precision architectural shape language. All functional components use `roundedness: 1` (0.25rem / 4px base corner radius) with selective chamfered cues:

- **Cards, Modals, Inputs & Menus:** 4px border-radius creates a sharp, technical aesthetic without the harshness of raw 90-degree corners.
- **Status Indicators & Pulse Dots:** 9999px fully circular geometries preserve pure organic vitality when signaling active beam locks or live transmissions.
- **Telemetry Chips & Metric Badges:** Strict 3px-4px radius, preventing playful consumer pill shapes and maintaining a cohesive HUD feel.
- **Dividers & Hairlines:** Crisp 1px solid vectors styled with soft edge gradients fading out towards panel margins.

## Components

### Buttons & Interactive Triggers
- **Primary Operational Button:** Solid emerald `#10B981` fill with `#090D16` bold text, 4px corner radius, and faint green glow (`box-shadow: 0 0 14px rgba(16, 185, 129, 0.3)`). Hover shifts to `#34D399` with intensified luminescence.
- **Secondary / HUD Button:** Dark slate `#1E293B` fill, 1px border of `rgba(34, 211, 238, 0.3)`, `#22D3EE` text, and zero ambient drop shadow. Hover triggers `rgba(6, 182, 212, 0.12)` background wash.
- **Ghost / Utility Action:** Monospaced label, transparent fill, subtle muted text (`#94A3B8`), shifting to high-contrast white with a 1px border on focus.

### Telemetry Chips & Specimen Status Badges
- Built using `label-sm` or `label-md` uppercase JetBrains Mono.
- **Nominal / Abducted:** Emerald translucent fill `rgba(16, 185, 129, 0.12)` with solid `#10B981` border and text.
- **In-Transit / Beam Active:** Cyan translucent fill `rgba(6, 182, 212, 0.12)` with `#22D3EE` border and an animated pulsating signal dot.
- **Quarantined / Risk Escalated:** Amber translucent fill `rgba(245, 158, 11, 0.14)` with `#F59E0B` text and border.

### Agile Sprint Cards & Abduction Tickets
- Composed of Surface Elevated `#1E293B` at 4px radius with an understated top border accent corresponding to specimen threat classification or priority level.
- Header holds tabular identifier (`ABD-4092`), followed by `body-md` title, assigned mothership avatar chip, and bottom metadata array (containment sector, story points, elapsed mission time).
- Dragged state elevates card to Layer 3, adds 3-degree rotation tilt, and introduces a cyan border edge glow (`#06B6D4`).

### Form Inputs & Telemetry Filters
- Height fixed at 32px for compact desktop density.
- Background `#0F172A` with 1px border `rgba(148, 163, 184, 0.2)`. Placeholder text in `#475569`.
- Active focus state applies a crisp neon cyan outline: `border-color: #22D3EE` with `box-shadow: 0 0 0 1px #22D3EE, 0 0 8px rgba(34, 211, 238, 0.2)`.

### Checkboxes, Switches & Radio Nodes
- Precision square checkboxes with 2px corner radius.
- Unchecked: `#0F172A` fill with 1px border `rgba(148, 163, 184, 0.3)`.
- Checked: `#10B981` solid fill with dark void checkmark icon.
- Toggles utilize sliding rectangular nodes with monospaced `0` / `1` or `OFF` / `ON` micro-indicators inside the groove.

### Telemetry Tables & Metric Matrices
- Row height clamped at 36px. Alternating zebra stripes using subtle `rgba(255, 255, 255, 0.015)`.
- Numeric coordinates and time-series data right-aligned using tabular figures in JetBrains Mono.
- Hover states highlight entire rows in `rgba(6, 182, 212, 0.05)` with a 2px vertical neon cyan indicator bar pinned to the left edge.