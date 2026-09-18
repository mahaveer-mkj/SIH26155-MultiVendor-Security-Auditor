# AI Specification

Clearly separate AI from deterministic logic.

## 14.1 AI Is Allowed To

```text
Interpret unknown commands
Suggest normalized mappings
Explain findings
Generate remediation explanations
Retrieve relevant security knowledge
Assist administrator
```

## 14.2 AI Cannot

```text
Declare final compliance
Override deterministic rules
Silently modify security controls
Automatically change device configurations
Invent framework controls
Invent evidence
```

## 14.3 Structured AI Output

Example:

```json
{
  "input_command": "...",
  "suggested_category": "...",
  "suggested_value": "...",
  "confidence": 0.0,
  "reasoning_summary": "...",
  "requires_human_review": true
}
```
