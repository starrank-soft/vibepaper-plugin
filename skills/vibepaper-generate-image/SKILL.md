---
name: vibepaper-generate-image
description: >-
  Generate AI images with VibePaper: text to image and image to image with
  GPT-Image-2.5, GPT-Image-2, Banana 2, Banana 2 Lite, Banana Pro, Seedream
  5.0 Pro, Wan 2.7 Image Pro, Z-Image Turbo or Midjourney V8.2. Use when the
  user asks for a picture, poster, cover, thumbnail, product shot, wallpaper,
  concept art or any still image.
---
# Generate an image

Read the `vibepaper-guide` skill first if you have not this session.

1. Clarify only what changes the result: subject, style, aspect ratio, and whether there is a reference image. Otherwise pick sensible defaults.
2. `list_models` with `kind: "image"`. Pick by intent:
   - text rendering, layouts, posters: a GPT-Image model;
   - fast drafts and many variations: Banana 2 Lite or Z-Image Turbo;
   - photoreal and product: Banana Pro or Seedream 5.0 Pro;
   - stylised art: Midjourney V8.2.
   Use the ids returned by `list_models`, which may differ from these names.
3. `get_model_schema` → set aspect ratio and size from the schema; `outputCount` 1–4.
4. Write the prompt as a shot: subject, setting, light, lens or framing, mood, palette (see `vibepaper-cinematic-prompting`).
5. Reference image: `import_asset_url` or the upload flow, then pass `assetIds`.
6. `estimate_generation_cost` → confirm if non-trivial → `create_generation` with `wait: true`.
7. Return each output with the model used and credits spent, and offer one concrete next step (variation, upscale, animate it with `vibepaper-generate-video`).
