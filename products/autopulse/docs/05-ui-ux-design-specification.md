
# AutoPulse AI — UI/UX Design Specification

**Document ID:** AP-UX-005  
**Version:** 1.0  
**Status:** Initial design specification  
**Product:** AutoPulse AI  
**Platform:** Responsive Web Application

---

# 1. Design Vision

AutoPulse AI is a premium automotive intelligence platform designed for fleet managers, maintenance teams, and fleet analysts.

The interface should communicate:
- Operational intelligence.
- Automotive technology.
- Reliability.
- Data transparency.
- Predictive insights.
- Enterprise-grade usability.

## 1.1 Design Direction

Visual direction: Premium Automotive Intelligence.

Design characteristics:
- Dark charcoal application shell.
- Deep navy surfaces.
- Electric cyan accent.
- Restrained green, amber, and red status colors.
- Clean typography.
- Structured dashboard layouts.
- High-quality data visualization.
- Minimal decorative elements.

The application should feel like a combination of an enterprise fleet command center and a modern automotive technology platform.

## 1.2 UX Principles

1. Important information should be visible immediately.
2. Critical alerts should be easy to identify.
3. Every visualization should have a clear business purpose.
4. Data sources and timestamps should be transparent.
5. Complex workflows should require minimal navigation.
6. Desktop usability should be prioritized without sacrificing mobile accessibility.
7. AI predictions must be distinguishable from observed vehicle data.

---

# 2. Visual Design System

## 2.1 Color Palette

### Application background

| Token | Color | Usage |
|---|---|---|
| Background Primary | #090E18 | Main application background |
| Background Secondary | #101827 | Main workspace surfaces |
| Surface Primary | #151F30 | Cards and panels |
| Surface Elevated | #1B2940 | Elevated components |
| Surface Hover | #22324A | Hover states |

### Brand colors

| Token | Color | Usage |
|---|---|---|
| Primary | #36BFFA | Primary accent |
| Primary Hover | #159DDC | Interactive hover |
| Secondary | #7C8CFF | Secondary accent |
| Highlight | #54E0C1 | Data emphasis |

### Status colors

| Token | Color | Usage |
|---|---|---|
| Success | #36C98F | Operational / healthy |
| Warning | #F5B942 | Attention required |
| Danger | #F16B72 | Critical |
| Information | #55A8FF | Informational |

### Text colors

| Token | Color | Usage |
|---|---|---|
| Text Primary | #F4F7FC | Main text |
| Text Secondary | #A7B4C7 | Supporting text |
| Text Muted | #718198 | Metadata |
| Border | #27354A | Dividers and outlines |

Status must never rely on color alone. Use text labels and accessible indicators.

## 2.2 Typography

Recommended font family:
- Inter.

Typography scale:

| Element | Size | Weight |
|---|---:|---|
| Main page title | 28px | 700 |
| Section heading | 20px | 600 |
| Card heading | 15px | 600 |
| Body text | 14px | 400 |
| Supporting text | 12px | 400 |
| KPI value | 30px | 700 |
| Table heading | 12px | 600 |

## 2.3 Spacing

Use a consistent 4px spacing scale.

| Token | Value |
|---|---:|
| XS | 4px |
| SM | 8px |
| MD | 12px |
| LG | 16px |
| XL | 24px |
| 2XL | 32px |
| 3XL | 48px |

## 2.4 Border Radius

- Small controls: 6px.
- Inputs: 8px.
- Cards: 12px.
- Large panels: 16px.
- Pills: 999px.

## 2.5 Shadows

Use subtle elevation and borders.

Avoid excessive glow effects, strong gradients, and excessive glassmorphism.

---

# 3. Global Application Layout

## 3.1 Desktop Layout

Reference viewport: 1440 × 900.

Application structure:

- Sidebar: 248px expanded.
- Collapsed sidebar: 76px.
- Topbar: 68px.
- Main workspace: remaining available width.
- Main content padding: 28px.
- Standard card gap: 18px.

Layout:

```text
+--------------------------------------------------------------+
| SIDEBAR | TOPBAR: Search | Notifications | User              |
|         +----------------------------------------------------+
|         |                                                    |
|         | PAGE TITLE                         ACTION BUTTON   |
|         |                                                    |
|         | KPI 1       KPI 2       KPI 3       KPI 4           |
|         |                                                    |
|         | CHART / ANALYTICS       | SECONDARY PANEL           |
|         |                         |                           |
|         |----------------------------------------------------|
|         |                                                    |
|         | DATA TABLE / OPERATIONAL ACTIVITY                   |
|         |                                                    |
+--------------------------------------------------------------+
```

## 3.2 Sidebar

Brand:
- AutoPulse AI wordmark.
- Abstract automotive signal icon.

Navigation:
1. Overview
2. Vehicles
3. Telemetry Explorer
4. Maintenance
5. Predictive Intelligence
6. Analytics
7. Alerts

Bottom:
- Settings.
- Help.
- User profile.

The sidebar must support collapsed and expanded modes.

## 3.3 Topbar

Components:
- Breadcrumb.
- Global search.
- Notification icon.
- Data environment indicator.
- User avatar.
- Profile dropdown.

The environment indicator must clearly distinguish demonstration, historical, synthetic, and live-connected environments.

---

# 4. Screen 01 — Fleet Command Center

**Route:** /overview

**Primary persona:** Fleet Manager

### Objective

Provide an immediate overview of fleet operations, vehicle health, maintenance activities, and operational alerts.

### Layout

#### A. Page Header

Title: Fleet Command Center

Subtitle: Monitor fleet operations and vehicle intelligence.

Right-side controls:
- Fleet selector.
- Reporting period.
- Last updated timestamp.

#### B. KPI Cards

Four cards:

1. Total Vehicles
2. Operational Vehicles
3. Under Maintenance
4. Critical Alerts

Each card contains:
- Metric value.
- Descriptive label.
- Trend indicator, when meaningful.
- Supporting context.

Do not invent trend percentages if comparison data is unavailable.

#### C. Fleet Health Distribution

Visualization: Donut chart.

Categories:
- Healthy.
- Attention Required.
- Critical.
- Unknown.

Include:
- Vehicle count.
- Percentage.
- Legend.
- Reporting period.

Unknown must remain distinct from healthy.

#### D. Fleet Availability Trend

Visualization: Area or line chart.

Show:
- Reporting period.
- Availability percentage.
- Historical comparison, if available.
- Hover details.

#### E. Vehicle Class Distribution

Visualization: Horizontal bar chart.

Categories:
- Passenger Cars.
- Vans.
- Light Commercial Vehicles.
- Heavy Commercial Vehicles.

#### F. Critical Alerts

Table columns:
- Severity.
- Vehicle ID.
- Alert Description.
- Created Time.
- Status.
- Action.

#### G. Upcoming Maintenance

Table columns:
- Vehicle ID.
- Vehicle.
- Maintenance Type.
- Due Date.
- Priority.

#### H. Vehicles Requiring Attention

Display compact vehicle cards containing:
- Vehicle identifier.
- Vehicle class.
- Available health indicator.
- Latest relevant event.
- View Details action.

### Interactions

- Selecting a KPI opens its corresponding filtered inventory.
- Selecting a vehicle opens Vehicle Details.
- Selecting an alert opens Alert Details.
- Selecting a maintenance item opens its work order.
- Changing the reporting period refreshes supported metrics.

---

# 5. Screen 02 — Vehicle Inventory

**Route:** /vehicles

### Objective

Enable users to search, inspect, and manage fleet vehicles.

### Header

Title: Vehicle Inventory

Subtitle: Manage registered vehicles and monitor their operational status.

Primary action: + Add Vehicle

### Filter Bar

- Search by Vehicle ID.
- Vehicle Class.
- Operational Status.
- Health Status.
- Manufacturer.
- Clear Filters.

### Inventory Table

Columns:

| Field | Description |
|---|---|
| Vehicle ID | Unique identifier |
| Vehicle | Manufacturer and model |
| Class | Vehicle category |
| Year | Model year |
| Mileage | Latest available reading |
| Health | Available health indicator |
| Status | Operational status |
| Next Service | Maintenance due date |
| Actions | View / Edit |

### Row Interaction

Selecting a row opens its vehicle profile.

Actions:
- View.
- Edit.
- View Maintenance.

### Add Vehicle Drawer

Fields:
- Vehicle ID.
- Manufacturer.
- Model.
- Model Year.
- Vehicle Class.
- VIN.
- Fuel Type.
- Mileage.
- Fleet Assignment.

Buttons:
- Cancel.
- Register Vehicle.

Validation:
- Required field validation.
- Duplicate vehicle identifier check.
- Valid year.
- VIN validation when supplied.

---

# 6. Screen 03 — Vehicle Details

**Route:** /vehicles/:vehicleId

### Objective

Provide a complete operational profile for an individual vehicle.

### Header

Display:
- Vehicle ID.
- Manufacturer and model.
- Vehicle class.
- Model year.
- Operational status.
- Available health indicator.

Actions:
- Edit Vehicle.
- Create Work Order.
- View Alerts.

### Navigation Tabs

1. Overview
2. Specifications
3. Telemetry
4. Diagnostics
5. Maintenance
6. Alerts
7. Predictive Insights

### Overview Tab

Top cards:
- Latest Mileage.
- Operating Hours.
- Available Health Indicator.
- Open Alerts.

Main sections:
- Vehicle Information.
- Recent Telemetry.
- Maintenance Summary.
- Recent Events.

### Specifications Tab

Display:
- VIN, if available.
- Manufacturer.
- Model.
- Model year.
- Vehicle class.
- Fuel type.
- Fleet assignment.

### Telemetry Tab

Display:
- Time-series charts.
- Metric selection.
- Date filtering.
- Source classification.
- Data quality.

### Diagnostics Tab

Display:
- Diagnostic code.
- Event description.
- Severity.
- Timestamp.
- Resolution status.

### Maintenance Tab

Display:
- Service history.
- Upcoming maintenance.
- Work orders.
- Maintenance expenditure.

### Alerts Tab

Display:
- Open alerts.
- Historical alerts.
- Severity.
- Resolution details.

### Predictive Insights Tab

Display:
- Available model-generated estimates.
- Risk category.
- Supporting observations.
- Model version.
- Prediction timestamp.
- Uncertainty information.

If predictions are unavailable, show a clear explanation.

---

# 7. Screen 04 — Telemetry Explorer

**Route:** /telemetry

### Objective

Enable users to explore historical and demonstration vehicle telemetry.

### Header

Title: Telemetry Explorer

Subtitle: Analyze vehicle operating patterns and sensor readings.

### Filter Panel

- Vehicle.
- Vehicle Class.
- Date Range.
- Data Source.
- Metric Type.

### Main Visualization

Use a large time-series chart.

Supported metrics depend on the available dataset:
- Speed.
- Engine Temperature.
- Mileage.
- Fuel Consumption.
- Battery Voltage.
- Operating Hours.

### Supporting Panels

1. Latest Available Readings.
2. Data Quality Summary.
3. Missing Data Periods.
4. Diagnostic Event Markers.
5. Source Information.

### Interactions

- Change metric.
- Compare selected measurements.
- Zoom into a reporting period.
- Inspect individual readings.
- Navigate to Vehicle Details.

Every chart must display its measurement units and source classification.

---

# 8. Screen 05 — Maintenance Overview

**Route:** /maintenance

### Objective

Provide operational visibility into maintenance activities.

### KPI Cards

- Scheduled Maintenance.
- Due Maintenance.
- Overdue Maintenance.
- Open Work Orders.

### Main Sections

#### Maintenance Calendar

Display scheduled maintenance by date.

#### Work Order Distribution

Visualization: Donut chart.

Statuses:
- Open.
- Assigned.
- In Progress.
- On Hold.
- Completed.
- Closed.

#### Maintenance Expenditure

Visualization: Line chart.

Show expenditure by reporting period when actual or clearly labeled demonstration costs are available.

#### Recent Activity

Display:
- Vehicle.
- Work Order.
- Technician.
- Status.
- Updated Time.

### Primary Actions

- Create Work Order.
- View Work Orders.
- View Service History.

---

# 9. Screen 06 — Work Order Management

**Route:** /maintenance/work-orders

### Objective

Manage vehicle maintenance tasks and assignments.

### Work Order Table

Columns:
- Work Order ID.
- Vehicle.
- Maintenance Category.
- Priority.
- Assigned Technician.
- Planned Date.
- Status.
- Actions.

### Create Work Order Form

Fields:
- Vehicle.
- Title.
- Category.
- Description.
- Priority.
- Assigned Technician.
- Planned Date.
- Estimated Cost.
- Supporting Diagnostic Event.

### Work Order Detail

Sections:
1. Work Order Summary.
2. Vehicle Information.
3. Assignment.
4. Maintenance Checklist.
5. Inspection Findings.
6. Cost Details.
7. Status History.
8. Activity Timeline.

### Status Controls

Support valid transitions:

Draft → Open → Assigned → In Progress → Completed → Reviewed → Closed.

Additional states:
- On Hold.
- Cancelled.

The backend must validate transitions.

---

# 10. Screen 07 — Predictive Intelligence

**Route:** /intelligence

### Objective

Present explainable, evidence-supported automotive intelligence.

### Dashboard Sections

- Available Risk Assessments.
- Vehicle Risk Distribution.
- Vehicles Requiring Investigation.
- Anomaly Observations.
- Model Information.
- Recent Prediction History.

### Vehicle Risk Detail

Display:
- Vehicle identifier.
- Risk category.
- Risk score, if validated.
- Prediction timestamp.
- Model version.
- Contributing factors.
- Supporting telemetry.
- Confidence and uncertainty.
- Data quality.

### Design Rule

Never use predictive risk as a confirmed diagnosis.

Predictions must be clearly separated from observed diagnostic events.

---

# 11. Screen 08 — Analytics

**Route:** /analytics

### Objective

Provide operational and financial fleet performance analysis.

### Dashboard Sections

#### Fleet Performance
- Fleet availability.
- Utilization.
- Vehicle distribution.

#### Downtime
- Recorded downtime.
- Downtime trends.
- Maintenance-associated downtime.

#### Maintenance Analytics
- Expenditure.
- Preventive versus corrective maintenance.
- Service frequency.

#### Vehicle Comparison
- Vehicle class.
- Mileage.
- Utilization.
- Maintenance cost.

Only compatible metrics should be compared.

#### Reports

- Date range.
- Report type.
- Vehicle filters.
- CSV export.

---

# 12. Screen 09 — Alerts

**Route:** /alerts

### Objective

Provide a centralized operational alert management interface.

### Summary Cards

- Critical.
- High.
- Medium.
- Low.

### Alert Table

Columns:
- Alert ID.
- Vehicle.
- Description.
- Severity.
- Source.
- Created Time.
- Assigned User.
- Status.

### Alert Detail Drawer

Display:
- Alert summary.
- Original event.
- Associated vehicle.
- Supporting evidence.
- Investigation notes.
- Assignment.
- Resolution history.

Actions:
- Acknowledge.
- Assign.
- Add Note.
- Resolve.
- Close.

All actions must be permission-controlled and auditable.

---

# 13. Screen 10 — Settings

**Route:** /settings

### Sections

- User Profile.
- User Management.
- Roles and Permissions.
- Data Sources.
- Notification Preferences.
- Audit Logs.
- Application Preferences.

Use a secondary settings navigation panel.

Administrator-only functionality must be protected by backend authorization.

---

# 14. Reusable Component Specifications

## KPI Card

Elements:
- Label.
- Value.
- Icon.
- Supporting description.
- Optional trend.

## Status Badge

Supported variants:
- Healthy.
- Operational.
- Attention.
- Critical.
- Unknown.
- In Progress.
- Completed.

## Data Table

Features:
- Sorting.
- Pagination.
- Search.
- Filters.
- Row actions.
- Responsive behavior.

## Chart Container

Elements:
- Chart title.
- Description.
- Reporting period.
- Legend.
- Tooltip.
- Source indicator.

## Empty State

Include:
- Relevant icon.
- Clear message.
- Explanation.
- Optional next action.

## Confirmation Dialog

Include:
- Action description.
- Consequence.
- Cancel.
- Confirm.

---

# 15. Responsive Design

## Desktop

Reference: 1440px and above.

- Expanded or collapsible sidebar.
- Four-column KPI layouts where space permits.
- Multi-column charts.
- Full data tables.

## Tablet

Reference: 768px–1439px.

- Collapsible sidebar.
- Two-column KPI layouts.
- Adapted data tables.
- Responsive charts.

## Mobile

Reference: Below 768px.

- Compact navigation.
- Single-column content.
- Scrollable or card-based tables.
- Essential alert information.
- Vehicle lookup.
- Assigned work orders.

All layouts must be tested at intermediate widths as well as reference widths.

---

# 16. UI States

Every primary screen must support:

### Loading
Show skeleton components or progress indicators.

### Empty
Explain why information is unavailable.

### Error
Provide actionable error feedback.

### Permission Denied
Explain that the current role cannot perform the requested operation.

### Stale Data
Display the last successful update timestamp.

### Data Quality Warning
Identify missing, invalid, or incomplete information.

### Demonstration Data
Show a persistent demonstration-data indicator.

### Prediction Unavailable
Explain when model outputs are not available or validated.

---

# 17. Accessibility Requirements

- Keyboard navigation.
- Visible focus indicators.
- Sufficient text contrast.
- Semantic headings.
- Accessible labels.
- Form error descriptions.
- Chart descriptions.
- Non-color status identification.
- Screen-reader-friendly tables.

Target WCAG 2.2 AA.

---

# 18. Frontend Implementation Guidance

Recommended frontend stack:

- React.
- TypeScript.
- Vite.
- Tailwind CSS.
- shadcn/ui.
- Recharts.
- Lucide icons.
- React Router.
- TanStack Query.
- React Hook Form.
- Zod.

These are proposed technology choices and can be adjusted during architecture design.

### Suggested frontend structure

```text
src/
├── app/
│   ├── App.tsx
│   ├── router.tsx
│   └── providers/
│
├── components/
│   ├── layout/
│   ├── navigation/
│   ├── dashboard/
│   ├── charts/
│   ├── tables/
│   ├── forms/
│   └── ui/
│
├── features/
│   ├── overview/
│   ├── vehicles/
│   ├── telemetry/
│   ├── maintenance/
│   ├── intelligence/
│   ├── analytics/
│   ├── alerts/
│   └── settings/
│
├── hooks/
├── services/
├── types/
├── utils/
├── styles/
└── main.tsx
```

### Development sequence

1. Establish application shell.
2. Build sidebar and topbar.
3. Implement design tokens.
4. Create reusable UI components.
5. Build Fleet Command Center.
6. Build Vehicle Inventory.
7. Build Vehicle Details.
8. Build Telemetry Explorer.
9. Build Maintenance.
10. Build Predictive Intelligence.
11. Build Analytics.
12. Build Alerts.
13. Build Settings.
14. Integrate backend APIs.
15. Add authentication and permissions.
16. Validate responsive behavior.

Use mock data initially, with clear source labeling. Do not hardcode demonstration data into production API services.

---

# 19. UI Acceptance Criteria

The interface is considered ready for frontend implementation when:

- All ten primary screens are specified.
- Sidebar and topbar are defined.
- Design tokens are documented.
- Reusable components are identified.
- Primary interactions are documented.
- Loading and error states are defined.
- Responsive behavior is specified.
- Accessibility requirements are documented.
- Demonstration and historical data are clearly labeled.
- Predictive outputs are distinguished from observed information.

---

# 20. Next Deliverable

**06-design-system.md**

The next document will formalize the reusable visual system:

- Design tokens.
- Component library.
- Button variants.
- Form components.
- Tables.
- Cards.
- Navigation.
- Chart conventions.
- Iconography.
- Responsive rules.
- Component states.
- Frontend styling standards.

**End of document.**
