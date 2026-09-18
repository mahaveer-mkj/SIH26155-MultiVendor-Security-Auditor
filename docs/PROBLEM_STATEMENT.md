# SIH26155 - Problem Statement

## 1. Official Problem Statement

# SIH26155 - AI-Driven Multi-Vendor Network Security Compliance Auditor

- **PS Number:** SIH26155
- **Organization:** National Technical Research Organisation (NTRO)
- **Category:** Software
- **Theme:** Blockchain & Cybersecurity
- **Deadline:** 30 September 2026

## Description

• Background Modern enterprise networks are inherently heterogeneous, consisting of a vast array of hardware from diverse vendors. Organizations are mandated to align these devices with rigorous security frameworks, including CIS Benchmarks, NIST SP 800-53, DISA STIGs, and ISO/IEC 27001.
The network environment includes, but is not limited to:
• Firewalls & SASE: Palo Alto, Fortinet, Cisco (Firepower/Secure/Meraki), Check Point, Juniper (SRX), Sophos, SonicWall, WatchGuard, Barracuda, Zscaler, Cloud-native firewalls (AWS, Azure, GCP), Sangfor, Hillstone, A10, Forcepoint, Stormshield, Netgate (pf/TNSR), Cato Networks, and others.
• Routers & Switches: Cisco (Catalyst/Nexus), HPE Aruba, Juniper (EX/MX/PTX), Arista, Extreme, NVIDIA (Mellanox), Allied Telesis, Huawei, D-Link, MikroTik, Ubiquiti, Alcatel-Lucent, Ruijie, Adtran, and others.
• Specialized Networking: Open/Disaggregated (Dell, Nokia, 'White Box' hardware running SONiC, Cumulus), Hyperscale/AI (NVIDIA, Arista, Juniper), and Physical Infrastructure (Corning).
Note: The aforementioned list is illustrative; the application must be ideally designed to support any network device configuration, regardless of vendor or market segment.
• Description
• The Core Challenge:
In modern digital infrastructures, network devices act as the primary gatekeepers of data. However, they are also the most common point of misconfiguration, which accounts for a significant percentage of security breaches. Security frameworks like CIS, NIST, and STIGs offer specific 'hardening' protocols-such as disabling insecure protocols (Telnet/HTTP), enforcing strong cryptographic suites, configuring granular ACLs, and logging all administrative access. Currently, the industry relies on a bifurcated approach: either highly manual, checklist-based human auditing or expensive, vendor-locked enterprise management suites that lack flexibility for heterogeneous, multi-vendor environments.
• Operational Gap:
Administrators managing hybrid networks (composed of firewalls, switches, and routers from various vendors like Palo Alto, Cisco, Arista, etc.) lack a centralized 'Source of Truth' for compliance. The challenge is twofold:
1.Syntactic Diversity: Each vendor uses proprietary Command Line Interface (CLI) syntax, varied hierarchical structures, and distinct firmware/OS versioning. A 'secure password' setting in a Cisco IOS switch is syntactically distinct from the same setting in a Juniper SRX firewall.
2.Scalability & Adaptation: The network landscape is not static. As organizations adopt 'White Box' networking (SONiC), Cloud-native security groups (AWS/Azure), or specialized AI-driven infrastructure, traditional parsers fail because they cannot predict or interpret the configuration structures of newly acquired or proprietary hardware.
The requested solution is an AI-augmented, vendor-agnostic Compliance Engine. Rather than relying on a hard-coded library of commands-which becomes obsolete as vendors release firmware updates-the system will employ Ai based approaches ( for example (Pattern Recognition and Natural Language Processing (NLP)) to interpret configuration files.
When a configuration file is ingested, the AI-based engine will:
• Normalization: Extract the configuration and map it into a standardized, vendor-neutral schema (e.g., a 'Security Baseline Model').
• Deviation Analysis: Compare this normalized model against the chosen framework (e.g., checking if the parsed 'ssh_version' is '2' as required by CIS).
• Dynamic Adaptation (The 'Training' Loop): When the system encounters an unrecognized configuration structure, it will trigger an Interactive Training Interface. In this GUI, the administrator will be presented with the 'raw' unrecognized command lines. Using a user-friendly, low-code interface, the administrator will map these commands to specific security categories (e.g., 'This command sets the timeout limit'). The AI engine will then update its internal heuristics, effectively 'learning' to parse this new vendor’s logic without requiring backend code redeployment.
The proposed solution should be a user-friendly, robust software platform featuring:
1. Unified Ingestion Engine: A dashboard for uploading single or bulk configuration files from any network device.
2. AI-Powered Training Module: A dedicated, intuitive GUI where administrators can 'train' the system to parse unseen vendor formats by mapping specific command outputs to compliance parameters.
3. Multi-Framework Compliance Engine: A logic engine that evaluates configurations against user-selected benchmarks (CIS, NIST, STIGs, ISO).
4. Actionable Intelligence & PDF Reporting: A comprehensive, single PDF report for each device, covering:
o Device Identification: Including serial numbers and hardware details.
o Compliance Findings: Clear 'Pass/Fail' results with risk severity assessments.
o Remediation Paths: Device-specific, step-by-step CLI command sequences to resolve non-compliance and harden the device.
5.Vendor-Agnostic Scalability: A modular architecture designed to support new vendors, standards, and OS versions without requiring manual code modifications for every update.
• Suggested Development Workflow The development can be visualized in the following stages:
1. Normalization: Converting proprietary CLI outputs into a structured JSON/Schema model.
2. Compliance Engine: Using Python libraries (e.g., Netmiko or NAPALM) for data collection and custom logic for mapping.
3. AI/ML Integration: Using Natural Language Processing (NLP) or pattern matching to identify keywords in configurations that the system has not been pre-trained on.
4. Reporting: Generating dynamic PDFs (e.g., using ReportLab or FPDF in Python) that are customized based on the device's specific model and software version.
• Expected Solution/Deliverables for Evaluation
• Source Code Link (GitHub/Drive Link)
• Readme with Setup Instructions
• Architecture Document (Max 2 Pages)
• Demo Video (Max 2 Minutes)
• Technical Presentation (Max 5 Slides)

---
Source: https://sih.gov.in/sih2026PS · CC-BY-4.0 · 2026-09-03

## 2. Organization

National Technical Research Organisation (NTRO)

## 3. Category

Software

## 4. Theme

Blockchain & Cybersecurity

## 5. Our Interpretation

The project is a security compliance auditing platform for network device configurations. It should ingest configuration files, identify vendor-specific syntax, normalize relevant settings into a common representation, evaluate those settings against selected security frameworks, and produce evidence-backed compliance findings.

For the initial MVP, the project scope is intentionally narrower than the full official vendor/framework landscape. The frozen Member 1 package defines Cisco and Fortinet as the initial vendors, and CIS and NIST as the initial frameworks. Broader vendors and frameworks named in the official statement remain future extensibility targets, not initial implementation commitments.

AI is assistive in this project. It can help interpret unknown commands, suggest mappings, explain findings, and support remediation text, but deterministic rules must remain the final authority for compliance PASS/FAIL decisions.

## 6. Target Users

- Network administrators responsible for firewall, router, and switch configuration review.
- Security auditors who need repeatable compliance findings and evidence.
- Student developers implementing the SIH26155 MVP from a shared project baseline.
- Project reviewers evaluating whether the system addresses multi-vendor compliance auditing.

## 7. Input

- Network device configuration files.
- Initially supported MVP vendor configurations: Cisco and Fortinet.
- Human-provided mappings for unknown or unsupported configuration constructs.
- Selected compliance framework context for evaluation, initially CIS and NIST.

## 8. Expected Output

- Vendor detection result.
- Vendor-neutral normalized configuration representation.
- Deterministic PASS/FAIL compliance findings.
- Severity and evidence for findings.
- AI-assisted explanation and remediation guidance.
- Dashboard view and PDF/reporting output for review and demonstration.

## 9. Required Capabilities

- Configuration ingestion.
- Vendor detection.
- Cisco and Fortinet parsing for the MVP.
- Vendor-neutral normalization.
- Deterministic compliance evaluation.
- PASS/FAIL findings with severity and evidence.
- AI-assisted unknown-command interpretation.
- Human approval, edit, or rejection of AI-generated mappings.
- AI-assisted explanation and remediation support.
- Dashboard and reporting.

## 10. Constraints

- Do not expand the MVP beyond Cisco, Fortinet, CIS, and NIST unless explicitly approved later.
- Do not invent CIS, NIST, STIG, ISO, or other framework controls.
- Do not treat AI output as final compliance authority.
- Do not execute commands from uploaded configurations.
- Use only synthetic, public, team-created, or otherwise authorized configurations.
- Do not commit secrets, credentials, private device configurations, or sensitive real-world data.
- Preserve official SIH wording separately from team interpretation.

## 11. Important Technical Requirements

- Compliance PASS/FAIL must be deterministic, testable, and reproducible.
- The architecture must follow the frozen flow from configuration input through ingestion, detection, parsing, normalization, rule evaluation, AI explanation, remediation, dashboard, and PDF/reporting.
- Normalized data contracts must allow vendor-specific inputs to map into a shared security model.
- Unknown-command handling must include human validation before mappings are trusted.
- Reports must include clear findings, severity, evidence, and remediation context.
- The system must remain modular enough to add future vendors, frameworks, and OS versions without changing the locked MVP baseline.

## 12. Open Questions

- Which exact official CIS benchmark documents will be used for the initial MVP controls?
- Which exact NIST publication sections or control families will be mapped for the initial MVP?
- Which Cisco OS/configuration format will be used first for MVP testing?
- Which Fortinet FortiOS configuration format will be used first for MVP testing?
- What official OUTR submission instructions, presentation templates, or internal evaluation rubrics must be preserved alongside the SIH source?

## 13. Explicitly Out of Scope for MVP

- Support for all vendors listed in the official problem statement.
- Support for STIGs, ISO/IEC 27001, and other frameworks beyond the frozen initial CIS and NIST scope.
- Autonomous remediation or automatic device configuration changes.
- Production infrastructure deployment.
- Unauthorized network scanning or testing.
- AI-generated final compliance decisions.
- Fabricated compliance controls or evidence.
- Blockchain features added only because the SIH theme includes Blockchain & Cybersecurity.

## 14. Source Documents

- `SIH26155_OFFICIAL_PROBLEM_STATEMENT.md`
- `SIH26155_MEMBER_1_COMPLETE_EXECUTION_PACKAGE_FROZEN.md`
- Official source URL recorded in source file: https://sih.gov.in/sih2026PS
- License recorded in source file: CC-BY-4.0
- Source date recorded in source file: 2026-09-03
