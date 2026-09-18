# SIH26155 — Ideal Solution Specification

## 1. Project Identity

- **Problem ID:** SIH26155
- **Problem:** AI-Driven Multi-Vendor Network Security Compliance Auditor
- **Organization:** National Technical Research Organisation (NTRO)
- **Category:** Software
- **Theme:** Blockchain & Cybersecurity
- **Primary MVP Vendors:** Cisco, Fortinet
- **Primary MVP Frameworks:** CIS, NIST

## 2. The Core Solution

Build a **vendor-agnostic network configuration compliance platform** that converts heterogeneous device configurations into one **vendor-neutral security model**, evaluates that model using **deterministic compliance rules**, and uses AI only where interpretation, explanation, or adaptation is needed.

> **AI assists. Deterministic rules decide. Human administrators approve unknown mappings.**

This directly addresses the two central problems in SIH26155:
1. **Syntactic diversity** — the same security intent appears in different vendor syntaxes.
2. **Scalability/adaptation** — traditional parsers break when a new vendor, OS, or configuration structure appears.

## 3. Complete End-to-End Workflow

```text
Configuration File(s)
        ↓
Secure Ingestion
        ↓
Metadata + Integrity Record
        ↓
Vendor / Device Detection
        ↓
Vendor-Specific Parser
        ↓
 ┌───────────────────────────────┐
 │ Known command / structure     │──→ Parse normally
 │ Unknown command / structure   │──→ AI interpretation
 └───────────────────────────────┘
                         ↓
                Human validation
                         ↓
                  Mapping Registry
                         ↓
          Vendor-Neutral Normalization
                         ↓
             Canonical Security Model
                         ↓
      Selected Framework Control Pack
          ┌─────────┬─────────┬─────────┐
          │   CIS   │  NIST   │ Future  │
          └─────────┴─────────┴─────────┘
                         ↓
          Deterministic Rule Evaluation
                         ↓
                PASS / FAIL Findings
                         ↓
       Evidence + Severity + Control ID
                         ↓
        AI Explanation + Remediation Draft
                         ↓
              Dashboard / PDF Report
                         ↓
        Human Review / Manual Remediation
                         ↓
       Re-upload → Re-audit → Verify
```

## 4. Architecture

### Presentation Layer
- Upload / bulk upload
- Device inventory
- Audit configuration
- Framework selection
- Findings dashboard
- Unknown-command training interface
- Report viewer / export

### Application / Orchestration Layer
- Job manager
- Audit session manager
- Vendor detection service
- Parsing service
- Normalization service
- Compliance orchestration
- AI assistance service
- Reporting service

### Security Intelligence Layer
- Vendor adapters
- Parsers
- Canonical Security Schema
- Framework control packs
- Deterministic rule engine
- Evidence engine
- Severity metadata
- Mapping registry

### Persistence Layer
- Device/configuration metadata
- Normalized configuration snapshots
- Rule/control definitions
- AI mapping proposals
- Human-approved mappings
- Audit findings
- Evidence
- Report metadata
- Audit logs

## 5. Canonical Security Model

The central abstraction is a **vendor-neutral security schema**.

```text
Device
├── Identity
│   ├── Vendor
│   ├── Model
│   ├── OS / Version
│   └── Device Identifier
├── Management Access
│   ├── SSH
│   ├── HTTP/HTTPS
│   ├── Telnet
│   ├── AAA
│   └── Session / Timeout
├── Authentication & Authorization
│   ├── Local Accounts
│   ├── Privilege
│   └── Authentication Sources
├── Cryptography
│   ├── Protocol Versions
│   ├── Ciphers
│   └── Key / Certificate Settings
├── Logging & Monitoring
│   ├── Admin Logging
│   ├── Remote Logging
│   └── Time Synchronization
├── Network Controls
│   ├── ACLs / Policy
│   ├── Interfaces
│   ├── Management Plane
│   └── Segmentation-related settings
└── Other Security Controls
```

## 6. Compliance Engine

The compliance engine must be **deterministic, testable, and reproducible**.

Each control should conceptually contain:

```text
Control
├── Framework
├── Control ID
├── Requirement
├── Canonical Field(s)
├── Evaluation Logic
├── Evidence Requirement
├── Severity Metadata
└── Remediation Guidance
```

```text
Normalized Security State
        +
Selected Control
        ↓
Deterministic Evaluator
        ↓
Evidence
        ↓
PASS / FAIL
        ↓
Severity
```

No LLM should directly decide the final compliance result.

## 7. AI-Assisted Unknown Command Loop

```text
Unknown Command
      ↓
Detect as Unmapped
      ↓
Show Raw Command + Context
      ↓
AI proposes:
• semantic meaning
• canonical field
• security category
• possible control mappings
• confidence
      ↓
Administrator reviews
      ↓
┌───────────────┬───────────────┬───────────────┐
│ Accept        │ Edit          │ Reject        │
└───────┬───────┴───────┬───────┴───────────────┘
        ↓               ↓
              Approved Mapping
                     ↓
              Mapping Registry
                     ↓
             Re-run Normalization
                     ↓
              Re-run Compliance
```

The system **learns operationally through approved mappings**, without allowing uncontrolled AI output to become compliance truth.

## 8. Evidence Chain

```text
Framework Control
      ↓
Rule Evaluation
      ↓
Canonical Field
      ↓
Normalized Value
      ↓
Original Configuration Evidence
      ↓
PASS / FAIL
```

Every finding should be traceable to its source evidence.

## 9. AI Usage Boundaries

### AI may
- Interpret unknown command syntax
- Suggest vendor-to-canonical mappings
- Explain why a rule failed
- Generate human-readable remediation guidance
- Draft vendor-specific CLI remediation
- Help identify patterns in previously unseen configurations

### AI must not
- Make the final PASS/FAIL decision
- Invent compliance controls
- Invent evidence
- Execute commands on devices
- Automatically change production devices
- Bypass human approval for unknown mappings

## 10. Remediation Loop

```text
Finding
  ↓
Evidence
  ↓
AI Explanation
  ↓
Device-Specific Remediation Draft
  ↓
Administrator Reviews
  ↓
Manual / Authorized Change
  ↓
New Configuration Snapshot
  ↓
Re-audit
  ↓
Verify Finding Resolved
```

Autonomous remediation is outside the MVP.

## 11. MVP Scope

### Vendors
- Cisco
- Fortinet

### Frameworks
- CIS
- NIST

### Core MVP Capabilities
- Single and bulk configuration ingestion
- Vendor detection
- Cisco parser
- Fortinet parser
- Canonical normalization
- Deterministic compliance engine
- PASS/FAIL findings
- Severity
- Evidence
- Unknown-command AI assistance
- Human mapping approval
- AI explanation
- Remediation guidance
- Dashboard
- PDF reporting

### Rule Set
A controlled initial set of meaningful CIS/NIST rules sufficient to demonstrate the complete pipeline. Exact controls must come from the selected official framework documents and must not be fabricated.

## 12. Future Extensibility

```text
                    Compliance Auditor
                           │
        ┌──────────────────┼──────────────────┐
        ↓                  ↓                  ↓
     Vendors           Frameworks          Platforms
        │                  │                  │
 Cisco/Forti → more    CIS/NIST → STIG     Network OS
                            → ISO           Cloud controls
                                            White-box / SONiC
```

Future support is an architectural goal, not an MVP claim.

## 13. Feasibility Strategy

### Why it is feasible
- Configuration files are structured text inputs.
- Vendor parsers can be isolated behind adapters.
- Normalization separates vendor syntax from security logic.
- Compliance rules can be deterministic and independently tested.
- AI can be constrained to interpretation and explanation.
- Human approval provides a safety boundary for unseen syntax.
- PDF reporting is a standard software component.

### Main risks and mitigations

| Risk | Mitigation |
|---|---|
| Vendor syntax changes | Modular parser + mapping registry |
| Unknown commands | AI suggestion + human validation |
| Wrong AI interpretation | AI never controls final compliance |
| False compliance result | Deterministic rules + evidence |
| Framework ambiguity | Use exact official control sources |
| Sensitive configuration data | Synthetic/public/authorized data only |
| Scope explosion | Freeze MVP to Cisco/Fortinet + CIS/NIST |

## 14. Security-by-Design

```text
Uploaded Configuration
        ↓
No Command Execution
        ↓
Parse as Data
        ↓
Isolated Processing
        ↓
Evidence + Audit Trail
        ↓
Human Review
```

Development and demonstrations should use only synthetic, public, team-created, or otherwise authorized configuration data.

## 15. Key Differentiators

1. **Vendor-neutral canonical security model**
2. **AI-assisted adaptation for unknown configuration syntax**
3. **Human-in-the-loop mapping approval**
4. **Deterministic compliance authority**
5. **Evidence-linked findings**
6. **Framework abstraction**
7. **Modular vendor/framework expansion**
8. **Device-specific remediation guidance**
9. **Single auditable report per device**

The strongest differentiator is:

> **AI interpretation + human validation + deterministic compliance + vendor-neutral normalization.**

## 16. Ideal Demo Flow

### Known configurations
```text
Cisco config
   ↓
Vendor detected
   ↓
Parsed
   ↓
Normalized
   ↓
CIS/NIST evaluated
   ↓
Findings
   ↓
Evidence
   ↓
AI explanation
   ↓
Remediation
   ↓
PDF report
```

### Unknown command
```text
Unknown vendor command
   ↓
AI interpretation
   ↓
Human confirmation
   ↓
Mapping saved
   ↓
Re-run audit
   ↓
Finding generated with evidence
```

## 17. Ideal SIH Idea PPT Mapping

### Slide 1 — Title
Problem ID, title, theme, category, team.

### Slide 2 — Proposed Solution
Show:
**Problem → Core gap → Proposed platform → Key innovation**

Main visual:
`Multi-vendor configs → Unified Security Model → Compliance Truth → Actionable Report`

### Slide 3 — Technical Approach
Show the complete pipeline:

`Ingest → Detect → Parse → AI Unknown-Command Loop → Normalize → Rule Engine → Findings → AI Explain/Remediate → Dashboard/PDF`

Also show a compact layered architecture diagram.

### Slide 4 — Feasibility & Viability
Show:
- MVP scope
- Risk → mitigation matrix
- Modular expansion model
- Security guardrails

### Slide 5 — Impact & Benefits
Use a user/impact mindmap:

```text
                    Platform
                       │
      ┌────────────────┼────────────────┐
      ↓                ↓                ↓
   Security          Audit          Operations
      ↓                ↓                ↓
Better visibility  Evidence      Faster review
Repeatability      Traceability  Centralized view
Vendor neutrality  Reporting     Adaptability
```

### Slide 6 — Research & References
Use authoritative/relevant sources actually used by the project:
- Official SIH26155 problem statement
- CIS Benchmark documentation used by the project
- NIST documentation used by the project
- Relevant vendor configuration documentation
- Project architecture/research artifacts

Delete the template's instruction slide before submission.

## 18. Visual Design Rules

Preferred visual language:
- dark navy / deep blue base
- white text
- restrained cyan accents
- thin technical connectors
- clean cards
- simple line icons
- architecture blocks
- decision diamonds for evaluation
- loop arrows for adaptive learning
- tree/mindmap for scope and impact

Avoid:
- hacker stock photos
- fake product screenshots
- fake dashboards
- decorative AI robots
- excessive neon gradients
- unverified numerical claims
- crowded paragraphs

## 19. Repository Documentation

Recommended structure:

```text
docs/
├── SIH26155_OFFICIAL_PROBLEM_STATEMENT.md
├── SIH26155_IDEAL_SOLUTION_SPEC.md
├── SIH26155_ARCHITECTURE.md
├── SIH26155_MVP_SCOPE.md
├── SIH26155_COMPLIANCE_MODEL.md
├── SIH26155_AI_GUARDRAILS.md
└── SIH26155_DEMO_FLOW.md
```

Keep the official problem statement clearly separated from the team's solution specification.

## 20. Truth / Scope Rule

Never claim:
- support for every vendor in the MVP
- support for every framework in the MVP
- fully autonomous compliance
- autonomous remediation
- guaranteed compliance
- fabricated control mappings
- fabricated performance metrics
- fabricated customer or deployment results

Use:
- **Official requirement** for what SIH asks
- **MVP target** for what the team plans to build first
- **Implemented** only when the feature exists and is tested
- **Future** for extensibility beyond the frozen MVP

## 21. Final Solution Statement

> **SIH26155 is addressed through a vendor-agnostic compliance architecture that transforms heterogeneous network configurations into a common security model, evaluates them using deterministic CIS/NIST rule packs, and uses AI with human validation to interpret previously unseen configuration syntax and generate actionable explanations and remediation guidance.**
