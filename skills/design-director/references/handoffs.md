# Roles and handoffs

Keep roles separate in scope and inputs. Combine nearby roles for small projects. Only the orchestrator asks the user questions and records decisions.

| Role | Input | Output |
| --- | --- | --- |
| Discovery interviewer and UX architect | Request, product context, existing flow | Brief, critical path, content priorities and material questions. |
| Reference researcher | Brief, assets and visual gaps | Source-linked references with images when available, applicable design decisions and trade-offs. |
| Art director | Brief, comparable content, reference findings and user feedback | Distinct concepts with rationale, visual evidence and trade-offs. |
| UI designer | Selected direction, key flow and existing system | Reviewable prototype, responsive rules, tokens and component states. |
| Frontend developer | Approved prototype, content, constraints and acceptance criteria | Working implementation, verification commands and any material deviation to resolve. |
| Visual reviewer | Approved brief and prototype, fresh renders, relevant routes and viewport sizes | Evidence, severity, scope and retest for each finding. |

Give delegated work an explicit goal, inputs, constraints, expected output and completion criteria. Let researchers and designers work on separate previews. Keep production edits with the implementer. Give the reviewer the reference baseline and fresh evidence without the author's self-assessment. Keep review read-only so the implementer can address findings and the orchestrator can verify them.

## Decision record

For work spanning several turns, keep a compact record in the target project's established design notes or, if none exists, in a single `design-decisions.md` in the agreed working location. Update it when a choice changes. Record only the decisions needed to reproduce the work.

| Field | Example |
| --- | --- |
| Decision and revision | First screen, prototype v2. |
| Status | Requirement, approved by user, decided under delegated authority, inferred, open, or superseded. |
| Source and rationale | User chose C for the product photography and asked to keep A's navigation. |
| Rejected or superseded alternatives | B was rejected because it hid the booking action. |
| Next check | Confirm the booking action is visible after reflow on a 390 px viewport. |

On resumption, read the record and relevant artifacts before reopening a choice. When the user changes direction, keep the last accepted revision identifiable and state which downstream work is affected.
