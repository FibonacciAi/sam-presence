# Sam — intelligence, in the moment

![Sam](media/scene.jpg)

Your main agent should get you. It should be there with you in the moment. Sam brings realtime voice, local expression, head, gaze, gesture, and Jev-powered attention into one calm, responsive experience. See it on the [public showcase page](https://fibonacciai.github.io/sam-presence/).

The demo is intentionally simple: Sam listens, notices lightly, and keeps the thread moving.

This repository is the small public window around the demo: the native landing page and a technical walkthrough. The product implementation remains private; no implementation source is included here.

## What the demo shows

- Camera perception stays local in the browser. MediaPipe reduces the live view to coarse movement, head, gaze, and gesture observations.
- Those observations and the human's words become compact, ephemeral context rather than raw camera data.
- Jev works alongside the voice loop, returning typed relevance, grounding, perspective, and attention signals that join the same conversation context.
- OpenAI Marin is the primary realtime voice, with Grok Carina as the automatic fallback when budget is exhausted. Sam responds with the latest available words, movement, expression, and attention context; visual color pulses follow actual audio playback.

Read the [architecture walkthrough](ARCHITECTURE.md) for the public dataflow and timing boundary.

## Included media

- `media/scene.jpg` — still image
