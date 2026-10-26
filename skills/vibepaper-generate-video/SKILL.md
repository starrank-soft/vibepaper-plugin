---
name: vibepaper-generate-video
description: >-
  Generate AI video with VibePaper: text to video and image to video with
  Seedance 2.5, Seedance 2.0, Kling 3.0 Omni, Veo 3.1, Wan 3.0, Vidu q3 Pro,
  MiniMax Hailuo 2.3, PixVerse V6 or HeyGen avatar video, with sound where the
  model supports it. Use when the user wants a clip, shot, ad, trailer, b-roll,
  animation, or wants to animate an image.
---
# Generate a video

Read the `vibepaper-guide` skill first if you have not this session.

1. Pin down: text-to-video or image-to-video, duration, aspect ratio (16:9, 9:16, 1:1), and whether audio is wanted.
2. `list_models` with `kind: "video"`, then `get_model_schema` for the candidate. Check which params it actually supports (duration, resolution, audio, first/last frame, references).
3. Image to video: get an `assetId` with `import_asset_url` or the upload flow. For Seedance 2.x references run `certify_asset` with `wait: true` first.
4. Write one shot, not a wish: camera move, subject action, setting, light, lens, pace. Use `vibepaper-cinematic-prompting`.
5. `estimate_generation_cost`. Video costs more than images: always state the estimate and get a yes.
6. `create_generation` (no wait), tell the user it is rendering, then `wait_generation_job`.
7. Return the clip with model, duration and credits. Offer the next step: another take, a different model (`vibepaper-compare-models`), extend from the last frame (`extract_frame` → image to video), or upscale.
