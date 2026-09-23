# AI CODING RULES — SIH26155

You are assisting development of SIH26155.

Before modifying the repository, read:

1. PROJECT_RULES.md
2. PROBLEM_STATEMENT.md
3. REQUIREMENTS.md
4. TRACEABILITY_MATRIX.md
5. ARCHITECTURE.md
6. DATA_MODEL.md
7. COMPLIANCE_MODEL.md
8. AI_SPEC.md
9. SECURITY_MODEL.md

## Mandatory Rules

1. Do not invent requirements.
2. Do not silently redesign architecture.
3. Do not change normalized schemas without documenting the change.
4. Do not make an LLM the final compliance decision-maker.
5. Compliance PASS/FAIL must remain deterministic.
6. Do not hard-code secrets.
7. Do not commit credentials.
8. Do not use unauthorized network targets.
9. Treat uploaded network configurations as sensitive.
10. Add tests for security-critical logic.
11. Preserve backwards compatibility where practical.
12. Prefer small, modular changes.
13. Do not add unnecessary dependencies.
14. Do not add functionality outside the current milestone without explicit approval.
15. Update documentation when architecture or behavior changes.
16. Never fabricate security evidence.
17. Never fabricate compliance controls.
18. Cite authoritative sources when implementing compliance requirements.
19. AI-generated mappings require human validation where specified.
20. Every completed requirement must have testable evidence.

## Development Process

Understand → Plan → Implement → Test → Review → Document

Never skip testing for compliance logic.
