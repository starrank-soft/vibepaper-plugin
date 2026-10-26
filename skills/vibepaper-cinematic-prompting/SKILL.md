---
name: vibepaper-cinematic-prompting
description: >-
  Write cinematic prompts for AI video and image generation on VibePaper: shot
  size, camera movement, lens, lighting, color grade, pacing, sound, and
  storyboard sequences of shots. Use before any VibePaper generation when the
  prompt is vague, or when the user asks for a film look, ad, trailer, music
  video or storyboard.
---
# Cinematic prompting

Write a shot, not a wish. A good prompt answers, in this order:

1. **Shot**: size and angle (extreme wide, wide, medium, close-up, macro; low angle, overhead).
2. **Subject and action**: who, doing what, in one clear beat. One action per shot.
3. **Setting and time**: place, era, weather, time of day.
4. **Camera**: static, slow push-in, dolly, tracking, handheld, crane, orbit, whip pan. Video only: say how fast.
5. **Lens and look**: 24mm wide, 50mm natural, 85mm portrait, anamorphic flares, shallow depth of field, film grain.
6. **Light**: golden hour, neon practicals, hard rim light, overcast soft, candlelight, volumetric haze.
7. **Grade**: teal and orange, bleach bypass, muted pastel, high-contrast noir, Kodak 2383 warmth.
8. **Sound** (models with audio): ambience, foley, dialogue line in quotes, music mood.

Example:
> Wide shot, low angle. A lone figure in a long coat walks away down a rain-soaked alley at night, neon signs reflecting in puddles. Slow dolly forward following him. 35mm anamorphic, shallow depth of field, light haze. Purple and amber neon, deep shadows, fine grain. Sound: rain on metal, distant traffic.

## Rewrite loop

When a result misses, change one thing per take and say which: framing, motion, light, or subject detail. Keep the rest of the prompt fixed so the user can see what changed.

## Storyboards

For a sequence, write 3–6 numbered shots with the same character description, wardrobe and palette in each. Generate the key frame of each shot as an image first, then animate the approved frames with image to video so characters stay consistent.

## Avoid

Lists of adjectives without a camera; several actions in one 5-second shot; real people's names without consent; asking for text in video (use an image model for typography).
