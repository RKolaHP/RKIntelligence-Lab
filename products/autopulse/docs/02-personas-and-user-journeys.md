
# AutoPulse AI — Personas and User Journeys

**Document ID:** AP-UX-002  
**Version:** 1.0  
**Status:** Initial UX specification  
**Parent Document:** 01-product-discovery.md

---

## 1. Purpose

Define the primary users, their responsibilities, application interactions, and end-to-end workflows for AutoPulse AI.

This document establishes the foundation for information architecture, wireframes, and detailed UI specifications.

## 2. User Roles

| Role | Access | Main responsibility |
|---|---|---|
| Fleet Manager | Fleet-wide | Monitor fleet operations |
| Maintenance Manager | Fleet and maintenance | Plan and coordinate maintenance |
| Fleet Analyst | Analytics and data | Analyze fleet performance |
| Service Technician | Assigned vehicles and work orders | Execute vehicle inspections and maintenance |
| Administrator | Configuration | Manage users, roles, and settings |

## 3. Detailed Personas

### Persona 01 — Fleet Manager

**Objective:** Maintain fleet availability and operational efficiency.

Pain points:
- Multiple vehicle types and operational records.
- Difficulty identifying vehicles requiring attention.
- Limited visibility into maintenance activities.
- Difficulty comparing fleet performance.

Application needs:
- Fleet Command Center.
- Vehicle inventory.
- Fleet health indicators.
- Critical alerts.
- Utilization analytics.

Key workflow:
1. Sign in.
2. Open Overview.
3. Review fleet KPIs.
4. Identify vehicles requiring attention.
5. Open vehicle profiles.
6. Review alerts.
7. Coordinate maintenance.

Success outcome: Quickly understand fleet status and identify operational priorities.

### Persona 02 — Maintenance Manager

**Objective:** Coordinate preventive and corrective maintenance.

Pain points:
- Overdue service activities.
- Incomplete vehicle histories.
- Unclear maintenance priorities.
- Difficulty tracking work orders.

Application needs:
- Maintenance dashboard.
- Service calendar.
- Work-order management.
- Diagnostic events.
- Maintenance cost analytics.

Key workflow:
1. Open Maintenance.
2. Review due and overdue services.
3. Investigate vehicle health.
4. Review diagnostic information.
5. Create a work order.
6. Assign a technician.
7. Track completion.

Success outcome: Maintain a traceable maintenance process.

### Persona 03 — Fleet Analyst

**Objective:** Understand fleet performance using operational data.

Pain points:
- Inconsistent source data.
- Limited historical comparisons.
- Difficulties measuring utilization and downtime.

Application needs:
- Analytics dashboard.
- Historical telemetry.
- Data-quality indicators.
- Cost and utilization reports.
- Export capabilities.

Key workflow:
1. Open Analytics.
2. Select reporting period.
3. Filter vehicle classes.
4. Review utilization and maintenance trends.
5. Investigate anomalies.
6. Export findings.

Success outcome: Produce reliable operational insights.

### Persona 04 — Service Technician

**Objective:** Complete assigned vehicle inspections and service tasks.

Pain points:
- Incomplete vehicle history.
- Unclear inspection requirements.
- Poor visibility into previous maintenance.

Application needs:
- Assigned work orders.
- Vehicle details.
- Diagnostic information.
- Inspection checklist.
- Service history.

Key workflow:
1. Open assigned tasks.
2. Select vehicle.
3. Review vehicle history.
4. Perform inspection.
5. Record findings.
6. Update work-order status.
7. Submit completion details.

Success outcome: Complete maintenance work with traceable records.

### Persona 05 — Administrator

**Objective:** Maintain application configuration and user access.

Application needs:
- User management.
- Role assignments.
- Access permissions.
- Data-source configuration.
- Audit logs.

Key workflow:
1. Open Settings.
2. Create or update user.
3. Assign role.
4. Configure permissions.
5. Review access history.

Success outcome: Maintain controlled and auditable application access.

---

## 4. Information Architecture

### Primary navigation

1. Overview
2. Vehicles
3. Telemetry Explorer
4. Maintenance
5. Predictive Intelligence
6. Analytics
7. Alerts
8. Settings

### Navigation hierarchy

#### Overview
- Fleet summary
- Vehicle availability
- Fleet health distribution
- Critical alerts
- Upcoming maintenance
- Utilization trends

#### Vehicles
- Vehicle inventory
- Vehicle details
- Vehicle health
- Vehicle telemetry
- Diagnostic history
- Maintenance history

#### Telemetry Explorer
- Historical readings
- Sensor selection
- Time-series visualization
- Diagnostic events
- Data-quality status
- Source information

#### Maintenance
- Maintenance overview
- Maintenance calendar
- Work orders
- Service history
- Maintenance costs

#### Predictive Intelligence
- Risk overview
- Component risk
- Anomaly detection
- Prediction history
- Model explanations

#### Analytics
- Fleet utilization
- Vehicle downtime
- Maintenance expenditure
- Vehicle comparisons
- Reports

#### Alerts
- Critical alerts
- Warning alerts
- Informational events
- Alert history
- Resolution tracking

#### Settings
- User management
- Role management
- Data sources
- Notification preferences
- Audit history

---

## 5. Primary User Journeys

### Journey 01 — Fleet Overview

**User:** Fleet Manager

1. User signs in.
2. System displays Fleet Command Center.
3. User reviews total vehicles.
4. User reviews operational availability.
5. User examines fleet health distribution.
6. User identifies critical alerts.
7. User opens a vehicle requiring attention.
8. System displays vehicle-specific information.

Expected outcome: Fleet-wide visibility and issue identification.

### Journey 02 — Vehicle Investigation

**User:** Fleet Manager / Maintenance Manager

1. User opens Vehicles.
2. User searches by vehicle identifier.
3. User selects a vehicle.
4. System displays vehicle profile.
5. User reviews mileage and operating hours.
6. User examines available telemetry.
7. User reviews diagnostic events.
8. User checks maintenance history.
9. User determines whether further inspection is needed.

Expected outcome: Complete vehicle investigation using available evidence.

### Journey 03 — Maintenance Work Order

**User:** Maintenance Manager

1. User opens Maintenance.
2. User selects a vehicle.
3. User reviews service history.
4. User selects Create Work Order.
5. User enters maintenance category.
6. User enters description and priority.
7. User assigns a technician.
8. User selects planned service date.
9. User submits the work order.
10. System records the work order.

Expected outcome: Traceable maintenance assignment.

### Journey 04 — Complete Maintenance

**User:** Service Technician

1. Technician opens assigned work orders.
2. Technician selects an assignment.
3. Technician reviews vehicle details.
4. Technician performs inspection.
5. Technician records findings.
6. Technician enters service details.
7. Technician updates work-order status.
8. Maintenance Manager reviews completion.
9. System updates maintenance history.

Expected outcome: Recorded service completion.

### Journey 05 — Investigate Predictive Risk

**User:** Maintenance Manager / Fleet Analyst

1. User opens Predictive Intelligence.
2. User selects a vehicle.
3. System displays an available model-generated risk estimate.
4. User reviews the contributing factors.
5. User examines supporting telemetry.
6. User reviews model confidence and data quality.
7. User decides whether inspection is appropriate.
8. User optionally creates a maintenance work order.

Expected outcome: Human-reviewed, explainable maintenance investigation.

Important: If a validated model or suitable data is unavailable, the interface must clearly indicate that predictive results are unavailable rather than generate fabricated predictions.

### Journey 06 — Fleet Performance Analysis

**User:** Fleet Analyst

1. User opens Analytics.
2. User selects a reporting period.
3. User selects vehicle class.
4. User reviews fleet utilization.
5. User compares downtime.
6. User reviews maintenance expenditure.
7. User identifies trends.
8. User exports the report.

Expected outcome: Actionable fleet performance reporting.

### Journey 07 — Alert Investigation

**User:** Fleet Manager / Maintenance Manager

1. User opens Alerts.
2. User filters by severity.
3. User selects an alert.
4. System displays event details.
5. User opens the associated vehicle.
6. User reviews supporting diagnostic information.
7. User acknowledges or assigns the issue.
8. User tracks resolution.

Expected outcome: Traceable alert management.

---

## 6. Screen-to-Role Mapping

| Screen | Fleet Manager | Maintenance Manager | Analyst | Technician |
|---|---|---|---|---|
| Overview | Primary | Secondary | Secondary | — |
| Vehicles | Primary | Primary | Read | Assigned |
| Telemetry | Read | Primary | Primary | Read |
| Maintenance | Read | Primary | Read | Assigned |
| Predictive AI | Read | Primary | Primary | — |
| Analytics | Primary | Read | Primary | — |
| Alerts | Primary | Primary | Read | Assigned |
| Settings | Admin | — | — | — |

Access permissions must be enforced by the backend, not merely hidden in the frontend.

---

## 7. Important Interaction States

Every major screen must define the following states:

- Loading.
- Successful data retrieval.
- Empty results.
- No available telemetry.
- Stale data.
- Data-quality warning.
- API failure.
- Permission denied.
- Invalid form input.
- Successful submission.
- Failed submission.

Examples:

**No telemetry available**

"Telemetry is not available for this vehicle or selected period."

**Synthetic data**

"Demonstration data — simulated vehicle readings."

**Historical public data**

"Historical dataset — not a live vehicle connection."

**Prediction unavailable**

"Insufficient validated data to generate a reliable prediction."

---

## 8. Work Order Lifecycle

Proposed workflow:

1. Draft
2. Open
3. Assigned
4. In Progress
5. Completed
6. Reviewed
7. Closed

Additional states:
- Cancelled
- On Hold

Every transition should be recorded with the user, timestamp, and relevant notes.

---

## 9. Alert Lifecycle

Proposed workflow:

1. Detected
2. Open
3. Acknowledged
4. Assigned
5. Under Investigation
6. Resolved
7. Closed

Alerts should retain their original event details even after resolution.

---

## 10. UX Design Principles

### Navigation
- Keep navigation consistent.
- Show active sections clearly.
- Preserve useful filter context when navigating between related screens.

### Data visualization
- Use appropriate chart types.
- Include units and date ranges.
- Avoid unnecessary chart decoration.
- Allow users to inspect supporting information.

### Forms
- Use clear labels.
- Validate required information.
- Provide actionable error messages.
- Confirm important actions.

### Responsive design
- Desktop: Full operational workspace.
- Tablet: Adapted navigation and dashboards.
- Mobile: Essential alerts, vehicle lookup, and assigned work orders.

### Accessibility
- Keyboard navigation.
- Accessible contrast.
- Text labels for status.
- Clear focus states.
- Accessible chart descriptions.

---

## 11. Initial UX Acceptance Criteria

- Every primary persona has a defined workflow.
- Fleet managers can reach vehicle details from the overview.
- Maintenance managers can create and track work orders.
- Technicians can record service completion.
- Analysts can filter and export reports.
- Users can investigate alerts.
- Predictions are distinguishable from observed readings.
- Synthetic and historical data are labeled.
- Empty, loading, and error states are specified.
- Navigation is consistent across all primary screens.

---

## 12. Outstanding Design Decisions

- Exact fleet size for demonstration.
- Initial vehicle inventory.
- Maintenance priority rules.
- Work-order assignment rules.
- Alert severity thresholds.
- Vehicle-specific telemetry availability.
- Dashboard KPI definitions.
- Report export formats.
- GPS and location-data scope.
- User authentication approach.

These will be resolved during screen specification and technical architecture.

---

## 13. Next Design Phase

The next document will be:

**03-functional-requirements.md**

It will contain:
- Detailed feature requirements.
- User stories.
- Acceptance criteria.
- Business rules.
- Field-level requirements.
- Validation rules.
- Permission matrix.
- Functional dependencies.
- MVP prioritization.

**End of document.**
