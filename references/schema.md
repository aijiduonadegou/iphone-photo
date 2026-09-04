# Structured prompt schema

Read this file only when the user asks for JSON, prompt auditing, automation output, or a strict source test.

Return a single valid JSON object. Do not use comments, Markdown fences, trailing commas, or prose outside the object.

```json
{
  "meta_data": {
    "style": "iPhone Pro Max Photography",
    "aspect_ratio": "9:16"
  },
  "prompt_components": {
    "subject": "Detailed people, styling, pose, and relationships",
    "environment": "Background, location, and social context",
    "lighting": "Smart HDR behavior and the natural or direct-flash source",
    "camera_gear": "iPhone 16 Pro Max, Main Camera 24mm f/1.78",
    "processing": "Apple ProRAW, Deep Fusion, Shot on iPhone",
    "imperfections": "Situation-appropriate digital noise, motion blur, skin texture, exposure errors, or framing flaws"
  },
  "full_prompt_string": "One comma-separated prompt combining the fields above",
  "negative_prompt": "professional camera, DSLR, bokeh balls, anamorphic, cinema lighting, studio lighting"
}
```

## Field rules

- Keep `subject` faithful to the request and reference images. Do not silently rewrite identity, age, body type, ethnicity, or relationship.
- Use `environment` to complete vague locations without inventing a new story.
- Use one camera lens in `camera_gear`; do not list alternatives.
- Keep `processing` as an aesthetic target. Do not claim the generated file is genuine Apple ProRAW or a real camera capture.
- Choose only relevant imperfections. For people, prefer pores, peach fuzz, mild tonal variation, and localized highlights over uniform gloss.
- Make `full_prompt_string` self-contained. A downstream image model should not need to read the component fields.
- Add user-requested exclusions to `negative_prompt`; in strict source-test mode, keep only the six default exclusions shown above.

## Reference-image notation

When JSON must describe references, identify their roles inside the existing fields rather than changing the schema. Example: `"subject": "Match Image 1 for identity and Image 2 for pose..."`.
