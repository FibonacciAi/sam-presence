# How Sam works

Sam keeps perception local and makes every handoff small enough to inspect. The browser turns a live camera session into coarse, ephemeral observations; Jev adds typed attention signals; the voice model keeps the conversation moving.

```mermaid
flowchart LR
  A[Browser camera] --> B[MediaPipe<br/>local perception]
  B --> C[Coarse movement<br/>head · gaze · gesture]
  C --> D[Compact ephemeral<br/>observation]
  U[Human speech or text] --> D
  D --> E[Jev<br/>typed signals]
  D --> F[Realtime voice<br/>Grok open mic]
  E -. enriches next turn .-> F
  F --> G[Speech + transcript]
  G --> H[Sam colors pulse<br/>to actual audio]
```

## The boundary

Raw frames and landmarks stay in the browser. Jev receives bounded text and compact structured observations; the voice provider additionally receives microphone audio during voice sessions. A room description, when supplied, is human-provided context—not something Sam claims to sense.

The following is illustrative schema, not an API contract:

```json
{
  "utterance": "What should I look at next?",
  "target": { "label": "blue card", "dwellMs": 860 },
  "neighbors": ["red card", "notebook"],
  "observation": {
    "gaze": { "x": 0.62, "y": 0.41 },
    "head": { "yaw": -0.08, "pitch": 0.03 },
    "movement": "steady",
    "gesture": "pointing"
  }
}
```

Jev's response is likewise typed and bounded: relevance, grounding, perspective, and confidence-like signals that can shape pacing and the next voice context. It is an attention signal, not a diagnosis, permission, or command.

## Timing that stays responsive

Local perception can update several times per second and is available without a network round trip. Jev runs alongside conversation work and may finish after a voice turn has already started. In Grok open-mic mode, native voice activity detection can begin a response from the latest available context; Sam does not hold every reply waiting for Jev. A completed Jev result can enrich the next turn, while stale work is discarded when a new speech epoch begins. Hold-to-talk has a different boundary: audio is committed when the user releases, then response scheduling begins.

The Sam mark's color motion is driven by measured assistant audio playback. It does not infer a person's mood from pixels.

## Privacy in one sentence

Pixels and landmarks remain on-device; only permissioned voice and compact, ephemeral observations cross the provider boundary.

This public showcase contains the static page, demo media, and this technical walkthrough. The implementation remains private.
