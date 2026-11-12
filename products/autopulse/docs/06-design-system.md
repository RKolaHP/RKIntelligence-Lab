
# AutoPulse AI — Design System

**Document ID:** AP-DS-006  
**Version:** 1.0  
**Status:** Initial design system baseline  
**Platform:** Responsive Web Application  
**Framework:** React + TypeScript + Tailwind CSS

---

## 1. Design System Objectives

The AutoPulse AI design system establishes reusable visual standards and frontend components.

Objectives:

- Maintain visual consistency across all application modules.
- Create reusable UI components.
- Support responsive layouts.
- Improve accessibility.
- Reduce duplicated frontend code.
- Establish predictable interaction patterns.
- Support future product expansion.

## 2. Brand Identity

### Product Name

AutoPulse AI

### Brand Positioning

Automotive intelligence for connected fleet operations.

### Brand Personality

- Intelligent.
- Precise.
- Reliable.
- Modern.
- Operational.
- Technology-driven.

### Logo Direction

Use an abstract automotive intelligence symbol.

Recommended concept:
- Circular telemetry signal.
- Stylized vehicle motion line.
- Geometric pulse waveform.
- Minimal automotive-inspired icon.

Avoid using a generic car emoji as the primary brand identity.

### Wordmark

AutoPulse AI

Typography:
- AutoPulse: Semibold.
- AI: Accent color.

## 3. Color Tokens

### 3.1 Background Colors

| Token | Hex | Usage |
|---|---|---|
| background | #090E18 | Application background |
| background-secondary | #101827 | Main workspace |
| surface | #151F30 | Cards |
| surface-elevated | #1B2940 | Dialogs and popovers |
| surface-hover | #22324A | Hover states |
| surface-active | #293A53 | Active controls |

### 3.2 Brand Colors

| Token | Hex | Usage |
|---|---|---|
| primary | #36BFFA | Primary actions |
| primary-hover | #159DDC | Hover |
| secondary | #7C8CFF | Secondary emphasis |
| accent | #54E0C1 | Supporting highlights |

### 3.3 Status Colors

| Token | Hex | Usage |
|---|---|---|
| success | #36C98F | Healthy |
| warning | #F5B942 | Attention |
| danger | #F16B72 | Critical |
| info | #55A8FF | Information |
| neutral | #718198 | Unknown |

### 3.4 Text Colors

| Token | Hex | Usage |
|---|---|---|
| text-primary | #F4F7FC | Main text |
| text-secondary | #A7B4C7 | Supporting text |
| text-muted | #718198 | Metadata |
| text-disabled | #526176 | Disabled text |

### 3.5 Borders

| Token | Hex | Usage |
|---|---|---|
| border | #27354A | Default borders |
| border-subtle | #1E2A3D | Dividers |
| border-focus | #36BFFA | Focus states |

## 4. Typography System

Primary font: Inter.

Fallback:
- system-ui
- sans-serif

### Typography Scale

| Token | Size | Weight | Usage |
|---|---:|---:|---|
| display | 36px | 700 | Major landing headings |
| h1 | 28px | 700 | Page titles |
| h2 | 22px | 600 | Section titles |
| h3 | 18px | 600 | Card headings |
| h4 | 15px | 600 | Subsections |
| body | 14px | 400 | Main content |
| small | 12px | 400 | Supporting text |
| caption | 11px | 400 | Metadata |
| kpi | 30px | 700 | Dashboard values |

### Typography Rules

- Use consistent heading hierarchy.
- Avoid excessively small text.
- Use tabular numerals for KPI values.
- Maintain readable line heights.
- Avoid unnecessary uppercase text.

## 5. Spacing System

Use a 4px base spacing scale.

| Token | Value |
|---|---:|
| space-1 | 4px |
| space-2 | 8px |
| space-3 | 12px |
| space-4 | 16px |
| space-5 | 20px |
| space-6 | 24px |
| space-8 | 32px |
| space-10 | 40px |
| space-12 | 48px |
| space-16 | 64px |

### Layout Rules

- Card padding: 20–24px.
- Dashboard gap: 16–20px.
- Section spacing: 24–32px.
- Main content padding: 28px desktop.
- Form field spacing: 16px.

## 6. Border Radius

| Token | Value |
|---|---:|
| radius-sm | 6px |
| radius-md | 8px |
| radius-lg | 12px |
| radius-xl | 16px |
| radius-full | 999px |

Use consistent corner radii across the application.

## 7. Shadows and Elevation

| Token | Usage |
|---|---|
| shadow-sm | Small controls |
| shadow-md | Cards and dropdowns |
| shadow-lg | Dialogs and overlays |

Avoid excessive shadows and neon effects.

## 8. Iconography

Library: Lucide React.

Icon standards:
- Sidebar: 18–20px.
- Buttons: 16px.
- Status indicators: 14–16px.
- Dashboard cards: 20–22px.

Recommended icons:

| Component | Icon |
|---|---|
| Overview | LayoutDashboard |
| Vehicles | CarFront |
| Telemetry | Activity |
| Maintenance | Wrench |
| Intelligence | BrainCircuit |
| Analytics | ChartNoAxesCombined |
| Alerts | Bell |
| Settings | Settings |
| Search | Search |
| Notifications | BellRing |
| Profile | UserRound |
| Add | Plus |

Icons should remain visually consistent in size and stroke weight.

## 9. Button System

### Primary Button

Usage:
- Create Vehicle.
- Create Work Order.
- Save Changes.

Appearance:
- Primary cyan background.
- Dark readable text.
- Medium rounded corners.

### Secondary Button

Usage:
- Cancel.
- View Details.
- Secondary navigation actions.

Appearance:
- Transparent or surface background.
- Subtle border.

### Destructive Button

Usage:
- Deactivate.
- Cancel Work Order.
- Delete permitted records.

Appearance:
- Danger treatment.
- Explicit confirmation for consequential operations.

### Button Sizes

| Size | Height |
|---|---:|
| Small | 32px |
| Medium | 40px |
| Large | 48px |

All buttons must support:
- Default.
- Hover.
- Focus.
- Active.
- Disabled.
- Loading.

## 10. Card System

### Standard Card

Properties:
- Background surface.
- Subtle border.
- 12px radius.
- 20px padding.

### KPI Card

Components:
- Label.
- Value.
- Icon.
- Optional trend.
- Supporting description.

### Chart Card

Components:
- Title.
- Description.
- Filter controls.
- Chart.
- Legend.
- Source information.

### Alert Card

Components:
- Severity.
- Description.
- Vehicle identifier.
- Timestamp.
- Action.

### Vehicle Card

Components:
- Vehicle identifier.
- Vehicle class.
- Manufacturer.
- Operational status.
- Available health information.
- View Details.

## 11. Form System

Standard form components:

- Text input.
- Number input.
- Select.
- Multi-select.
- Date picker.
- Textarea.
- Checkbox.
- Radio group.
- Search field.

### Form Standards

- Always show field labels.
- Mark required fields.
- Provide validation messages.
- Preserve entered values after recoverable errors.
- Disable submission while processing.
- Show success or failure feedback.

### Validation States

- Default.
- Focus.
- Valid.
- Invalid.
- Disabled.

## 12. Table System

Tables should support:

- Sorting.
- Pagination.
- Search.
- Filtering.
- Row selection when appropriate.
- Row actions.
- Empty states.
- Loading skeletons.

### Table Design

Header:
- 12px semibold.
- Secondary text color.

Body:
- 13–14px.
- Primary text color.

Rows:
- Minimum 52px height.
- Subtle separators.
- Hover background.

Avoid placing excessive information in a single table.

## 13. Data Visualization System

Recommended library: Recharts.

### Chart Mapping

| Business requirement | Chart |
|---|---|
| Fleet health distribution | Donut |
| Vehicle class distribution | Horizontal bar |
| Availability trends | Line |
| Maintenance expenditure | Area or line |
| Vehicle utilization | Bar |
| Telemetry readings | Time-series line |
| Work-order distribution | Donut |
| Vehicle comparison | Grouped bar |

### Chart Standards

Every chart should include:
- Clear title.
- Description.
- Axis labels.
- Units.
- Legend when necessary.
- Tooltips.
- Reporting period.
- Source classification.

### Visualization Rules

- Avoid misleading axis ranges.
- Do not hide missing values.
- Use consistent measurement units.
- Make charts accessible.
- Do not use color as the only distinction.

## 14. Status Badge System

Supported variants:

| Status | Treatment |
|---|---|
| Healthy | Success |
| Operational | Success |
| Attention Required | Warning |
| Critical | Danger |
| Unknown | Neutral |
| In Progress | Information |
| Completed | Success |
| On Hold | Warning |
| Cancelled | Neutral |

Each badge must contain readable text.

## 15. Navigation Components

### Sidebar

- Expanded width: 248px.
- Collapsed width: 76px.
- Fixed desktop navigation.
- Active navigation indicator.
- Tooltips when collapsed.

### Topbar

- Height: 68px.
- Search.
- Notifications.
- Environment indicator.
- User menu.

### Breadcrumb

- Reflect actual page hierarchy.
- Support navigation to parent pages.
- Indicate the current page.

## 16. Dialog and Drawer System

Use dialogs for:
- Confirmation.
- Important warnings.
- Short forms.

Use side drawers for:
- Vehicle details.
- Alert investigation.
- Work-order creation.
- Quick editing.

Dialogs must:
- Support keyboard interaction.
- Maintain focus.
- Have accessible labels.
- Provide clear actions.

## 17. Notification System

Notification types:

- Success.
- Error.
- Warning.
- Information.

Notifications should:
- Describe the result.
- Explain errors clearly.
- Avoid unnecessary interruptions.
- Remain accessible.

Critical operational alerts should also be available in the dedicated Alerts module.

## 18. Application States

Every reusable component should define:

1. Default.
2. Hover.
3. Focus.
4. Active.
5. Disabled.
6. Loading.
7. Error.
8. Empty, where applicable.

All components must remain consistent across modules.

## 19. Accessibility Standards

Target: WCAG 2.2 AA.

Requirements:
- Keyboard accessibility.
- Semantic HTML.
- Visible focus states.
- Sufficient contrast.
- Accessible form labels.
- Screen-reader support.
- Accessible tables.
- Chart descriptions.
- Reduced-motion support.

## 20. Tailwind CSS Implementation

Use centralized design tokens rather than scattering color values throughout components.

Example CSS variables:

```css
:root {
  --background: #090E18;
  --background-secondary: #101827;
  --surface: #151F30;
  --surface-elevated: #1B2940;

  --primary: #36BFFA;
  --secondary: #7C8CFF;
  --accent: #54E0C1;

  --success: #36C98F;
  --warning: #F5B942;
  --danger: #F16B72;

  --text-primary: #F4F7FC;
  --text-secondary: #A7B4C7;
  --text-muted: #718198;

  --border: #27354A;
  --border-subtle: #1E2A3D;

  --radius-card: 12px;
  --radius-control: 8px;
}
```

### Component Folder Structure

```text
src/
├── components/
│   ├── ui/
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── badge.tsx
│   │   ├── input.tsx
│   │   ├── select.tsx
│   │   ├── dialog.tsx
│   │   ├── table.tsx
│   │   └── tooltip.tsx
│   │
│   ├── charts/
│   │   ├── line-chart.tsx
│   │   ├── bar-chart.tsx
│   │   └── donut-chart.tsx
│   │
│   ├── layout/
│   │   ├── app-sidebar.tsx
│   │   ├── app-topbar.tsx
│   │   └── app-layout.tsx
│   │
│   └── shared/
│       ├── kpi-card.tsx
│       ├── status-badge.tsx
│       ├── empty-state.tsx
│       └── loading-state.tsx
```

## 21. Component Quality Standards

Every reusable component should:

- Have a single clear responsibility.
- Support TypeScript interfaces.
- Avoid duplicated styling.
- Support accessible interaction.
- Have documented variants.
- Be independently testable.
- Avoid business-specific data dependencies.

## 22. Design System Acceptance Criteria

The design system is ready when:

- Color tokens are defined.
- Typography is standardized.
- Spacing is consistent.
- Buttons and forms are reusable.
- Tables and cards are standardized.
- Chart conventions are documented.
- Navigation components are reusable.
- Responsive behavior is established.
- Accessibility requirements are documented.
- Components have defined interaction states.

## 23. Next Deliverable

**07-system-architecture.md**

The next document will define:

- Overall system architecture.
- Frontend architecture.
- Backend services.
- Data ingestion architecture.
- Microsoft Fabric integration strategy.
- Database integration.
- AI/ML services.
- API communication.
- Authentication and security.
- Infrastructure and deployment.
- Monitoring and observability.

**End of document.**
