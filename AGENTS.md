\# SIH26155 — Engineering Agent Rules



\## Read Before Coding



Before making changes, read:



\- docs/PROJECT\_RULES.md

\- docs/PROBLEM\_STATEMENT.md

\- docs/REQUIREMENTS.md

\- docs/ARCHITECTURE.md

\- docs/DATA\_MODEL.md

\- docs/COMPLIANCE\_MODEL.md

\- docs/AI\_SPEC.md

\- docs/SECURITY\_MODEL.md

\- docs/TEST\_PLAN.md

\- docs/TRACEABILITY\_MATRIX.md

\- docs/AI\_CODING\_RULES.md



\## Core Rules



1\. Do not invent requirements.

2\. Do not invent compliance controls, control IDs, expected values, or security claims.

3\. Do not silently change the approved architecture or data contracts.

4\. Final compliance PASS/FAIL decisions must be deterministic and testable.

5\. AI may assist with interpretation, explanation, remediation, and knowledge retrieval, but must not be the final compliance authority.

6\. Preserve raw configuration evidence.

7\. Never hard-code secrets, API keys, passwords, or credentials.

8\. Do not send configuration data to external services unless explicitly authorized.

9\. Never automatically modify or deploy device configurations.

10\. Use only synthetic, public, or explicitly authorized test data.

11\. Security-critical logic must have automated tests.

12\. Keep vendor-specific parsing separate from vendor-neutral compliance evaluation.

13\. Prefer small, modular changes.

14\. Update documentation and traceability when behavior or contracts change.



\## Git Rules



\- Work from develop.

\- Use one focused feature branch per task.

\- Do not mix unrelated features.

\- Review git diff before committing.

\- Never commit secrets.



\## Testing Rules



\- Parser changes require parser fixture tests.

\- API changes require API tests.

\- Compliance changes require deterministic compliance tests.

\- Security-sensitive changes require negative/security tests.

\- End-to-end changes require integration tests.



\## Codex Workflow



\### Pass 1 — Analyze



Do not edit files.



Report:

\- relevant requirements

\- relevant existing files

\- proposed files to change

\- implementation approach

\- risks

\- tests required

\- blockers



\### Pass 2 — Implement



After the plan is understood:

\- implement the focused change

\- run relevant tests

\- inspect git diff

\- report changed files

\- report test results

\- report remaining risks



\## Project Pipeline



Configuration Input

\-> Validation

\-> Vendor Detection

\-> Vendor Parser

\-> Normalization

\-> Deterministic Compliance Engine

\-> PASS/FAIL

\-> Severity + Evidence

\-> AI Explanation/Remediation

\-> Dashboard/Report



Do not bypass this architecture without explicit approval.



\## Important



Development-time AI tools such as Codex are separate from the product AI functionality.

