<p align="center"><img src="assets/logo.svg" width="96" alt="VibePaper"></p>

# VibePaper

**Write a shot, not a wish.** Cinematic AI video, image, audio and text generation for Cursor, Grok Bot and any MCP client, powered by [VibePaper](https://vibepaper.io).

Describe the frame, the camera move and the light. Your agent picks the model, quotes the credits, renders the result, and can place it on your VibePaper canvas.

This plugin connects your agent to VibePaper's hosted MCP server at `https://mcp.vibepaper.io/mcp`. You sign in with your VibePaper account through OAuth. There is no API key to copy. Generations are charged to your VibePaper credits and also appear in your VibePaper History under **MCP & CLI**.

## What you can do

- **Video**: text to video and image to video with Seedance 2.5, Seedance 2.0, Kling 3.0 Omni, Veo 3.1, Wan 3.0, Vidu q3 Pro, MiniMax Hailuo 2.3, PixVerse V6 and HeyGen avatar video.
- **Images**: text to image and image to image with GPT-Image-2.5, GPT-Image-2, Banana 2, Banana 2 Lite, Banana Pro, Seedream 5.0 Pro, Wan 2.7 Image Pro, Z-Image Turbo and Midjourney V8.2.
- **Edits**: image edit and expand, upscale, background cutout, trim, compose, and extracting a frame from a video.
- **Audio**: voiceover and text to speech with ElevenLabs, MiniMax Speech, Fish Audio and Doubao TTS, and music with MiniMax Music 2.6.
- **Text**: GPT, Gemini, DeepSeek and Seed text models.
- **Canvas**: read and edit a live VibePaper canvas and import results onto it.

The live model list comes from `list_models`, and it changes as VibePaper adds models.

## Install

1. Open **Cursor Settings → Plugins** (or Customize) and search for **VibePaper**.
2. Click **Install**.
3. Approve the VibePaper sign-in and consent page when it opens.

## Skills

| Skill | Use it for |
| --- | --- |
| `vibepaper-guide` | The tool flow, uploads, credits and errors. Agents read this first. |
| `vibepaper-generate-image` | Text to image and image to image |
| `vibepaper-generate-video` | Text to video and image to video |
| `vibepaper-compare-models` | The same prompt across several models, side by side |
| `vibepaper-cinematic-prompting` | Shot, camera, lens, light, grade and storyboard prompts |
| `vibepaper-credits-and-cost` | Balance, membership and cost estimates before spending |
| `vibepaper-iterate-and-edit` | Variations, edits, upscales, cutouts, extending clips |
| `vibepaper-voice-and-music` | Voiceover, TTS and music |

## MCP

```json
{
  "mcpServers": {
    "vibepaper": {
      "type": "http",
      "url": "https://mcp.vibepaper.io/mcp"
    }
  }
}
```

Authorization uses OAuth 2.1 with PKCE and dynamic client registration. The server advertises its authorization server at `/.well-known/oauth-protected-resource`.

## Example prompts

- "Make a 5-second 16:9 video of a rain-soaked neon alley at night, slow dolly forward. Use Seedance 2.5."
- "Generate a poster for a jazz night in three versions with GPT-Image-2.5 and Banana Pro, and compare them."
- "How many credits do I have? What would a 10-second Veo 3.1 clip cost?"
- "Upscale the last image and remove its background."

## License

MIT. See [LICENSE](LICENSE).

## Support

[pixelarrayai@gmail.com](mailto:pixelarrayai@gmail.com) · [vibepaper.io/contact](https://vibepaper.io/contact) · [Privacy](https://vibepaper.io/privacy) · [Terms](https://vibepaper.io/terms)
