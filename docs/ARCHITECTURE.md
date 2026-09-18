# SIH26155 — Architecture

              CONFIGURATION INPUT
                      │
                      ▼
              INGESTION LAYER
                      │
                      ▼
              VENDOR DETECTION
                      │
             ┌────────┴────────┐
             ▼                 ▼
          CISCO             FORTINET
          PARSER             PARSER
             │                 │
             └────────┬────────┘
                      ▼
               NORMALIZATION
                      │
                      ▼
          VENDOR-NEUTRAL MODEL
                      │
                      ▼
        DETERMINISTIC RULE ENGINE
                      │
             ┌────────┴─────────┐
             ▼                  ▼
           PASS                FAIL
                                │
                                ▼
                         SEVERITY + EVIDENCE
                                │
                                ▼
                       AI EXPLANATION
                                │
                                ▼
                          REMEDIATION
                                │
                                ▼
                       DASHBOARD / PDF

## Major Components

1. Ingestion
2. Vendor detection
3. Vendor parsers
4. Normalization
5. Compliance engine
6. Findings
7. AI service
8. Mapping/training
9. Dashboard
10. Reporting

## Architecture Rule

Do not redesign the architecture casually.

Any proposed structural change requires a documented critical engineering reason.
