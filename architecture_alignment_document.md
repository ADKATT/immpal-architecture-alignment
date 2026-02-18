# Architecture Alignment Document
IMMPAL – Architecture & Alignment Audit Phase

---

## 1. Purpose

This document confirms the architectural baseline formally defined in the existing IMMPAL architecture and governance documentation.

This document does not redefine architectural principles.

Its purpose is to:

- Validate structural boundaries
- Confirm authority ownership
- Clarify enforcement expectations
- Establish the benchmark against which implementation alignment will be evaluated

All references are derived from the formally documented:
- Role Map Specification
- Governance & Architectural Compliance documentation
- Module architecture specifications

---

## 2. Architectural Baseline Confirmation

The following architectural invariants are confirmed as established and non-negotiable:

1. Library is the canonical, normalized, and versioned source of truth.
2. CaseEngine exclusively governs deterministic case lifecycle transitions.
3. Business Layer governs entitlement and activation only.
4. Core modules and Ecosystem modules remain structurally separated.
5. The system remains country-agnostic and program-agnostic.
6. Governance and change-control rules apply to all structural modifications.

These principles form the structural foundation of IMMPAL.

---

## 3. Module Responsibility Confirmation

### 3.1 Library

Confirmed Responsibilities:
- Stores normalized program definitions
- Stores eligibility logic
- Stores evidence requirements
- Defines validation criteria
- Maintains versioned rule sets

Enforcement Expectation:
- No rule logic duplication outside Library
- No country or program logic embedded in CaseEngine or UI
- All rule consumption must originate from Library

---

### 3.2 CaseEngine

Confirmed Responsibilities:
- Owns lifecycle states
- Governs deterministic state transitions
- Enforces validation checkpoints
- Maintains case exclusivity
- Prevents unauthorized state mutation

Enforcement Expectation:
- No direct state transitions outside CaseEngine
- No UI-triggered lifecycle mutation
- No entitlement-driven state override

---

### 3.3 Business Layer

Confirmed Responsibilities:
- Governs subscription access
- Controls feature activation
- Controls PRO-level permissions
- Validates ecosystem eligibility

Enforcement Expectation:
- Cannot modify case lifecycle state
- Cannot override validation outcomes
- Cannot alter Library definitions

---

### 3.4 Core vs Ecosystem Modules

Core Modules:
- Library
- CaseEngine
- Validation Layer
- Role & Access Control
- Business Layer

Ecosystem Modules:
- JobMatch
- Marketplace
- External integrations
- Add-on modules

Enforcement Expectation:
- Ecosystem modules may consume case data
- Ecosystem modules may surface recommendations
- Ecosystem modules may not mutate lifecycle state
- Activation must satisfy entitlement and prerequisite artifacts

---
## 3.5 Authority Enforcement Matrix

The following matrix confirms intended authority distribution across modules:

| Module | Can Read Case Data | Can Modify Case Data | Can Transition Lifecycle State | Can Define Rules |
|--------|-------------------|----------------------|-------------------------------|------------------|
| Library | Yes | No | No | Yes |
| CaseEngine | Yes | Yes | Yes | No |
| Business Layer | Yes | No | No | No |
| Ecosystem Modules | Scoped | No | No | No |
| UI Layer | Yes | No | No | No |

Any deviation from this authority model constitutes structural misalignment.

---
## 4. Role Separation Confirmation

Role enforcement is confirmed as follows:

Platform Administrator:
- Controls system configuration
- Cannot directly mutate case lifecycle

Firm Administrator:
- Manages firm users
- Cannot bypass lifecycle enforcement

PRO User:
- Manages assigned client cases
- Subject to lifecycle gating

DIY User:
- Manages own case
- Subject to identical lifecycle enforcement

Role elevation must not introduce lifecycle bypass capability.

---

## 5. Country-Agnostic & Program-Agnostic Enforcement

Implementation must ensure:

- No country-specific branching in CaseEngine
- No program-specific logic embedded in UI
- No rule duplication outside Library
- All rule execution references normalized metadata

Violation of abstraction introduces structural drift and must be flagged during implementation alignment assessment.

---

## 6. Alignment Benchmark

This document defines the architectural benchmark for the audit phase.

The Implementation Alignment Report will evaluate:

- Boundary enforcement integrity
- Lifecycle authority protection
- Rule-source consistency
- Entitlement separation
- Ecosystem isolation
- Case exclusivity and concurrency safety

Any deviation identified will be documented with severity and stabilization recommendation.

---

## 7. Conclusion

The architectural baseline is confirmed as defined in existing documentation.

The objective of this phase is not architectural redesign.

The objective is structural validation and controlled alignment of implementation with the established architectural principles.
