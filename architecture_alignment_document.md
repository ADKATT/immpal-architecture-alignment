# IMMPAL – Architecture Alignment Document  
_Audit Phase – Structural Baseline Confirmation_

---

## 1. Scope

This document does **not** redefine IMMPAL architecture.

The architectural baseline is already defined in:

- OS Role Map (Final Architecture Spec)
- Governance & Architectural Compliance Documentation
- Module-Level Master Specifications

This document:

- Confirms interpretation of the existing architectural baseline  
- Consolidates architectural invariants  
- Defines enforcement expectations  
- Establishes the validation benchmark for implementation alignment  

This file serves as the architectural reference point for the audit phase.

---

## 2. Purpose

The purpose of this document is to:

- Confirm structural boundaries  
- Confirm authority ownership  
- Confirm enforcement expectations  
- Establish the benchmark against which implementation will be evaluated  

No architectural redesign is introduced in this phase.

---

## 3. Architectural Invariants (Confirmed)

The following principles are established and non-negotiable:

1. **Library is the single canonical, normalized, and versioned source of truth.**
2. **The system is strictly country-agnostic and program-agnostic.**
3. **CaseEngine exclusively governs deterministic lifecycle transitions.**
4. **Execution is strictly case-centric and case-exclusive.**
5. **Business Layer governs entitlement and activation only.**
6. **Core modules and ecosystem modules remain structurally separated.**
7. **BrainReport is a structural milestone artifact and activation prerequisite.**
8. **Governance and change-control rules apply to structural modifications.**

These define the architectural identity of IMMPAL.

---

## 4. Module Responsibility Confirmation

### 4.1 Library (Canonical Knowledge Layer)

**Responsibilities**

- Consume external regulatory/program sources  
- Normalize eligibility logic  
- Store program definitions  
- Store evidence requirements  
- Define validation criteria  
- Maintain versioned rule sets  
- Expose structured outputs to all other modules  

**Enforcement**

- No rule duplication outside Library  
- No country-specific logic in CaseEngine  
- No program-specific branching in UI  
- No module may bypass Library normalization  
- All rule execution must originate from Library metadata  

Library remains the authoritative rule layer.

---

### 4.2 CaseEngine (Lifecycle Authority)

**Responsibilities**

- Own lifecycle states  
- Govern deterministic state transitions  
- Enforce validation checkpoints  
- Maintain case exclusivity  
- Prevent unauthorized state mutation  
- Control progression through milestones  

**Enforcement**

- No lifecycle transitions outside CaseEngine  
- No UI-triggered lifecycle mutation  
- No entitlement-based lifecycle override  
- Concurrent lifecycle mutation must be structurally prevented  

CaseEngine is the sole lifecycle authority.

---

### 4.3 Business Layer (Entitlement Governance)

**Responsibilities**

- Govern subscription access  
- Control feature activation  
- Enforce persona-based permissions (DIY Individual, DIY Enterprise, PRO)  
- Validate ecosystem eligibility  

**Enforcement**

- Cannot modify lifecycle state  
- Cannot override validation results  
- Cannot alter Library definitions  
- May validate eligibility, but defers lifecycle authority to CaseEngine  

Business Layer governs access, not execution.

---

### 4.4 Core vs Ecosystem Separation

**Core Modules**

- Library  
- CaseEngine  
- Validation Layer  
- Role & Access Control  
- Business Layer  

**Ecosystem Modules**

- Muscle (execution & assisted automation)  
- DocGen (narrative generation only)  
- JobMatch  
- Marketplace  
- External integrations  

**Ecosystem Constraints**

- Depend on valid case context  
- Depend on valid BrainReport  
- Cannot exist independently of lifecycle  
- Cannot mutate lifecycle state  
- Cannot define rules  

Structural isolation must be preserved.

---

### 4.5 Ecosystem Activation Governance

Ecosystem modules may be activated only through governed entry points:

1. Savy-driven activation when structural gaps are detected  
2. BrainReport CTAs  
3. Direct client activation (requires completed profile + valid BrainReport)

In all cases:

- Entitlement must be validated  
- Case context must be valid  
- BrainReport prerequisite must be satisfied  
- Lifecycle authority remains with CaseEngine  
- No module may bypass lifecycle enforcement  

Activation is governed, not free-form.

---

## 5. Authority Enforcement Matrix

| Module            | Read Case Data | Modify Case Data | Transition Lifecycle | Define Rules |
|-------------------|----------------|------------------|----------------------|-------------|
| Library           | Yes            | No               | No                   | Yes         |
| CaseEngine        | Yes            | Yes              | Yes                  | No          |
| Business Layer    | Yes            | No               | No                   | No          |
| Ecosystem Modules | Scoped         | No               | No                   | No          |
| UI Layer          | Yes            | No               | No                   | No          |

Any deviation from this model constitutes structural misalignment.

---

## 6. Role Separation Confirmation

### Platform Administrator
- System configuration only  
- Cannot mutate lifecycle state  

### Firm Administrator
- Manage firm users  
- Cannot bypass lifecycle enforcement  

### PRO User
- Manage assigned client cases  
- Subject to lifecycle gating  

### DIY User
- Manage own case  
- Subject to identical lifecycle enforcement  

Role elevation must never introduce lifecycle bypass capability.

---

## 7. Country-Agnostic & Program-Agnostic Enforcement

Implementation must ensure:

- No country-specific branching in CaseEngine  
- No program-specific logic embedded in UI  
- No rule duplication outside Library  
- All rule execution references normalized Library metadata  
- Adding jurisdictions must not require core engine modification  

Violation introduces structural drift.

---

## 8. Governance Revalidation Requirement

Any structural adjustment identified during audit must:

- Preserve Library authority  
- Preserve lifecycle determinism  
- Preserve case exclusivity  
- Preserve ecosystem isolation  
- Preserve abstraction boundaries  

Architectural drift must be explicitly documented before remediation.

---

## 9. Audit Benchmark

This document defines the validation baseline for:

- Boundary enforcement integrity  
- Lifecycle authority protection  
- Rule-source consistency  
- Entitlement separation  
- Ecosystem isolation  
- Activation governance compliance  
- Case exclusivity and concurrency safety  

The Implementation Alignment Report will reference this document directly.

---

## 10. Conclusion

Architecture remains defined by existing IMMPAL documentation.

This audit phase:

- Does not redesign architecture  
- Does not introduce new principles  
- Validates structural alignment of implementation  

**Objective:** controlled alignment, not reinvention.
