
# AutoPulse AI — Information Architecture

**Document ID:** AP-IA-004  
**Version:** 1.0  
**Status:** Initial architecture baseline  
**Parent Documents:**
- 01-product-discovery.md
- 02-personas-and-user-journeys.md
- 03-functional-requirements.md

---

## 1. Purpose

Define the structural organization of AutoPulse AI, including application navigation, page hierarchy, screen relationships, reusable layouts, and user interaction entry points.

This document establishes the blueprint for the frontend application and subsequent detailed UI/UX specifications.

## 2. Application Structure

AutoPulse AI will use a modular application structure with a centralized operational dashboard.

### Primary application modules

1. Overview
2. Vehicles
3. Telemetry Explorer
4. Maintenance
5. Predictive Intelligence
6. Analytics
7. Alerts
8. Settings

### Application layout

The application will use three primary layout regions:

- Left sidebar: Primary navigation.
- Top navigation: Search, notifications, user profile, and contextual controls.
- Main workspace: Dashboard, tables, charts, forms, and detailed content.

## 3. Global Navigation

### 3.1 Primary Sidebar

| Order | Navigation | Route | Icon concept |
|---|---|---|---|
| 01 | Overview | /overview | Layout dashboard |
| 02 | Vehicles | /vehicles | Car |
| 03 | Telemetry Explorer | /telemetry | Activity |
| 04 | Maintenance | /maintenance | Wrench |
| 05 | Predictive Intelligence | /intelligence | Brain circuit |
| 06 | Analytics | /analytics | Chart |
| 07 | Alerts | /alerts | Bell |
| 08 | Settings | /settings | Settings |

The sidebar should support:
- Expanded navigation.
- Collapsed navigation.
- Active page indicators.
- Tooltips when collapsed.
- Role-aware navigation.
- Consistent navigation across modules.

Hiding a navigation item does not replace backend authorization.

### 3.2 Top Navigation

Components:

**Global Search**
- Search vehicles.
- Search diagnostic events.
- Search work orders.
- Search alerts.

**Notification Center**
- Critical alerts.
- Maintenance reminders.
- Work-order updates.
- Data pipeline notifications.

**Data Environment Indicator**
- Demonstration environment.
- Historical dataset.
- Synthetic data.
- Connected live source, when eventually supported.

**User Profile**
- User details.
- Role.
- Account settings.
- Sign out.

### 3.3 Breadcrumb Navigation

Examples:

Overview

Vehicles > Inventory

Vehicles > Vehicle Details > Vehicle History

Maintenance > Work Orders > Work Order Details

Predictive Intelligence > Vehicle Risk Details

Breadcrumbs must reflect the actual navigation hierarchy.

---

## 4. Complete Sitemap

```text
AUTOPULSE AI
│
├── Authentication
│   ├── Login
│   ├── Forgot Password
│   └── Access Denied
│
├── Overview
│   ├── Fleet Command Center
│   ├── Fleet Health
│   ├── Fleet Availability
│   ├── Critical Alerts
│   └── Upcoming Maintenance
│
├── Vehicles
│   ├── Vehicle Inventory
│   │   ├── All Vehicles
│   │   ├── Cars
│   │   ├── Vans
│   │   └── Trucks
│   │
│   ├── Register Vehicle
│   └── Vehicle Details
│       ├── Overview
│       ├── Specifications
│       ├── Health
│       ├── Telemetry
│       ├── Diagnostics
│       ├── Maintenance History
│       ├── Alerts
│       └── Predictions
│
├── Telemetry Explorer
│   ├── Telemetry Overview
│   ├── Vehicle Readings
│   ├── Historical Trends
│   ├── Sensor Analysis
│   └── Data Quality
│
├── Maintenance
│   ├── Maintenance Overview
│   ├── Maintenance Calendar
│   ├── Work Orders
│   │   ├── All Work Orders
│   │   ├── Create Work Order
│   │   └── Work Order Details
│   ├── Service History
│   └── Maintenance Costs
│
├── Predictive Intelligence
│   ├── Risk Overview
│   ├── Vehicle Risk Analysis
│   ├── Component Risk
│   ├── Anomaly Detection
│   ├── Prediction Details
│   ├── Model Information
│   └── Prediction History
│
├── Analytics
│   ├── Fleet Performance
│   ├── Vehicle Utilization
│   ├── Downtime Analysis
│   ├── Maintenance Analytics
│   ├── Vehicle Comparison
│   └── Reports
│
├── Alerts
│   ├── All Alerts
│   ├── Critical
│   ├── Warning
│   ├── Informational
│   ├── Alert Details
│   └── Alert History
│
└── Settings
    ├── User Profile
    ├── User Management
    ├── Roles and Permissions
    ├── Data Sources
    ├── Notifications
    ├── Audit Logs
    └── Application Preferences
```

Some sections are future-facing and will be enabled only when their supporting capabilities are implemented.

---

## 5. Screen Architecture

### Screen 01 — Fleet Command Center

Route: `/overview`

Purpose: Give fleet managers an immediate operational overview.

Layout:

**Header**
- Welcome message.
- Fleet selector.
- Reporting period.
- Last updated timestamp.

**KPI row**
- Total Vehicles.
- Operational Vehicles.
- Vehicles Under Maintenance.
- Critical Alerts.

**Main dashboard**
- Fleet Health Distribution.
- Vehicle Availability Trend.
- Maintenance Overview.
- Vehicle Class Distribution.

**Lower dashboard**
- Critical Alerts.
- Upcoming Maintenance.
- Vehicles Requiring Attention.
- Recent Operational Activity.

Primary interactions:
- Select a KPI to navigate to a filtered inventory.
- Select an alert to investigate.
- Select a vehicle to open its profile.
- Change reporting period.

### Screen 02 — Vehicle Inventory

Route: `/vehicles`

Purpose: Provide a searchable fleet inventory.

Components:
- Page title.
- Add Vehicle action.
- Search field.
- Vehicle class filters.
- Operational status filters.
- Sort controls.
- Vehicle data table.
- Pagination.

Suggested columns:

| Column | Description |
|---|---|
| Vehicle ID | Unique identifier |
| Vehicle | Manufacturer and model |
| Class | Car, van, truck |
| Year | Model year |
| Mileage | Latest available mileage |
| Health | Supported health indicator |
| Status | Operational status |
| Maintenance | Next due date |
| Actions | View or edit |

Interactions:
- Open vehicle.
- Register vehicle.
- Filter inventory.
- Export supported inventory fields.

### Screen 03 — Vehicle Details

Route: `/vehicles/:vehicleId`

Purpose: Display a comprehensive individual vehicle profile.

Header:
- Vehicle identifier.
- Manufacturer and model.
- Vehicle class.
- Operational status.
- Available health indicator.
- Edit action.

Tabs:

1. Overview
2. Specifications
3. Telemetry
4. Diagnostics
5. Maintenance
6. Alerts
7. Predictive Insights

Overview sections:
- Vehicle summary.
- Latest available readings.
- Health indicators.
- Recent events.
- Maintenance schedule.

The screen must distinguish unavailable readings from actual zero measurements.

### Screen 04 — Telemetry Explorer

Route: `/telemetry`

Purpose: Explore available historical and simulated vehicle readings.

Layout:

**Filter panel**
- Vehicle selector.
- Vehicle class.
- Date range.
- Measurement type.
- Data source.

**Main workspace**
- Time-series charts.
- Metric comparison.
- Reading details.
- Event markers.

**Data quality panel**
- Missing records.
- Invalid readings.
- Data freshness.
- Source classification.

Important:
Historical and synthetic records must never be presented as live-connected telemetry.

### Screen 05 — Maintenance Overview

Route: `/maintenance`

Purpose: Provide a central view of fleet maintenance activities.

KPI section:
- Scheduled Maintenance.
- Due Maintenance.
- Overdue Maintenance.
- Open Work Orders.

Main sections:
- Maintenance calendar.
- Work-order status distribution.
- Maintenance cost trend.
- Recent maintenance activity.

Primary actions:
- Create Work Order.
- View Work Orders.
- View Service History.

### Screen 06 — Work Order Management

Route: `/maintenance/work-orders`

Purpose: Manage maintenance assignments.

Table columns:
- Work Order ID.
- Vehicle.
- Category.
- Priority.
- Assigned Technician.
- Planned Date.
- Status.
- Created Date.

Filters:
- Status.
- Priority.
- Vehicle class.
- Technician.
- Date.

Work-order detail route:

`/maintenance/work-orders/:workOrderId`

Detail sections:
- Work-order information.
- Vehicle information.
- Diagnostic references.
- Assignment.
- Inspection notes.
- Service records.
- Status history.
- Cost details.

### Screen 07 — Predictive Intelligence

Route: `/intelligence`

Purpose: Present validated model-generated operational insights.

Main sections:
- Available risk assessments.
- Risk distribution.
- Vehicle risk ranking.
- Anomaly observations.
- Model information.
- Recent prediction history.

Risk detail route:

`/intelligence/vehicles/:vehicleId`

Risk details:
- Risk category.
- Estimated score.
- Model version.
- Prediction timestamp.
- Contributing factors.
- Supporting telemetry.
- Data quality.
- Model limitations.

If validated model outputs are unavailable, display an explanatory empty state.

### Screen 08 — Analytics

Route: `/analytics`

Purpose: Enable fleet-level performance analysis.

Sections:

**Fleet Performance**
- Fleet availability.
- Vehicle utilization.
- Operational trends.

**Maintenance Analytics**
- Maintenance expenditure.
- Preventive versus corrective maintenance.
- Service frequency.

**Downtime Analysis**
- Recorded downtime.
- Vehicle downtime trends.
- Maintenance-related downtime.

**Vehicle Comparison**
- Vehicle class comparison.
- Compatible vehicle metric comparison.

**Reports**
- Report selection.
- Date filters.
- CSV export.

### Screen 09 — Alerts

Route: `/alerts`

Purpose: Provide a centralized alert investigation workspace.

Alert table:
- Alert ID.
- Vehicle.
- Alert category.
- Severity.
- Source.
- Created time.
- Assigned user.
- Status.

Alert detail route:

`/alerts/:alertId`

Detail sections:
- Alert summary.
- Original event.
- Associated vehicle.
- Supporting evidence.
- Investigation notes.
- Assignment.
- Resolution history.

### Screen 10 — Settings

Route: `/settings`

Sections:
- Profile.
- User Management.
- Roles and Permissions.
- Data Sources.
- Notification Preferences.
- Audit Logs.
- Application Preferences.

Access must be controlled by administrator permissions.

---

## 6. Global Reusable Components

The frontend should use reusable components rather than independently building every screen.

### Navigation components
- Sidebar.
- Topbar.
- Breadcrumb.
- Navigation item.
- Notification panel.
- User menu.

### Data components
- KPI card.
- Data table.
- Search input.
- Filter dropdown.
- Date selector.
- Status badge.
- Pagination.
- Empty state.

### Visualization components
- Line chart.
- Bar chart.
- Donut chart.
- Area chart.
- Metric comparison.
- Trend indicator.

### Operational components
- Vehicle status card.
- Health indicator.
- Alert card.
- Diagnostic event card.
- Maintenance task card.
- Work-order status tracker.
- Prediction explanation panel.

### Form components
- Vehicle registration form.
- Work-order form.
- Technician assignment selector.
- Alert investigation form.
- Confirmation dialog.

---

## 7. Global Interaction Patterns

### Search

Global search should support:
- Vehicle ID.
- Work-order ID.
- Alert ID.
- Supported vehicle identifiers.

### Filtering

Filters should:
- Be visible.
- Support multiple criteria where appropriate.
- Allow clearing.
- Preserve relevant context when navigating.

### Data tables

Tables should support:
- Sorting.
- Pagination.
- Filtering.
- Row selection where necessary.
- Responsive behavior.

### Confirmation

Require confirmation for important operations:
- Deactivating users.
- Cancelling work orders.
- Closing critical alerts.
- Deleting permitted records.

### Feedback

All actions must provide:
- Loading feedback.
- Success feedback.
- Validation feedback.
- Failure feedback.

---

## 8. Screen-to-API Dependencies

| Screen | Required API domain |
|---|---|
| Overview | Fleet, Analytics, Alerts, Maintenance |
| Vehicles | Vehicle, Fleet |
| Vehicle Details | Vehicle, Telemetry, Diagnostics, Maintenance |
| Telemetry | Telemetry, Data Quality |
| Maintenance | Maintenance, Work Orders |
| Predictive Intelligence | Predictions, Models |
| Analytics | Analytics, Reports |
| Alerts | Alerts, Diagnostics |
| Settings | Users, Roles, Configuration |

Detailed endpoints will be documented in 09-api-specification.md.

---

## 9. Responsive Layout Strategy

### Desktop
- Full sidebar.
- Multi-column dashboard.
- Detailed data tables.
- Large analytical visualizations.

### Tablet
- Collapsible sidebar.
- Two-column KPI layouts.
- Adapted tables.
- Responsive charts.

### Mobile
- Compact navigation.
- Essential alert information.
- Vehicle lookup.
- Assigned work orders.
- Basic maintenance updates.

The first development priority is a polished desktop and tablet experience.

---

## 10. Navigation Rules

1. The Overview page is the default authenticated landing page.
2. Vehicle details can be opened from inventory, alerts, analytics, and maintenance.
3. Work orders must link back to their associated vehicles.
4. Alerts must link to their original diagnostic or operational events when available.
5. Prediction details must link to supporting observations.
6. Breadcrumbs must reflect actual page hierarchy.
7. Unauthorized routes must display an access-denied experience.
8. Missing records must display a useful not-found state.

---

## 11. Information Architecture Acceptance Criteria

- Every MVP feature has an assigned application module.
- All primary routes are documented.
- All major screens have defined content sections.
- Primary navigation is consistent.
- User journeys have corresponding screen paths.
- Screen-to-API dependencies are identified.
- Reusable components are specified.
- Responsive behavior is documented.
- Future-facing modules are distinguishable from implemented functionality.

---

## 12. Outstanding Decisions

- Exact sidebar branding and typography.
- Whether vehicle details use tabs or a secondary navigation panel.
- Which filters should persist across sessions.
- Dashboard widget customization.
- Global search behavior.
- Mobile navigation design.
- Initial report templates.
- Notification interaction patterns.

---

## 13. Next Deliverable

**05-ui-ux-design-specification.md**

The next document will define the actual screen designs in detail:

- Visual layout for every primary page.
- Exact component placement.
- Screen dimensions and spacing.
- Typography hierarchy.
- Color specifications.
- Tables and chart specifications.
- Form field definitions.
- Loading, empty, and error states.
- Interaction behavior.
- Responsive design.
- Frontend implementation guidance.

The objective is to turn this information architecture into an implementation-ready interface blueprint.

---

**End of document.**
