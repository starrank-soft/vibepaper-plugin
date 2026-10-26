---
name: vibepaper-guide
description: >-
  Read first before using any VibePaper tool (the VibePaper plugin or the
  vibepaper MCP at mcp.vibepaper.io). Covers sign-in, the generation flow
  (list_models, get_model_schema, estimate_generation_cost, create_generation,
  wait_generation_job), uploads, edits, credits, canvases, and what to do on
  errors. Use for any AI image, video, audio, voice, music or text generation
  through VibePaper.
---
# VibePaper guide

VibePaper (vibepaper.io) is a cinematic AI creative workspace. Its MCP server lets an agent run the same image, video, audio and text models the web app offers, charged to the user's VibePaper credits. Jobs made here also show up in the user's VibePaper History under **MCP & CLI**.

## Sign-in

The connector uses OAuth. The first call opens a VibePaper sign-in and consent page; the user approves once. There is no API key. If tools are missing or every call returns 401, ask the user to reconnect the VibePaper plugin.

## The core loop

1. `list_models` with `kind` set to `image`, `video`, `audio` or `text`. Never guess a model id; copy it from this list.
2. `get_model_schema` for the chosen model: allowed params (aspect ratio, duration, resolution, audio, seed…) and pricing.
3. `estimate_generation_cost` with the exact `model`, `prompt`, `params`, `assetIds` and `outputCount` you plan to submit.
4. Tell the user the estimate when it is more than a trivial amount, or when a batch or video is involved. Get a yes before spending.
5. `create_generation`. Pass `wait: true` for images; for video submit, then `wait_generation_job` (videos can take minutes).
6. Show the outputs as links or inline media, with the model name and the credits spent.

## Reference media

- Public https link: `import_asset_url` → `assetId`. Never pass raw URLs to `create_generation`.
- Local file in a terminal agent: `presign_asset_upload` → PUT the bytes → `complete_asset_upload`.
- Web chat clients that cannot PUT files: `upload_asset_widget`, give the user the page, then poll `get_asset`.
- Seedance 2.x with image references: call `certify_asset` first (`wait: true`).
- Reuse earlier results with `list_assets` and `reference_job_outputs`.

## Edits and operations

`list_edit_models` (image edit, expand) and `list_operations` (upscale, cutout, trim, compose, …), then `estimate_edit_cost` → `create_edit` → `wait_edit_job`. `extract_frame` turns a video frame into an image asset.

## Credits

`account_status` returns the points balance and membership tier. If the balance is below the estimate, say so and point them to https://vibepaper.io to top up instead of submitting.

## Canvas

`connect_canvas`, `canvas_read`, `canvas_query`, `canvas_edit`, `canvas_exec` and `import_to_canvas` work on a live VibePaper canvas. Use them only when the user names a canvas or asks to put results on one.

## Errors

- 401: reconnect the plugin.
- Insufficient points: report balance and estimate; do not retry.
- Validation errors: re-read `get_model_schema` and fix params; do not invent fields.
- A job that fails: report the error text, offer one sensible retry (another model or simpler params).
- `cancel_generation_job` / `cancel_edit_job` stop jobs the user no longer wants.
