---
name: vibepaper-compare-models
description: >-
  Run the same prompt through several VibePaper image or video models side by
  side (for example Seedance 2.5 vs Kling 3.0 vs Veo 3.1, or GPT-Image-2.5 vs
  Banana Pro vs Seedream 5.0 Pro) and compare quality, speed and cost. Use when
  the user asks which model is best, wants options, or is choosing a model.
---
# Compare models on one prompt

1. Agree on the prompt and 2–4 models. Default sets:
   - video: Seedance 2.5, Kling 3.0 Omni, Veo 3.1 (add Wan 3.0 for a cheaper option);
   - image: GPT-Image-2.5, Banana Pro, Seedream 5.0 Pro.
   Take ids from `list_models`.
2. `get_model_schema` for each; map shared settings (aspect ratio, duration) to each model's own param names. Note where a model cannot match.
3. `estimate_generation_cost` for each and show a total. Get one yes for the whole batch.
4. Submit all with `create_generation` (no wait), then `wait_generation_job` for each.
5. Present a compact table: model, output link, time taken, credits, and one line on what it did well or badly (prompt adherence, motion, faces, text, light).
6. Recommend one model for this kind of shot and say why. Do not claim a model is best in general.
