# Visual review

## Gather evidence

Render the relevant routes and states with the project's browser tooling or an available browser. Wait for the intended fonts and media before comparing. Capture representative desktop, tablet and mobile widths, for example 1440, 768 and 390 CSS pixels, and any breakpoint where the design materially changes. For a component or narrow audit, use only the sizes and states that affect it. Check horizontal overflow at narrow sizes and inspect the primary flow in a realistic state.

Compare with the approved prototype and token rules. For regression checks, compare the same content, viewport and state before and after. Separately review visual quality and usability. If a browser or approved baseline is unavailable, use the strongest evidence available and distinguish source inspection from rendered review.

## Inspect the experience

- **Structure and brand.** The content hierarchy, action prominence, rhythm and media reinforce the brief. Layout, type and assets hold up across sizes and relevant states.
- **Interaction and accessibility.** Exercise key controls and links, keyboard order, visible focus, labels and semantics, contrast, reduced motion where applicable, and feedback on loading, empty and error states. Use project accessibility tooling if available and report the actual coverage.
- **Anti-slop.** Look for a generic hero with interchangeable copy, repeated card grids without a grouping purpose, several competing accents, decorative glow or animation that distracts, a weak type hierarchy, and arbitrary spacing or inconsistent radii. Evaluate the actual impact. Cards, gradients, and common fonts are valid when they serve the content or brand. Favor a specific fix over a style blacklist.

## Close findings

Write each finding with severity, route or component, viewport or state, evidence, impact, and a concrete fix or retest. Treat blockers to the primary flow, broken responsive layouts, and serious accessibility barriers as critical. Mark material deviations or comprehension issues as major. Treat isolated polish issues as minor. Compare alternatives against the same brief and criteria.

For implementation, fix in-scope critical and major findings and rerun the affected visual and functional checks. Escalate a decision when resolving it would change an approved direction. Stop when the acceptance criteria are verified or a remaining limitation is identified and reported. For audit-only work, hand off the evidence and severity without changing the site.
