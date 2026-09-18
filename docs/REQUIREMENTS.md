# SIH26155 — Requirements

## 1. Functional Requirements

### FR-001 — Configuration Ingestion

The system shall allow users to upload network-device configuration files for analysis.

Initial MVP input shall support Cisco and Fortinet configurations.

### FR-002 — Vendor Detection

The system shall detect the vendor of an uploaded configuration.

Initial MVP vendors:

- Cisco
- Fortinet

### FR-003 — Vendor-Neutral Normalization

The system shall convert vendor-specific configuration data into a vendor-neutral normalized representation.

### FR-004 — Deterministic Compliance Evaluation

The system shall evaluate normalized configuration data against defined compliance rules using deterministic and testable logic.

AI shall not be the final authority for compliance PASS/FAIL decisions.

### FR-005 — Compliance Findings and Evidence

The system shall produce compliance findings containing:

- PASS/FAIL result
- evidence
- observed value
- expected value where applicable
- control reference

### FR-006 — Severity

The system shall assign a severity to applicable compliance findings.

### FR-007 — AI-Assisted Unknown Command Interpretation

The system shall allow AI assistance for interpreting unknown or unsupported configuration commands and suggesting possible mappings.

AI-generated interpretations shall not automatically become trusted compliance rules.

### FR-008 — Human Validation of Mappings

The system shall allow an authorized human reviewer to approve, edit, or reject AI-generated mappings.

### FR-009 — Remediation Assistance

The system shall provide AI-assisted remediation guidance for identified compliance findings.

AI remediation guidance shall not automatically modify device configurations.

### FR-010 — Reporting

The system shall provide dashboard and reporting capabilities for compliance results.

---

## 2. Non-Functional Requirements

### NFR-001 — Modularity

The system shall use a modular architecture that separates ingestion, vendor detection, parsing, normalization, compliance evaluation, AI assistance, and reporting.

### NFR-002 — Extensibility

The architecture shall support future addition of vendors, frameworks, and operating-system versions without changing the locked MVP baseline.

### NFR-003 — Reproducibility

Deterministic compliance evaluation shall produce reproducible results for the same normalized input, controls, and rule versions.

### NFR-004 — Testability

Security-critical compliance logic shall be testable using controlled test cases and ground-truth data.

### NFR-005 — AI Assistive Operation

AI functionality shall remain assistive and shall not replace deterministic compliance evaluation.

---

## 3. Security Requirements

### SEC-001 — Secret Protection

Secrets, credentials, API keys, tokens, and other sensitive authentication material shall never be committed to the repository.

### SEC-002 — Configuration Sensitivity

Uploaded network configurations shall be treated as potentially sensitive data and shall be handled according to the project's security model.

### SEC-003 — Prompt Data Minimization

AI prompts shall not expose unnecessary sensitive configuration information.

### SEC-004 — Authorized Data and Environments

Development and testing shall use only synthetic data, public documentation, team-created configurations, authorized laboratory environments, or authorized devices and virtual labs.

### SEC-005 — No Unauthorized Testing

The project shall not perform unauthorized scanning, testing, or access against third-party infrastructure.

### SEC-006 — No Arbitrary Command Execution

Uploaded configuration files shall not be treated as executable commands.

### SEC-007 — AI Output Trust Boundary

AI-generated output shall not be blindly trusted for security-critical decisions.

---

## 4. AI Requirements

### AI-001 — Unknown Command Interpretation

AI may assist in interpreting unknown or unsupported commands.

### AI-002 — Mapping Suggestions

AI may suggest mappings between configuration constructs and compliance parameters.

### AI-003 — Explanation

AI may explain compliance findings and their security significance.

### AI-004 — Remediation Assistance

AI may generate remediation explanations and guidance.

### AI-005 — Knowledge Retrieval

AI may assist with retrieval and interpretation of relevant knowledge sources.

### AI-006 — Human Review

AI-generated mapping suggestions shall require human validation where specified by the project rules.

### AI-007 — Deterministic Compliance Authority

AI shall not be the final authority for compliance PASS/FAIL decisions.

### AI-008 — No Fabricated Controls or Evidence

AI shall not invent compliance framework controls or fabricate evidence.

### AI-009 — No Autonomous Configuration Changes

AI shall not automatically modify network-device configurations.

---

## 5. Data Requirements

### DATA-001 — Normalized Data Contract

The project shall define a vendor-neutral normalized data contract for representing relevant network-device configuration information.

### DATA-002 — Ground Truth

The project shall maintain controlled ground-truth data for supported vendors and compliance evaluation.

### DATA-003 — Test Cases

The project shall maintain controlled test cases for parser, normalization, compliance, AI, and end-to-end validation.

### DATA-004 — Data Provenance

Compliance findings and mappings shall maintain sufficient source/evidence information to support review and reproducibility.

### DATA-005 — Authorized Data Only

Project datasets shall comply with the project's authorized-data security boundary.

---

## 6. Demonstration Requirements

### DEMO-001 — End-to-End Demonstration

The project shall demonstrate the core workflow from configuration ingestion through compliance evaluation and reporting.

### DEMO-002 — Multi-Vendor Demonstration

The MVP demonstration shall include supported Cisco and Fortinet configuration examples.

### DEMO-003 — Evidence Demonstration

The demonstration shall show compliance findings with evidence and severity.

### DEMO-004 — AI Assistance Demonstration

The demonstration shall show AI-assisted functionality without presenting AI as the final compliance authority.

---

## 7. Documentation Requirements

### DOC-001 — Project Rules

The repository shall contain the project rules defining the locked architecture, security boundaries, AI boundaries, and development principles.

### DOC-002 — Problem Statement

The repository shall contain the official problem statement separately from the team's interpretation.

### DOC-003 — Requirements

The repository shall maintain a traceable requirements baseline.

### DOC-004 — Architecture

The repository shall document the approved system architecture.

### DOC-005 — Data Model

The repository shall document the data contracts required by the system.

### DOC-006 — Compliance Model

The repository shall document the compliance evaluation model.

### DOC-007 — AI Specification

The repository shall document permitted and prohibited AI behavior.

### DOC-008 — Security Model

The repository shall document the project's security model and trust boundaries.

### DOC-009 — Testing and Demonstration

The repository shall document the test and demonstration plans.

---

## 8. SIH-Related Requirements

### SIH-001 — Problem Statement Alignment

The implementation shall remain aligned with SIH26155 and the project's frozen MVP interpretation.

### SIH-002 — Scope Control

The project shall not expand the MVP beyond its defined initial scope without explicit review.

### SIH-003 — Source Preservation

Official SIH/OUTR source documents shall remain immutable reference material.

### SIH-004 — Evidence-Based Development

Major features shall have a requirement ID, implementation reference, test case, and demonstrable evidence.

---

## 9. Initial MVP Scope

Initial vendors:

- Cisco
- Fortinet

Initial compliance frameworks:

- CIS
- NIST

Initial capabilities:

- configuration ingestion
- vendor detection
- configuration parsing
- vendor-neutral normalization
- deterministic compliance evaluation
- PASS/FAIL findings
- severity
- evidence
- AI-assisted explanation
- AI-assisted remediation
- unknown-command interpretation
- human approval/edit/rejection of mappings
- dashboard
- reporting

The initial MVP shall not automatically expand to additional vendors or compliance frameworks merely because they appear in the broader official problem statement.

---

## 10. Requirement Source and Interpretation

The requirements in this document are derived from the frozen Member 1 execution package and the official SIH26155 problem statement where applicable.

Official SIH/OUTR requirements shall not be claimed unless supported by the official source material.

Team-defined engineering requirements and MVP constraints shall remain distinguishable from official problem-statement wording.
