---
name: vibepaper-voice-and-music
description: >-
  Generate voiceover, text to speech and music with VibePaper using ElevenLabs
  Multilingual v2, ElevenLabs Flash v2.5, MiniMax Speech 2.8, Fish Audio S2
  Pro, Doubao TTS or MiniMax Music 2.6. Use when the user wants narration, a
  voice line, a jingle, background music or a soundtrack for a video.
---
# Voice and music

1. `list_models` with `kind: "audio"`; choose a speech model for narration or MiniMax Music for songs and beds.
2. Speech: `list_voices` with the model id (filter by `search` or `languageCode`), pick a voice, and confirm it with the user when tone matters.
3. `get_model_schema` for params (voice id, speed, format, lyrics or style for music).
4. `estimate_generation_cost` → `create_generation` with `wait: true` → return the audio link with model, voice and credits.
5. For a video soundtrack, match the clip length and mood, and mention which video it is meant for.
