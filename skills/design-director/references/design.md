# Concept, prototype and implementation

## Concept comparison

- Map the main flow and prioritize real content. Establish the navigation, first meaningful decision, primary action and key state. Use clearly marked temporary content for unavailable material.
- Use comparable copy, scope, and viewport across concepts. Make alternatives change the visual or information hierarchy, composition, image strategy, density, or interaction model. A palette or font swap alone is a treatment variant. Give each direction a memorable label and a concrete benefit and trade-off tied to the brief.
- Start with a visual slice of the important content, such as a first screen plus the next section, or the key task and state in a product UI. Render the slices when possible. Show enough of the mobile treatment to reveal meaningful differences. For an approved design reference, extract its visual rules and identify ambiguities before coding.
- Develop the chosen concept into a prototype that covers the critical path, content hierarchy, responsive changes and the states that affect the task. For a combined reference direction, show how the parts work together in this prototype. Use a full-page or interactive mockup when the brief requires it.

## Freeze what the implementation needs

Use existing design-system tokens and components where they serve the approved direction. Record only the new or changed rules needed to make the design reproducible.

| Area | Record |
| --- | --- |
| Type and color | Semantic color roles, typefaces, scale, line heights and text hierarchy. |
| Layout | Content width, columns, spacing scale, breakpoints and how key sections reflow. |
| Components | Variants and relevant states, including keyboard focus, errors, loading, empty and disabled states. |
| Media and motion | Image sources and crops, icon treatment, motion purpose and reduced-motion behavior. |
| Exceptions | The component or screen, the reason for departure and its approval status. |

Reference the approved variant and revision in the handoff. For a larger build, keep the design system in the project's established format, such as existing CSS variables or token files. Give the implementer the chosen prototype, content, responsive rules and acceptance criteria. Use the current project stack and conventions. Implement real behaviors and verify the intended primary flow. Keep preview code and unused alternatives out of production.
