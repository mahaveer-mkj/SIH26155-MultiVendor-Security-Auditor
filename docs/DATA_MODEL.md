# SIH26155 — Data Model

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
