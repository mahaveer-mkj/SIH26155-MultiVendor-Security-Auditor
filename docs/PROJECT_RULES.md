# SIH26155 Project Rules

## 1. Project Identity

Problem Statement:
SIH26155 — AI-Driven Multi-Vendor Network Security Compliance Auditor

Organization:
National Technical Research Organisation (NTRO)

Category:
Software

Theme:
Blockchain & Cybersecurity

## 2. Primary Objective

Build an AI-assisted, vendor-agnostic network security compliance auditing platform capable of processing heterogeneous network-device configurations and evaluating them against defined security frameworks.

## 3. Locked Architecture Principle

AI may assist with:
- interpretation
- unknown-command understanding
- mapping suggestions
- explanation
- remediation assistance
- knowledge retrieval

AI MUST NOT be the final authority for compliance PASS/FAIL decisions.

Final compliance decisions MUST be produced by deterministic, testable security rules.

## 4. Initial MVP Boundary

Initial vendors:
- Cisco
- Fortinet

Initial frameworks:
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

## 5. Development Principle

Build a working vertical slice before expanding breadth.

## 6. Security Principle

Use only:
- synthetic data
- public documentation
- team-created configurations
- authorized laboratory environments
- authorized devices or virtual labs

No unauthorized scanning or testing of third-party infrastructure.

## 7. Architecture Change Rule

Architecture is considered locked.

Any proposed structural change must include:
- reason
- current limitation
- proposed change
- impact
- migration requirement

No silent architecture changes.

## 8. Evidence Rule

Every major feature must have:
- requirement ID
- implementation reference
- test case
- demonstrable evidence

## 9. AI Development Rule

AI coding agents must read:
- PROJECT_RULES.md
- REQUIREMENTS.md
- ARCHITECTURE.md
- DATA_MODEL.md
- AI_CODING_RULES.md

before implementing project features.

## 10. Source of Truth

The GitHub repository is the engineering source of truth.

Official SIH/OUTR documents remain immutable reference material.
