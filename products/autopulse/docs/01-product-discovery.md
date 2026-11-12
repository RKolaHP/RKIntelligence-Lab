
# AutoPulse AI — Product Discovery Document

**Document ID:** AP-DISC-001  
**Version:** 1.0  
**Status:** Initial discovery baseline  
**Product:** AutoPulse AI  
**Industry:** Automotive / Fleet Operations  
**Repository:** RKIntelligence-Lab  
**Last updated:** 12 November 2026

---

## 1. Executive Summary

AutoPulse AI is a fleet intelligence and predictive maintenance platform designed to help fleet operators monitor mixed vehicle fleets, understand vehicle health, coordinate maintenance, and make better operational decisions using data and AI.

The initial product will support a mixed fleet of:

- Passenger cars
- Vans and light commercial vehicles
- Trucks and heavy commercial vehicles

The product will combine public automotive and transportation datasets with clearly labeled synthetic operational data. This approach will allow us to demonstrate realistic fleet workflows while acknowledging that public datasets do not necessarily provide every operational field required by the application.

AutoPulse AI will be developed as an independent application within RK Intelligence Lab.

### Product direction

**From vehicle data to operational intelligence.**

The platform should help fleet operators answer five questions:

1. What is happening across my fleet?
2. Which vehicles require attention?
3. Why does a vehicle appear to be at risk?
4. What maintenance action should be considered?
5. How are fleet performance and maintenance costs changing?

---

## 2. Product Vision

Build a unified automotive intelligence platform that connects fleet operations, vehicle telemetry, maintenance history, analytics, and explainable predictive insights.

The experience should make complex vehicle and fleet data understandable to operational users without requiring them to be data scientists or automotive engineers.

### Product principles

- Operational usefulness before decorative dashboards.
- Explainable insights instead of unexplained AI scores.
- Consistent fleet-wide visibility with vehicle-level detail.
- Clear distinction between observed data, derived metrics, and predictions.
- Support for different vehicle classes without assuming all vehicles have identical sensors.
- Transparent data quality and source information.
- Human review before maintenance recommendations become operational actions.

---

## 3. Target Customer and Initial Market

### Primary customer segment

Fleet operators managing multiple vehicles across logistics, delivery, transportation, and commercial operations.

### Initial vehicle scope

| Vehicle class | Examples | Initial operational focus |
|---|---|---|
| Passenger cars | Company cars, fleet cars | Usage, mileage, service history |
| Vans | Delivery and service vans | Utilization, mileage, maintenance |
| Trucks | Commercial and logistics trucks | Engine health, operating hours, maintenance |

The application must accommodate vehicle-specific data differences. A sensor available for one truck model may not exist for a passenger car.

### Initial customer profile

A small-to-medium or enterprise fleet operation that:

- Manages multiple vehicle types.
- Maintains vehicle and service records.
- Wants a consolidated view of fleet condition.
- Needs to reduce avoidable downtime.
- Uses operational data to plan maintenance and allocate assets.

This is an initial target profile, not a validated market-size or customer-demand claim.

---

## 4. User Personas

### Persona 1 — Fleet Manager

**Responsibility:** Overall fleet availability and operational performance.

**Needs:**
- Fleet inventory and status.
- Vehicles available, in service, or unavailable.
- Utilization and downtime trends.
- Critical vehicle alerts.
- Fleet-level maintenance visibility.

**Primary question:** Which vehicles need attention today?

### Persona 2 — Maintenance Manager

**Responsibility:** Maintenance planning and service coordination.

**Needs:**
- Upcoming and overdue maintenance.
- Vehicle service history.
- Diagnostic events and fault information.
- Work-order tracking.
- Maintenance costs.

**Primary question:** What needs to be serviced, and when?

### Persona 3 — Fleet Analyst

**Responsibility:** Fleet performance analysis and reporting.

**Needs:**
- Historical telemetry and utilization.
- Maintenance expenditure.
- Vehicle downtime.
- Data quality indicators.
- Downloadable operational reports.

**Primary question:** What patterns are affecting fleet performance?

### Persona 4 — Service Technician

**Responsibility:** Vehicle inspection and maintenance execution.

**Needs:**
- Vehicle profile and service history.
- Diagnostic information.
- Assigned maintenance tasks.
- Inspection and service records.
- Work-order status updates.

**Primary question:** What do I need to inspect or repair?

---

## 5. Problems to Solve

The following are product hypotheses to validate during discovery.

| Problem hypothesis | Product opportunity |
|---|---|
| Fleet information is spread across different systems and files. | Unified fleet inventory and overview |
| Maintenance teams may discover issues too late. | Alerts and maintenance planning |
| Vehicle histories are difficult to compare. | Centralized vehicle profiles |
| Operational trends are not easy to interpret. | Fleet analytics and reporting |
| Predictive results may lack useful explanations. | Explainable risk indicators |
| Data from different vehicle types is inconsistent. | Vehicle-aware data normalization |

AutoPulse should not claim to eliminate breakdowns or guarantee maintenance savings. Those outcomes require validation with real operational evidence.

---

## 6. Product Goals and Non-Goals

### Goals for the first release

1. Provide a consolidated view of a mixed vehicle fleet.
2. Support vehicle inventory and vehicle-level profiles.
3. Show vehicle health and available diagnostic information.
4. Track maintenance schedules and work orders.
5. Present historical operational and maintenance trends.
6. Demonstrate explainable anomaly and maintenance-risk indicators.
7. Integrate public datasets and synthetic operational records.
8. Provide a responsive, accessible user experience.

### Non-goals for the first release

- Direct integration with every vehicle manufacturer.
- Production-grade real-time OEM connectivity.
- Autonomous vehicle control.
- Automated repair decisions.
- Guaranteed failure prediction.
- Insurance underwriting or driver surveillance.
- Full enterprise fleet procurement and accounting.
- A mobile-native application.

These can be reconsidered after the MVP is evaluated.

---

## 7. Proposed Product Modules

### 7.1 Fleet Command Center

Purpose: Provide a fleet-wide operational overview.

Initial capabilities:
- Total registered vehicles.
- Vehicle availability and operational status.
- Health distribution.
- Critical and warning alerts.
- Upcoming maintenance.
- Fleet utilization trends.
- Maintenance cost summaries.

Primary user: Fleet Manager.

### 7.2 Vehicle Intelligence

Purpose: Provide a consolidated profile for each vehicle.

Initial capabilities:
- Vehicle identification and classification.
- Manufacturer, model, year, and fuel type.
- Current mileage and operating hours where available.
- Vehicle status.
- Available telemetry.
- Diagnostic events.
- Maintenance history.
- Health indicators.

Primary users: Fleet Manager and Maintenance Manager.

### 7.3 Telemetry Intelligence

Purpose: Explore vehicle operating data over time.

Potential data elements:
- Vehicle speed.
- Engine operating hours.
- Mileage.
- Fuel consumption.
- Engine temperature.
- Battery voltage.
- Diagnostic trouble codes.
- GPS position, where available and permitted.

Not every vehicle or dataset will contain every field. The interface must communicate unavailable or stale readings instead of inventing values.

Primary users: Fleet Analyst and Maintenance Manager.

### 7.4 Maintenance Operations

Purpose: Coordinate preventive and corrective maintenance.

Initial capabilities:
- Maintenance schedules.
- Due and overdue maintenance.
- Work-order creation.
- Work-order assignment.
- Service status.
- Maintenance history.
- Service cost tracking.

Primary users: Maintenance Manager and Service Technician.

### 7.5 Predictive Intelligence

Purpose: Help users identify patterns and investigate potential maintenance risks.

Potential capabilities:
- Anomaly detection.
- Component risk indicators.
- Maintenance priority suggestions.
- Historical trend analysis.
- Model confidence and explanation.
- Prediction history and feedback.

All predictions must be labeled as model-generated estimates. The application must show the factors contributing to a result and must not present predictions as confirmed mechanical faults.

Primary users: Maintenance Manager and Fleet Analyst.

### 7.6 Analytics and Reporting

Purpose: Support fleet-level operational analysis.

Initial reporting areas:
- Vehicle utilization.
- Fleet availability.
- Vehicle downtime.
- Maintenance expenditure.
- Service frequency.
- Vehicle performance trends.
- Alert frequency and resolution.

Primary users: Fleet Manager and Fleet Analyst.

---

## 8. Core User Journey

### Journey: Identify and investigate a vehicle maintenance issue

1. The Fleet Manager opens the Fleet Command Center.
2. The application displays fleet status and outstanding alerts.
3. The user selects a vehicle requiring attention.
4. The Vehicle Intelligence page displays vehicle details and available health information.
5. The user reviews telemetry trends and diagnostic events.
6. Predictive Intelligence displays a risk estimate, contributing factors, and data-quality context where a model is available.
7. The Maintenance Manager reviews the finding.
8. The user creates or assigns a maintenance work order.
9. The Service Technician records inspection and service results.
10. The vehicle's maintenance history and operational status are updated.

### Journey outcome

A traceable workflow from fleet-level visibility to vehicle investigation and maintenance follow-through.

---

## 9. Initial Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Users can view fleet summary information. | Must |
| FR-002 | Users can search and filter vehicles. | Must |
| FR-003 | Users can view individual vehicle profiles. | Must |
| FR-004 | Users can view available vehicle health and diagnostic information. | Must |
| FR-005 | Users can view maintenance schedules. | Must |
| FR-006 | Authorized users can create and update work orders. | Must |
| FR-007 | Users can review maintenance history. | Must |
| FR-008 | Users can view fleet utilization and maintenance analytics. | Must |
| FR-009 | Users can view alerts and their resolution status. | Must |
| FR-010 | Users can view model-generated risk indicators and explanations. | Should |
| FR-011 | Users can export selected reports. | Should |
| FR-012 | Users can configure alert preferences. | Could |
| FR-013 | Users can compare vehicle groups. | Could |

Priorities are proposed and will be reviewed before implementation.

---

## 10. Non-Functional Requirements

### Performance
- Common screens should load efficiently.
- Large tables should support pagination or virtualization.
- Charts should support practical date-range filtering.
- API responses should be monitored and optimized.

### Reliability
- Data ingestion failures should be visible.
- Invalid records should be quarantined or reported.
- Failed background jobs should be traceable.
- The interface should distinguish unavailable data from zero values.

### Security
- Authentication is required for protected application functions.
- Role-based permissions should govern access.
- Sensitive customer and vehicle information should be protected.
- API communication must use secure transport.
- Important user actions should be auditable.

### Usability and accessibility
- Responsive desktop and tablet layouts.
- Clear status labels and consistent interactions.
- Accessible color contrast.
- Keyboard-accessible controls.
- Do not communicate severity using color alone.

### Explainability
- Predictions must show their generation time and model version.
- Display the relevant input factors when available.
- Distinguish historical observations from future estimates.
- Allow users to inspect the supporting data.

---

## 11. Data Strategy

AutoPulse will use two complementary data sources.

### A. Public datasets

Purpose:
- Learn realistic data structures.
- Explore time-series and vehicle-operation data.
- Benchmark analytical and machine-learning workflows.
- Document data limitations and licensing.

Candidate sources:

| Source | Potential use | Important limitation |
|---|---|---|
| SCANIA Component X | Truck operational data and predictive maintenance research | Truck/component-specific; not a universal mixed-fleet schema |
| U.S. DOT ITS DataHub | Connected-vehicle and transportation research data | Dataset schemas and coverage vary |
| NLR Fleet Data Logging / FleetREDI information | Fleet-operation and telematics research | Access and reuse conditions must be checked for each dataset |

Candidate references:
- SCANIA Component X: https://doi.org/10.5878/jvb5-d390
- U.S. DOT ITS DataHub: https://www.its.dot.gov/data/
- NLR Fleet Data Logging: https://www.nlr.gov/transportation/fleet-data-logging

Before importing any dataset:
1. Read its documentation.
2. Verify its license and permitted use.
3. Record its source and version.
4. Inspect its schema and data quality.
5. Map only compatible fields.
6. Preserve source-specific fields where necessary.

Do not assume a truck dataset can directly train a reliable passenger-car maintenance model.

### B. Synthetic operational data

Purpose:
- Fill gaps in public datasets.
- Demonstrate complete fleet workflows.
- Provide consistent mixed-vehicle examples.
- Test dashboards, alerts, work orders, and reporting.

Synthetic records may include:
- Fleet and vehicle master data.
- Vehicle status.
- Mileage and operating hours.
- Simulated telemetry.
- Diagnostic events.
- Maintenance schedules.
- Work orders.
- Maintenance costs.
- Simulated anomaly events.

Synthetic data must be visibly identified in the application and in documentation.

### Data provenance

Every imported or generated dataset should carry:
- Source name.
- Source reference.
- Dataset version.
- Import or generation date.
- Vehicle class.
- Data quality status.
- Synthetic/public classification.

### Data quality rules

- Vehicle identifiers must be consistent.
- Timestamps must use a documented timezone convention.
- Units must be explicit.
- Invalid sensor readings must be flagged.
- Missing values must not silently become zero.
- Duplicate records must be identified.
- Data freshness must be visible where relevant.

---

## 12. Proposed Data Domains

These are conceptual domains, not a finalized database schema.

| Domain | Example information |
|---|---|
| Fleet | Fleet identity and configuration |
| Vehicle | Vehicle identity and specifications |
| Telemetry | Timestamped operating readings |
| Diagnostic Event | Fault codes and event details |
| Maintenance | Maintenance plans and service history |
| Work Order | Assigned tasks and execution status |
| Alert | Severity, source, and resolution |
| Prediction | Model output, risk, and explanation |
| Data Source | Provenance and ingestion metadata |

A normalized database design and detailed entity relationships will be produced in a separate architecture phase.

---

## 13. AI and Analytics Strategy

AI should be introduced progressively.

### Stage 1 — Descriptive analytics
- Fleet utilization.
- Vehicle availability.
- Maintenance expenditure.
- Service trends.
- Alert frequency.

### Stage 2 — Data quality and anomaly detection
- Sensor outlier detection.
- Unusual operating patterns.
- Missing or delayed telemetry.
- Diagnostic-event frequency analysis.

### Stage 3 — Predictive maintenance exploration
- Component-risk estimation.
- Maintenance forecasting.
- Remaining-useful-life experimentation where suitable data exists.

### Model governance requirements
- Establish a baseline before advanced modeling.
- Avoid data leakage.
- Use time-aware train/test splits for temporal data.
- Evaluate class imbalance.
- Report precision, recall, F1, and appropriate calibration metrics.
- Record model versions and training-data lineage.
- Explain model limitations.
- Keep maintenance decisions under human review.

No predictive accuracy target is finalized at this discovery stage.

---

## 14. Success Metrics

Initial product and engineering measures:

### Product usability
- Users can find a vehicle and inspect its profile.
- Users can identify outstanding maintenance tasks.
- Users can trace an alert to its supporting information.
- Users can complete the work-order workflow.

### Data engineering
- Ingestion success rate.
- Data validation pass rate.
- Duplicate-record rate.
- Missing-data rate.
- Pipeline execution duration.
- Data freshness.

### Operational analytics
- Fleet availability.
- Vehicle utilization.
- Maintenance cost per vehicle.
- Downtime duration.
- Preventive versus corrective maintenance distribution.

### Predictive intelligence
- Precision and recall for supported failure labels.
- False-alert rate.
- Lead time where valid event timestamps exist.
- Model calibration and performance by vehicle class.

Targets will be defined after baseline data and test scenarios are established.

---

## 15. Risks and Mitigations

| Risk | Mitigation |
|---|---|
| Public datasets do not cover all vehicle classes | Combine suitable sources with labeled synthetic records |
| Different vehicles expose different telemetry | Use a common core schema with optional, source-specific attributes |
| Synthetic data looks like real telemetry | Display source and synthetic-data indicators throughout the UI |
| Model predictions are unreliable | Establish baselines, validate by vehicle class, and show limitations |
| False alerts create unnecessary work | Provide severity rules, evidence, and human review |
| Sensitive location or vehicle data is exposed | Apply access controls, minimization, and audit logging |
| Dashboard becomes overloaded | Prioritize workflows and progressive disclosure |

---

## 16. MVP Acceptance Criteria

The initial MVP will be considered functionally demonstrable when:

- A user can access the fleet overview.
- A mixed fleet of cars, vans, and trucks can be represented.
- Users can search and filter the vehicle inventory.
- Each vehicle has a detail page.
- Available telemetry and diagnostic information can be inspected.
- Maintenance schedules and work orders can be viewed and updated.
- Alerts can be reviewed and resolved.
- Fleet-level operational analytics are available.
- Public and synthetic data are distinguishable.
- Data quality issues are visible.
- Predictive outputs, if included, are labeled and explained.
- The main workflows function on desktop and tablet layouts.

These criteria define a demonstration-ready MVP, not production certification.

---

## 17. Proposed Design Direction

**Experience concept:** Automotive Operations Cockpit.

### Visual language
- Deep graphite and navy surfaces.
- Electric cyan as the primary accent.
- Amber for warnings.
- Red for critical states.
- Neutral tones for ordinary information.
- Clear typography and compact data layouts.

### Navigation
1. Overview
2. Vehicles
3. Live Telemetry
4. Maintenance
5. Predictive AI
6. Analytics
7. Alerts
8. Settings

### Core screen priority
1. Fleet Command Center.
2. Vehicle Inventory.
3. Vehicle Detail.
4. Maintenance Operations.
5. Alerts and Investigation.
6. Predictive Intelligence.
7. Analytics and Reporting.

The final design system and screen specifications will be documented separately.

---

## 18. Proposed Technology Direction

The technology choices are provisional until architecture and deployment requirements are reviewed.

| Layer | Proposed technology |
|---|---|
| Frontend | React / Next.js, TypeScript |
| Styling | Tailwind CSS |
| Charts | Recharts |
| Backend | Python, FastAPI |
| Operational database | PostgreSQL |
| Data processing | Python, SQL, PySpark |
| Analytics | SQL and Python |
| ML experimentation | Scikit-learn, XGBoost |
| Model experimentation at scale | PyTorch where justified |
| Testing | Pytest, frontend component and browser tests |
| Deployment | To be decided after architecture review |

The MVP should avoid introducing unnecessary infrastructure before the product workflows and data requirements are known.

---

## 19. Delivery Phases

| Phase | Deliverable | Status |
|---|---|---|
| 01 | Product discovery | Initial baseline |
| 02 | Personas and user journeys | Next |
| 03 | Functional requirements and acceptance criteria | Pending refinement |
| 04 | Information architecture and screen flows | Pending |
| 05 | Wireframes and UI specifications | Pending |
| 06 | Design system | Pending |
| 07 | Architecture and database design | Pending |
| 08 | API contracts and data pipelines | Pending |
| 09 | MVP implementation | Pending |
| 10 | Testing and deployment | Pending |

---

## 20. Open Questions for Future Discovery

These decisions are intentionally unresolved:

- Which fleet size should the demo represent?
- Should the initial experience prioritize logistics and delivery operations?
- Which vehicle fields are mandatory across all vehicle classes?
- Which diagnostic codes and sensor signals will be supported?
- Will GPS and route visualization be part of the first release?
- What maintenance scheduling rules should be supported?
- Which public dataset will be used for each analytical experiment?
- What should count as a critical alert?
- Which user roles can create, assign, and close work orders?
- Which predictive maintenance use case has sufficient data for validation?

These questions will be resolved progressively rather than guessed.

---

## 21. Discovery Decisions

### Confirmed

- Product name: AutoPulse AI.
- Primary customer: Fleet operators.
- Vehicle scope: Mixed fleet.
- Initial vehicle classes: Cars, vans, and trucks.
- Data strategy: Public datasets plus synthetic operational data.
- Development order: First product in RK Intelligence Lab.

### Proposed, pending validation

- Fleet operations as the central workflow.
- Maintenance operations as the main action workflow.
- Explainable predictive maintenance as a differentiating capability.
- Automotive Operations Cockpit visual direction.
- React/TypeScript and Python/FastAPI as the likely application stack.

### Decision principle

Any major change to customer scope, product workflow, data assumptions, or architecture should be recorded in the product decision log.

---

**End of document.**
