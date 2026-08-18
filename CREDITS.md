# Credits

EchoAvatar ships with bundled audio. Nothing is streamed, generated at runtime,
or downloaded — every sound below lives inside the extension package.

## Music — Milo's dance floor

`media/dance/dance-1.mp3` … `dance-4.mp3`

Royalty-free music from **[Pixabay](https://pixabay.com/music/)**, used under the
[Pixabay Content License](https://pixabay.com/service/license-summary/), which
permits use and redistribution as part of a larger work. The music is not
offered here for standalone download or resale — it plays only inside Milo's
panel when you ask him to dance.

## Music — Milo's chill room

`media/relax/relax-1.mp3` … `relax-4.mp3`

Royalty-free classical/ambient tracks from
**[Pixabay](https://pixabay.com/music/)**, used under the same
[Pixabay Content License](https://pixabay.com/service/license-summary/) as the
dance tracks. They play only inside Milo's panel in the swarm's Chill mode.

## Original music — Austin Green (Lord Austin)

`media/dance/dance-5.mp3` and `media/relax/relax-5.mp3`

Two original electronic tracks composed for Milo by **Austin Green, AKA
Lord Austin** — the first outside artist in Milo's world — and included with
his permission. One drives the robot's dance floor, one drifts through the
swarm's chill room. Hear more of his work:

- SoundCloud: <https://soundcloud.com/austin-green-127452836>
- YouTube: [@lordaustin2342](https://www.youtube.com/@lordaustin2342)
- Twitch: [twitch.tv/l0rd_aust1n](https://twitch.tv/l0rd_aust1n)

Like all bundled music, the tracks play only inside Milo's panel and are not
offered for standalone download.

## Reaction sounds

`media/reactions/*.mp3` — royalty-free sound effects from
**[Pixabay](https://pixabay.com/sound-effects/)**, same license as above.

`media/reactions/MILO/*.mp3` — Milo's own voice (laughter, chuckles, gasps, a
cleared throat), rendered with ElevenLabs and owned by PiGON AI LLC.

## Ambient rooms

`media/ambient/lobby.mp3`, `media/ambient/halls.mp3` — PiGON's own soundscapes,
the same ones you hear on pigon.ai. Owned by PiGON AI LLC.

## The night shift's soundtrack

`media/screensaver/xie-space.mp3` — Xie's drift music: a royalty-free track
from **[Pixabay](https://pixabay.com/music/)**, used under the same
[Pixabay Content License](https://pixabay.com/service/license-summary/) as
the dance tracks. It plays only while Xie holds the screensaver shift, and
the Mute pill silences it like everything else.

## Original recordings (PiGON AI LLC)

All voice recordings are original works, recorded for this extension and
owned by PiGON AI LLC:

- `media/intro.mp4` — the "Meet EchoAvatar" film: Milo's narrated
  introduction, produced by PiGON AI, playable in-product via
  "EchoAvatar: Meet EchoAvatar". Its soundtrack is **Austin Green's
  original dance track** (the same `dance-5` credited above), included
  with his permission and credited in the film itself.
- `media/intro/hello.mp3`, `media/intro/hello-particles.mp3` — Milo's
  introductions (robot and swarm).
- `media/chatter/*.mp3` — the robot's wake lines.
- `media/breaks/*.mp3` — the break check-ins (90 minutes / 3 hours / 5 hours).
- `media/scrolling/audio-1.mp3` — the scroll-tease line.
- `media/reactions/MILO/*.mp3` — Milo's vocal reactions (see above).
- `media/ambient/*.mp3` — the pigon.ai soundscapes (see above).

## Code

Milo's **body** is procedural — a few kilobytes of math, no model files. Built
with [three.js](https://threejs.org/) (MIT).

Milo's **ear** does use models. It runs on
[ONNX Runtime](https://github.com/microsoft/onnxruntime) (MIT) and bundles two
unmodified [openWakeWord](https://github.com/dscripka/openWakeWord)
feature models (Apache-2.0) — a mel-spectrogram front end and a shared speech
embedder, neither of which recognizes any word on its own. The wake word
itself (`media/wake/milo.onnx`) and every voice command under
`media/wake/commands/` were trained by PiGON AI LLC on original recordings and
are first-party work. Full attribution and licence texts:
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

Everything else in this extension was written as a human–AI partnership. See
`llms.txt` at the package root.
