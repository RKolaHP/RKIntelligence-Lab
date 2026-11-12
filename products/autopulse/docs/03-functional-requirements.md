
# AutoPulse AI — Functional Requirements and Business Rules

**Document ID:** AP-FR-003  
**Version:** 1.0  
**Status:** Initial requirements baseline  
**Parent Documents:** 01-product-discovery.md, 02-personas-and-user-journeys.md

---

## 1. Purpose

Define the functional requirements, business rules, application behavior, validation requirements, user permissions, and acceptance criteria for AutoPulse AI.

This document serves as the functional contract between product design, frontend engineering, backend engineering, data engineering, and AI/ML development.

## 2. Product Scope

AutoPulse AI supports fleet operators managing:
- Passenger cars
- Vans and light commercial vehicles
- Trucks and heavy commercial vehicles

The application provides:
- Fleet management
- Vehicle intelligence
- Telemetry exploration
- Maintenance management
- Predictive intelligence
- Fleet analytics
- Alert management
- User administration

## 3. Requirement Priorities

| Priority | Meaning |
|---|---|
| P0 | Essential for the MVP |
| P1 | Important for the initial release |
| P2 | Future enhancement |

## 4. Authentication and User Management

### FR-AUTH-001 — User Login
Priority: P0

Users must authenticate before accessing protected application functionality.

Acceptance criteria:
- Users can submit valid credentials.
- Invalid credentials display an appropriate error.
- Protected pages cannot be accessed without authorization.
- Sessions must expire according to security policy.

### FR-AUTH-002 — Role-Based Access
Priority: P0

The application must support:
- Fleet Manager
- Maintenance Manager
- Fleet Analyst
- Service Technician
- Administrator

Acceptance criteria:
- Each user has an assigned role.
- Permissions are enforced by the backend.
- Unauthorized operations are rejected.
- Role changes are auditable.

### FR-AUTH-003 — User Administration
Priority: P1

Administrators can:
- Create users.
- Update user details.
- Assign roles.
- Deactivate accounts.
- Review access history.

## 5. Fleet Management

### FR-FLEET-001 — Fleet Overview
Priority: P0

Display:
- Total vehicles.
- Active vehicles.
- Available vehicles.
- Vehicles under maintenance.
- Vehicles unavailable.
- Critical alerts.
- Upcoming maintenance.

Acceptance criteria:
- KPIs reflect the selected fleet and reporting period.
- KPI definitions are documented.
- Counts are derived from valid vehicle records.
- Unavailable source information is not presented as zero.

### FR-FLEET-002 — Fleet Inventory
Priority: P0

Users can:
- View registered vehicles.
- Search by vehicle identifier.
- Filter by vehicle class.
- Filter by operational status.
- Sort vehicle records.
- Open individual vehicle profiles.

### FR-FLEET-003 — Vehicle Registration
Priority: P0

Authorized users can register a vehicle.

Required fields:
- Vehicle identifier.
- Vehicle class.
- Manufacturer.
- Model.
- Model year.
- Fleet assignment.

Optional fields:
- VIN.
- Fuel type.
- Registration date.
- Mileage.
- Operating hours.

Validation:
- Vehicle identifier must be unique within its defined fleet scope.
- Model year must be valid.
- Required fields cannot be empty.
- VIN format must be validated when provided.

### FR-FLEET-004 — Vehicle Updates
Priority: P0

Authorized users can update vehicle information.

Every material change should retain an audit record.

## 6. Vehicle Intelligence

### FR-VEH-001 — Vehicle Profile
Priority: P0

Each vehicle must have a detailed profile.

Profile sections:
1. Vehicle information.
2. Operational status.
3. Available health indicators.
4. Telemetry summary.
5. Diagnostic history.
6. Maintenance history.
7. Alerts.
8. Predictions, when available.

### FR-VEH-002 — Vehicle Classification
Priority: P0

Support:
- Passenger car.
- Van.
- Light commercial vehicle.
- Heavy commercial vehicle.
- Other configurable categories.

### FR-VEH-003 — Vehicle History
Priority: P1

Users can inspect:
- Status changes.
- Maintenance events.
- Diagnostic events.
- Recorded mileage.
- Relevant alerts.

Historical records must not be overwritten when new events arrive.

## 7. Telemetry Intelligence

### FR-TEL-001 — Telemetry Ingestion
Priority: P0

The platform must accept supported vehicle telemetry from approved public datasets and synthetic data sources.

Potential fields:
- Vehicle identifier.
- Event timestamp.
- Mileage.
- Vehicle speed.
- Engine temperature.
- Engine operating hours.
- Fuel consumption.
- Battery voltage.
- Diagnostic codes.

Field availability depends on the source and vehicle class.

### FR-TEL-002 — Historical Telemetry
Priority: P0

Users can:
- Select a vehicle.
- Select a date range.
- Select available metrics.
- View historical readings.
- Inspect missing-data periods.

### FR-TEL-003 — Data Source Identification
Priority: P0

Each record must identify its provenance.

Supported classifications:
- Public dataset.
- Synthetic dataset.
- Future live-connected source.

Historical or synthetic data must never be labeled as live telemetry.

### FR-TEL-004 — Telemetry Quality
Priority: P0

The application must identify:
- Missing readings.
- Duplicate readings.
- Invalid values.
- Unexpected units.
- Delayed records.
- Schema inconsistencies.

### FR-TEL-005 — Telemetry Visualization
Priority: P1

Display appropriate time-series charts with:
- Metric name.
- Measurement unit.
- Timestamp.
- Reporting period.
- Data source.
- Quality indicators.

## 8. Diagnostic Intelligence

### FR-DIAG-001 — Diagnostic Events
Priority: P0

Users can inspect available diagnostic events associated with vehicles.

Each event should support:
- Event identifier.
- Vehicle identifier.
- Diagnostic code, if available.
- Description.
- Event timestamp.
- Source.
- Severity.
- Resolution status.

### FR-DIAG-002 — Diagnostic History
Priority: P1

Users can filter diagnostic history by:
- Vehicle.
- Date.
- Severity.
- Diagnostic category.
- Resolution status.

The system must distinguish actual diagnostic codes from simulated demonstration events.

## 9. Maintenance Management

### FR-MNT-001 — Maintenance Schedule
Priority: P0

Users can view:
- Upcoming maintenance.
- Due maintenance.
- Overdue maintenance.
- Completed maintenance.

### FR-MNT-002 — Maintenance Work Orders
Priority: P0

Authorized users can create work orders.

Required fields:
- Vehicle.
- Work-order title.
- Maintenance category.
- Description.
- Priority.
- Planned date.

Optional fields:
- Assigned technician.
- Estimated cost.
- Notes.
- Supporting diagnostic event.

### FR-MNT-003 — Work-Order Assignment
Priority: P0

Maintenance Managers can assign work orders to technicians.

### FR-MNT-004 — Work-Order Status
Priority: P0

Supported statuses:
- Draft.
- Open.
- Assigned.
- In Progress.
- On Hold.
- Completed.
- Reviewed.
- Closed.
- Cancelled.

Invalid status transitions must be rejected.

### FR-MNT-005 — Service Records
Priority: P0

Completed work orders must retain:
- Vehicle.
- Work performed.
- Technician.
- Completion date.
- Recorded cost, if available.
- Inspection findings.
- Supporting notes.

### FR-MNT-006 — Maintenance Analytics
Priority: P1

Calculate:
- Maintenance expenditure.
- Service frequency.
- Preventive maintenance distribution.
- Corrective maintenance distribution.
- Downtime associated with recorded maintenance.

Metrics must be based on documented definitions.

## 10. Predictive Intelligence

### FR-AI-001 — Vehicle Risk Assessment
Priority: P1

Display risk estimates only when a validated model and sufficient supporting data are available.

Potential outputs:
- Risk category.
- Estimated risk score.
- Prediction timestamp.
- Model version.
- Relevant input factors.
- Confidence or uncertainty information.

### FR-AI-002 — Anomaly Detection
Priority: P1

Identify unusual patterns in supported telemetry.

Examples:
- Unusual temperature readings.
- Abnormal operating patterns.
- Unexpected changes in sensor measurements.

### FR-AI-003 — Model Explainability
Priority: P1

Users must be able to inspect:
- Factors influencing predictions.
- Supporting observations.
- Model version.
- Prediction limitations.
- Data quality context.

### FR-AI-004 — Human Review
Priority: P0

AI-generated recommendations must not automatically initiate mechanical repairs or override human decisions.

Users must review and approve operational maintenance actions.

### FR-AI-005 — Prediction History
Priority: P2

Store prediction history for:
- Model evaluation.
- Historical comparison.
- Auditability.
- Model monitoring.

## 11. Alert Management

### FR-ALT-001 — Alert Generation
Priority: P0

Alerts may originate from:
- Diagnostic events.
- Data-quality failures.
- Maintenance deadlines.
- Validated anomaly detection.
- Validated predictive models.

### FR-ALT-002 — Alert Severity
Priority: P0

Supported severity levels:
- Critical.
- High.
- Medium.
- Low.
- Informational.

Severity thresholds must be configurable and documented.

### FR-ALT-003 — Alert Management
Priority: P0

Authorized users can:
- View alerts.
- Filter alerts.
- Acknowledge alerts.
- Assign alerts.
- Add investigation notes.
- Resolve alerts.
- Review alert history.

### FR-ALT-004 — Alert Traceability
Priority: P0

Each alert must retain:
- Alert identifier.
- Source event.
- Vehicle.
- Severity.
- Creation timestamp.
- Current status.
- Resolution information.

## 12. Analytics and Reporting

### FR-ANL-001 — Fleet Analytics
Priority: P0

Provide:
- Fleet availability.
- Vehicle utilization.
- Vehicle distribution.
- Downtime.
- Maintenance expenditure.

### FR-ANL-002 — Vehicle Comparison
Priority: P1

Allow comparisons across compatible vehicle groups.

Only comparable metrics should be compared.

### FR-ANL-003 — Date Filtering
Priority: P0

Users can filter supported analytics by date range.

### FR-ANL-004 — Report Export
Priority: P1

Allow authorized users to export supported reports in CSV format.

### FR-ANL-005 — KPI Definitions
Priority: P0

Every KPI must have:
- Name.
- Business definition.
- Calculation logic.
- Unit.
- Source.
- Refresh frequency.

## 13. Data Administration

### FR-DATA-001 — Data Source Registry
Priority: P0

Maintain:
- Source name.
- Source type.
- Dataset version.
- Source reference.
- Import date.
- License information.
- Data classification.

### FR-DATA-002 — Data Ingestion Monitoring
Priority: P1

Display:
- Pipeline execution status.
- Records processed.
- Records rejected.
- Processing duration.
- Failure details.

### FR-DATA-003 — Data Quality Reporting
Priority: P0

Expose quality indicators for:
- Completeness.
- Uniqueness.
- Validity.
- Consistency.
- Referential integrity.

## 14. Business Rules

| Rule ID | Business rule |
|---|---|
| BR-001 | Every vehicle must have a unique application identifier. |
| BR-002 | Vehicle classes must support optional vehicle-specific attributes. |
| BR-003 | All event timestamps must follow a documented timezone convention. |
| BR-004 | Missing measurements must not be silently converted to zero. |
| BR-005 | Every imported dataset must have source provenance. |
| BR-006 | Synthetic records must remain identifiable. |
| BR-007 | Historical records must be retained according to the retention policy. |
| BR-008 | Work orders must follow valid status transitions. |
| BR-009 | Completed work orders must retain completion information. |
| BR-010 | Predictions must identify model version and generation time. |
| BR-011 | Predictions cannot be represented as confirmed mechanical faults. |
| BR-012 | Unauthorized users cannot execute restricted operations. |
| BR-013 | Every critical operational change must be auditable. |
| BR-014 | KPIs must use documented calculation definitions. |
| BR-015 | Vehicle comparisons must account for incompatible measurements. |

## 15. Permission Matrix

Legend:
- C = Create
- R = Read
- U = Update
- D = Delete
- — = No access

| Module | Fleet Manager | Maintenance Manager | Analyst | Technician | Admin |
|---|---|---|---|---|---|
| Fleet overview | R | R | R | — | R |
| Vehicle inventory | R | R | R | R | C/R/U |
| Vehicle registration | — | C/U | — | — | C/U |
| Telemetry | R | R | R | R | R |
| Maintenance schedules | R | C/R/U | R | R | R |
| Work orders | R | C/R/U | R | R/U* | R |
| Predictive intelligence | R | R | R | — | R |
| Analytics | R | R | R | — | R |
| Alerts | R/U | R/U | R | R/U* | R |
| User management | — | — | — | — | C/R/U/D |
| Configuration | — | — | — | — | C/R/U |

*Technician updates are limited to assigned work orders and permitted alert actions.

This is a proposed permission baseline. Actual backend authorization must be specified in the API and security design.

## 16. Form Validation Rules

### Vehicle registration
- Vehicle identifier: required.
- Vehicle class: required.
- Manufacturer: required.
- Model: required.
- Model year: valid year.
- VIN: optional, format checked when supplied.

### Work-order creation
- Vehicle: required.
- Title: required.
- Category: required.
- Priority: required.
- Planned date: valid date.
- Assignment: must reference an active authorized technician when provided.

### Alert resolution
- Alert: must exist.
- Resolution action: required.
- Resolution notes: required for configured critical alert categories.
- User must have appropriate permissions.

## 17. Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-001 | Secure communication through HTTPS. |
| NFR-002 | Backend-enforced authorization. |
| NFR-003 | Audit logging for sensitive operations. |
| NFR-004 | Responsive desktop and tablet interface. |
| NFR-005 | Pagination for large datasets. |
| NFR-006 | Efficient filtering and search. |
| NFR-007 | Observable API and pipeline failures. |
| NFR-008 | Accessible forms and navigation. |
| NFR-009 | Configurable data retention. |
| NFR-010 | Documented backup and recovery strategy. |

Specific performance and availability targets will be defined after infrastructure selection.

## 18. MVP Scope

### P0 — Initial MVP
- Authentication and roles.
- Fleet overview.
- Vehicle inventory.
- Vehicle profiles.
- Historical telemetry exploration.
- Data provenance.
- Data-quality reporting.
- Maintenance schedules.
- Work-order creation and tracking.
- Alert management.
- Basic fleet analytics.

### P1 — Enhanced MVP
- Diagnostic intelligence.
- Predictive risk assessment.
- Anomaly detection.
- Model explanations.
- Advanced analytics.
- Report exports.
- Pipeline monitoring.

### P2 — Future
- Advanced fleet comparisons.
- Prediction history and monitoring.
- Configurable alert policies.
- Live vehicle integrations.
- Advanced maintenance optimization.

## 19. Functional Acceptance Criteria

The initial MVP must demonstrate that:

1. An authorized user can sign in.
2. A Fleet Manager can inspect the fleet overview.
3. A user can register and search for vehicles.
4. Users can inspect vehicle profiles.
5. Historical telemetry can be explored.
6. Public and synthetic data are distinguishable.
7. Data-quality exceptions are visible.
8. Maintenance Managers can create work orders.
9. Technicians can update assigned work orders.
10. Users can inspect and resolve alerts.
11. Users can review basic fleet analytics.
12. Backend permissions prevent unauthorized operations.
13. Important changes are recorded in audit history.

## 20. Dependencies

| Dependency | Required for |
|---|---|
| Product discovery | Scope and business context |
| Personas and journeys | Workflow definitions |
| Information architecture | Navigation and screen organization |
| UI/UX specifications | Frontend implementation |
| Database design | Persistent application data |
| API specification | Frontend/backend integration |
| Data engineering | Telemetry and analytical datasets |
| Security design | Authentication and authorization |
| Testing strategy | Acceptance and release validation |

## 21. Outstanding Decisions

The following remain open:

- Initial demonstration fleet size.
- Exact vehicle inventory.
- Vehicle identifier conventions.
- Supported diagnostic-code standards.
- Telemetry retention requirements.
- Maintenance scheduling rules.
- Alert threshold definitions.
- KPI calculation formulas.
- Authentication provider.
- Initial deployment environment.
- Supported export formats.

No unresolved decision should be silently converted into an implementation assumption.

## 22. Next Deliverable

**04-information-architecture.md**

The next phase will define:
- Complete application sitemap.
- Navigation hierarchy.
- Page relationships.
- Screen-level content organization.
- Global application layout.
- User interaction entry points.
- Search and filtering structure.
- Screen-to-API dependencies.

---

**End of document.**
