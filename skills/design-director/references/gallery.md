# Interactive visual selection

## Run a Visualize round

Use the `visualize` skill for collaborative design choices when it is available. Give each round one decision. A first round can choose an overall direction. In a focused round, vary only the property under discussion and keep approved choices fixed. For example, choose an accordion style first, then compare animations using that same style. Hold sample content, viewport, and initial state constant where they affect comparison.

| Decision | What to show in Visualize |
| --- | --- |
| A pattern from existing products | Show verified screenshots with source links. For a redesign, include the current screen as a baseline when it helps the comparison. See [Discovery](discovery.md#find-and-show-references). |
| A new static visual direction, or a gap in available screenshots | Use the `imagegen` skill for comparable UI concepts and label them as AI-generated. |
| Component behavior, motion, loading, or a workflow | Build interactive HTML examples with working controls and the states needed to test the difference. Honor reduced-motion preferences for animation comparisons. |

Give variants stable names and a visible choice button labeled **«Хочу этот»** for Russian, **“I want this one”** for English, or the equivalent in the user's language. Show which variant the user selected. When widget state is supported, record the round ID, variant ID, and name on explicit selection. Carousel navigation and preselected states are for browsing. Follow the [question protocol](discovery.md#ask-and-end-the-turn) and end the turn with the comparison. Apply a choice after an explicit widget submission reaches the conversation as a user answer or the user names it in chat. When the choice button only saves local state, show the selected name and invite the user to send it in chat. Accept requests to combine named parts or see new options, then record the property the user settled before moving to the next open decision.

Before sharing, verify that previews display and that the main interaction and choice button work. Keep visual comparison separate from prototype approval unless this round was explicitly presented as the approval step.

## Static gallery fallback

When Visualize is unavailable, use the [gallery template](../assets/gallery.html) for static previews or share labeled images or working HTML previews with the same option names. Ask for the selection by name in the final chat reply and end the turn. The static gallery has no package or server requirements. It can also export a decision file for the user to share.

### Prepare the gallery

1. Copy the template to a writable preview location outside the production source. Add permitted local preview images in a subfolder. For a concept, render comparable mockups first. For a reference, cite the original page and use only preview material available for display. Use the [visual reference fallback](discovery.md#find-and-show-references) when an image cannot be shown.
2. Populate the JSON in the `gallery-data` script element in the copy. Serialize the data as JSON, then replace every literal `<` in the serialized JSON with the JSON escape `\u003c` before embedding. Keep the HTML and JavaScript intact.

```json
{
  "id": "workshop-concepts-v2",
  "locale": "ru",
  "title": "Первый экран сайта мастерской",
  "prompt": "Выберите вариант и укажите, что стоит изменить.",
  "mode": "single",
  "options": [
    {
      "id": "A",
      "title": "Мастерская в деталях",
      "description": "Крупное фото показывает процесс. Запись находится рядом с расписанием.",
      "preview": "images/concept-a.png",
      "alt": "Первый экран с фотографией гончарного круга и кнопкой записи"
    },
    {
      "id": "B",
      "title": "Сначала расписание",
      "description": "Посетитель сразу видит ближайшие занятия. Фото уступает место списку.",
      "preview": "images/concept-b.png",
      "alt": "Первый экран со списком ближайших занятий"
    }
  ]
}
```

- Use a unique revision ID per round. The ID and option IDs use letters, digits, underscores or hyphens. Option IDs must be distinct. Keep the same IDs in chat and the gallery.
- Use `mode: "multiple"` when the user can combine elements from several references. Use `mode: "single"` when choosing a prototype. Use `locale: "ru"` for Russian controls or `"en"` for English. Write the title, question and descriptions in the user's language.
- `preview` is an optional relative image path within the gallery folder. Include meaningful `alt` text for each image. Add `source` as an optional HTTPS or HTTP URL to credit the original page or show more detail.
- Open the populated gallery when browser tooling is available. Check that the options are legible, previews load, and controls work at a narrow viewport. Share the local file and explain the JSON handoff. If the user cannot open the file, continue in chat with the same IDs.

### Interpret the gallery answer

The downloaded JSON contains `galleryId`, `outcome` (`choose`, `reject` or `revisit`), `selectedIds` and `comment`. Read it only when the user shares it or explicitly points to it. Check that the round ID matches the current gallery, IDs exist, and the selection count fits the mode. Resolve a stale or ambiguous answer before changing the recorded decision.

- `choose` records the selection and any specific preferences the user expressed. A reference choice informs the brief. A concept choice approves that prototype only when it was presented as the approval step.
- `reject` asks for revised options. Use the comment to identify the gap, or ask one targeted follow-up.
- `revisit` returns to a previous decision. Ask which decision if the comment does not say.

A reply such as “A for the layout, B for the photos, no animation” carries the same weight as a JSON export. Carry forward only what the reply establishes.
