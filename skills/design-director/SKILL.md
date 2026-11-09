---
name: design-director
description: Design, prototype, build, redesign, or visually audit websites and web UI. Use for landing pages, product flows, dashboards, and substantial components when the task calls for a design brief, visual references, alternative concepts, an approved mockup, or screenshot-based review. Use to compare and choose visual directions, component styles, interactions, or motion variants. Also matches дизайн сайта, макет, редизайн and визуальный аудит. Routine code fixes and pixel-level adjustments belong to the existing project workflow.
---

# Design Director

Turn an open-ended design request into a brief, a visual direction, a reviewable prototype, and, if requested, an implemented and verified website. Communicate in the user's language. Inspect the user's brief, references, assets, and current project before choosing a route.

## Choose a route

| Request | Start here | Finish at |
| --- | --- | --- |
| New site or substantial redesign | Read [Discovery](references/discovery.md). For redesigns, inspect the current flow, content, brand, and design system first. | The requested deliverable. For a build, continue through prototype approval, implementation, and visual QA. |
| Component or focused redesign | Identify the affected flow, existing patterns and states. Read [Design](references/design.md). Use alternatives when a design decision is open. | The requested component mockup or implementation and scoped QA. |
| Supplied design or approved direction | Extract constraints from the source and resolve material gaps. Read [Design](references/design.md). Reuse decisions the user already made. | The requested prototype or implementation and scoped QA. |
| Visual audit or comparison | Read [Visual review](references/visual-review.md). Gather current renders and any approved baseline. | Evidence and prioritized findings. Apply fixes when requested. |

## Run the design stages

1. **Discover.** Run a short adaptive interview when the brief has material gaps. With an underspecified request such as “I want a website”, establish the purpose, audience, and primary visitor action before making design choices. Read [Discovery](references/discovery.md) for Visualize questions, chat fallback, preference tracking, and reference research.
2. **Show references.** When visual direction is open, show a small, labeled set of actual interface screenshots or clearly labeled generated examples. Follow [Discovery](references/discovery.md) to find, verify, and display the images. Use the [visual selection protocol](references/gallery.md) when the user has an open design choice. Ask what to keep, combine, or avoid, then use the user's feedback to close the creative brief before making design concepts in a collaborative run.
3. **Explore and prototype.** Read [Design](references/design.md). Compare typically 3–6 genuinely distinct directions for an open-ended new design. Keep exploration proportionate for focused work. Use the [visual selection protocol](references/gallery.md) to compare one open design property per round in Visualize. Develop the chosen direction into the smallest prototype that tests the requested experience. Use a local HTML prototype unless the user requests another medium or the project has an established one.
4. **Lock the design and implement.** For a full build in a collaborative run, present the proposed direction and a reviewable prototype for approval before production implementation. A single review can settle both if the selected option already covers the requested flow and responsive behavior. Carry the approved prototype, tokens and behavior into implementation. Surface changes that would alter an approved decision and resolve them with the user before applying them.
5. **Render, review and refine.** Read [Visual review](references/visual-review.md). Inspect actual browser renders at relevant sizes, exercise key interactions, fix in-scope defects, and repeat affected checks. Use an independent reviewer when permitted. Name unverified coverage in the handoff.

## Handle choices and handoffs

- The orchestrator owns communication and approval. Use actual subagents when the host provides them and delegation is permitted. Give each a bounded role and the minimum inputs. Keep parallel work on separate outputs. If unavailable, execute the roles sequentially and identify review as a separate self-review pass. See [Roles and handoffs](references/handoffs.md).
- Ask design questions through Visualize or, if unavailable, in chat. Follow the [question protocol](references/discovery.md#ask-and-end-the-turn) and end the turn with the question. Resume only after the user's explicit answer arrives in a new turn.
- Honor explicit instructions to proceed autonomously or skip a stage. Resolve delegated design choices with evidence and record them as agent decisions. A prior explicit choice covers the same decision on later stages.
- Preserve decision provenance. Use one project-local decision log for larger work or a concise chat handoff for small tasks. Separate requirements, approvals, delegated choices, inferences and open questions. Keep private feedback in the target workspace or chat.
- Match the user's stopping point. A brief, concept comparison, mockup, audit and working site are distinct deliverables. A build request authorizes the build within its scope. Deployment and publication follow the user's request.
