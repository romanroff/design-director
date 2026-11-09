# Discovery and visual preferences

## Start with the missing decision

Extract the known facts from the prompt, assets, repository, current UI and design system. Identify what would change the structure, the content or the direction if answered differently. For a vague new project, ask the highest-impact questions first. Typically 2–3 fit one round.

| Gap | Example question |
| --- | --- |
| Purpose | What should the site help you achieve? Get inquiries, sell, explain a service, showcase work, or support an existing workflow? |
| Audience and key action | Who arrives here, and what should they be able to do on their first visit? |
| Scope and content | Which page or flow must work first? What real copy, images, brand materials or references are available? |
| Constraints | Which current flows, integrations, brand rules, languages or deadlines affect this design? |
| Visual preference | Do you have examples, or would you like to compare a few directions first? |

## Ask and end the turn

1. Prepare only the questions needed for the next decision. Ask about the product in ordinary language. Offer “show examples”, “undecided”, or “choose for me” when helpful. Treat delegated choices as scoped to what the user delegated.
2. Use the `visualize` skill to present the question. Use a small form with labeled choices or free-text fields for brief questions, or a [Visualize round](gallery.md#run-a-visualize-round) for design choices. If Visualize is unavailable, ask directly in the final chat reply. Skip `request_user_input`, its async variant, and other structured question tools for this workflow.
3. Put the form, comparison, or chat question in the final response and end the turn. Finish any work needed to present the question beforehand. Once the question is shown, stop the design workflow until the user answers.
4. Resume in a new turn with an explicit chat reply or an explicit widget submission delivered as a user answer. Treat drafts, widget state updates, opening the preview, browsing options, defaults, and silence as pending. When the widget cannot submit an answer to the conversation, invite the user to reply in chat with their answers or the option name.

## Find and show references

1. Start with the user's examples and assets. Search for ready-made screenshots of the relevant page type, user task, and interface state. Check product documentation, public demos, and comparable products. Open each candidate and verify that the image actually shows the pattern you plan to discuss. Look for transferable patterns from adjacent domains when direct matches are scarce.
2. Show the actual images in a [Visualize round](gallery.md) when the user is choosing between references. Use the same protocol for fallbacks when Visualize is unavailable. For open exploration, aim for roughly 4–8 useful examples across a few distinct directions. For each real screenshot, link directly to the page or document section that contains it. Verify that the previews load where the user will compare them. A link or text description alone does not count as a visual example.
3. If suitable screenshots are missing, cannot be shown, or leave a direction without a useful visual, use the `imagegen` skill and its built-in tool to fill the gap with static UI mockups. Brief the generator with the same task, sample content, interface state, and viewport across comparable examples. Vary the layout, hierarchy, or density that the user needs to choose. Inspect each result for legibility and relevance, show it alongside the real screenshots, and label it as an AI-generated example. If image generation is unavailable, try a rendered original sketch when practical and label it accordingly. If no image can be shown, explain the limitation before asking the user to choose.
4. For each candidate, identify the applicable decision. Describe how layout, hierarchy, typography, imagery, density or interaction supports the relevant visitor task. Name one element worth adapting and one trade-off or mismatch. Track asset source and reuse terms before using external imagery, type, or code in production.
5. Ask which option or combination works, what specifically works and what to avoid. Accept “none”. If two options appeal for different reasons, isolate the unresolved decision with a targeted comparison, such as the same content in an editorial grid and a service-first grid.

## Capture the creative brief

Summarize the audience, primary task and action, scope, content, brand constraints, desired direction, and success criteria. For decisions about layout, typography, color, imagery, density or motion, record the source and status. Use high, medium or low confidence for inferences when confidence affects the next step. Ask about a low-confidence choice only when guessing would materially change the result.

Example entry: `Heading type — high-contrast serif — inferred, medium confidence — user liked B for its photography; type was unmentioned.` A preference for one feature of a reference leaves its other features open.
