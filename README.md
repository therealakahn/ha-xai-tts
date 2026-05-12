# ha-xai-tts

A custom Home Assistant integration that adds xAI (Grok) as a Text-to-Speech provider, using the [xAI TTS API](https://docs.x.ai/developers/model-capabilities/audio/text-to-speech).

## Features

- Five voices: **Eve** (energetic), **Ara** (warm), **Rex** (confident), **Sal** (smooth), **Leo** (authoritative)
- Expressive speech tag support — `[pause]`, `[laugh]`, `[chuckle]`, `<emphasis>`, `<slow>`, `<soft>`, `<whisper>` and more
- Full UI config flow — no YAML required
- 20 supported languages
- Compatible with Home Assistant voice pipelines and `tts.speak` service calls
- Uses HA's modern `async_stream_tts_audio` API (requires HA 2024.10+)

## Installation

1. Copy the `custom_components/xai_tts` folder into your Home Assistant `custom_components` directory
2. Restart Home Assistant
3. Go to **Settings → Devices & Services → Add Integration** and search for **xAI Text-to-Speech**
4. Enter your [xAI API key](https://console.x.ai) and choose a default voice and language

## Speech Tags

The xAI voices support expressive tags inline in your TTS text:

```
Hello! [pause] I have some news. <emphasis>This is important.</emphasis> [chuckle] Just kidding.
```

See [xAI's TTS documentation](https://docs.x.ai/developers/model-capabilities/audio/text-to-speech) for the full list of supported tags.

## Pricing

xAI TTS is billed at **$15 per million characters**. A typical smart home announcement runs a few hundred characters — roughly $0.003 per call. A long AI-generated briefing (10,000+ characters) runs about $0.15.

## Requirements

- Home Assistant 2024.10 or later
- An [xAI API account](https://console.x.ai) with credits

## Notes

- Only one instance of the integration can be configured at a time
- The `tts.xai_tts` entity ID is fixed
- Voice and language can be changed per-call via service options
