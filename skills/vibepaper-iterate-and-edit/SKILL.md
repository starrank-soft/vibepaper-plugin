---
name: vibepaper-iterate-and-edit
description: >-
  Iterate on an existing VibePaper result: variations, image edit and expand
  (outpaint), upscale, background cutout, trim, compose, extract a video
  frame, or animate a generated image. Use when the user says "make it…",
  "another take", "upscale", "remove the background", "extend", or refers to a
  previous VibePaper output.
---
# Iterate on a result

1. Find the source: `list_generation_jobs` / `list_edit_jobs`, then `reference_job_outputs` for the output asset ids. Or `list_assets`.
2. Pick the path:
   - **New take** with a tweak: same model, change one part of the prompt (see `vibepaper-cinematic-prompting`), and pass the previous output in `assetIds` when the model accepts references.
   - **Edit or expand an image**: `list_edit_models` → `get_edit_model_schema` → `create_edit`.
   - **Upscale, cutout, trim, compose and other operations**: `list_operations` → `create_edit` with that operation.
   - **Animate an image**: hand off to `vibepaper-generate-video` with the image asset.
   - **Continue a clip**: `extract_frame` on the last frame, then image to video from that frame.
3. Estimate with `estimate_edit_cost` or `estimate_generation_cost`, confirm if non-trivial, submit, then `wait_edit_job` / `wait_generation_job`.
4. Show before and after together, and say what changed.
