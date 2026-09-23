# 13. PART 10 — COMPLIANCE MODEL

Define:

```text
Framework
   ↓
Control
   ↓
Condition
   ↓
Expected Value
   ↓
Observed Value
   ↓
Evaluation
   ↓
PASS/FAIL
   ↓
Severity
   ↓
Evidence
   ↓
Remediation
```

A rule should conceptually look like:

```yaml
control_id: CTRL-SSH-001
framework: CIS
platform: network
condition:
  field: ssh_version
  operator: equals
  expected: 2
result:
  pass: true
  severity: HIGH
```

### Compliance Rule Validation

This is only a model until Member 1 validates each actual control against authoritative framework material.

Do not invent or fabricate CIS/NIST controls.

---
