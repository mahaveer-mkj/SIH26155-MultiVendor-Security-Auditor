# 12. PART 9 — DATA MODEL

Member 1 defines the **contract**, not the implementation.

## 12.1 Normalized Representation

Example:

```json
{
  "device": {
    "vendor": "cisco",
    "model": "unknown",
    "hostname": "router-01"
  },
  "controls": {
    "ssh_version": 2,
    "telnet_enabled": false,
    "password_min_length": 12,
    "logging_enabled": true
  }
}
```

## 12.2 Security Control

Example:

```json
{
  "control_id": "CTRL-SSH-001",
  "framework": "CIS",
  "title": "Use SSH version 2",
  "category": "secure_management",
  "severity": "HIGH"
}
```

## 12.3 Finding

Example:

```json
{
  "finding_id": "FND-0001",
  "device_id": "DEV-0001",
  "control_id": "CTRL-SSH-001",
  "status": "FAIL",
  "severity": "HIGH",
  "observed_value": 1,
  "expected_value": 2,
  "evidence": "...",
  "remediation": "..."
}
```

### Data Contract Rule

Member 2 and Member 3 must implement against these contracts.

---
