# Sam — intelligence, in the moment

![Sam demo](media/preview.gif)

Your main agent should get you. It should be there with you in the moment. Sam brings realtime voice, local expression, head, gaze, gesture, and Jev-powered attention into one calm, responsive experience. See it on the [public showcase page](https://fibonacciai.github.io/sam-presence/).

The demo is intentionally simple: Sam listens, notices lightly, and keeps the thread moving.

This repository is the small public window around the demo: the native landing page, a short demo film, and a technical walkthrough. The product implementation remains private; no implementation source is included here.

## What the demo shows

- Camera perception stays local in the browser. MediaPipe reduces the live view to coarse movement, head, gaze, and gesture observations.
- Those observations become compact, ephemeral context rather than raw camera data.
- Jev works alongside the voice loop, returning typed relevance, grounding, and perspective signals. In Grok open-mic mode, the voice turn does not wait for Jev; its signals enrich what comes next. Hold-to-talk naturally commits on release.
- Realtime voice uses the latest bounded context, while visual color pulses follow actual audio playback.

Read the [architecture walkthrough](ARCHITECTURE.md) for the public dataflow and timing boundary.

## Included media

- `media/preview.gif` — page preview
- `media/scene.jpg` — still image
- `demo-media/presence-study-01.mp4` — synthetic demo film

Synthetic demo media credit: created for the Sam presence study.
