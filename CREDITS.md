# Credits

EchoAvatar ships with bundled audio. Every sound below lives inside the
extension package; nothing is streamed or generated at runtime. The one thing
that can be downloaded is the **dance-floor archive** — the previous release's
retired tracks — and only when you ask for it from the menu (see
DISCLOSURES.md). Its credits are listed here too.

## Music — Milo's dance floor (this release)

`media/dance/dance-2.mp3`, `dance-summer.mp3`, `dance-halloween.mp3`

Royalty-free music from **[Pixabay](https://pixabay.com/music/)**, used under the
[Pixabay Content License](https://pixabay.com/service/license-summary/), which
permits use and redistribution as part of a larger work. The music is not
offered here for standalone download or resale — it plays only inside Milo's
panel when you ask him to dance.

## Music — Milo's chill room (this release)

`media/relax/relax-1.mp3`, `relax-2.mp3`, `relax-flow.mp3`, `relax-halloween.mp3`

Royalty-free classical/ambient tracks from
**[Pixabay](https://pixabay.com/music/)**, used under the same
[Pixabay Content License](https://pixabay.com/service/license-summary/) as the
dance tracks. They play only inside Milo's panel in the swarm's Chill mode.

## Original music — Austin Green (Lord Austin)

`media/dance/dance-5.mp3`, `media/dance/dance-austin.mp3`,
`media/relax/relax-5.mp3` and `media/relax/relax-halloween-la.mp3`

Four original electronic tracks composed for Milo by **Austin Green, AKA
Lord Austin** — the first outside artist in Milo's world — and included with
his permission. Two drive the robot's dance floor, two drift through the
swarm's chill room (one of them his Halloween track). Hear more of his work:

- SoundCloud: <https://soundcloud.com/austin-green-127452836>
- YouTube: [@lordaustin2342](https://www.youtube.com/@lordaustin2342)
- Twitch: [twitch.tv/l0rd_aust1n](https://twitch.tv/l0rd_aust1n)

Like all bundled music, the tracks play only inside Milo's panel and are not
offered for standalone download.

## Reaction sounds

`media/reactions/*.mp3` — royalty-free sound effects from
**[Pixabay](https://pixabay.com/sound-effects/)**, same license as above.

`media/reactions/MILO/*.mp3` — Milo's own voice (laughter, chuckles, gasps, a
cleared throat), rendered with ElevenLabs and owned by PiGON EVOLUTIVE AI LLC.

## Ambient rooms

`media/ambient/lobby.mp3`, `media/ambient/halls.mp3` — PiGON's own soundscapes,
the same ones you hear on pigon.ai, owned by PiGON EVOLUTIVE AI LLC.
`media/ambient/halloween.mp3` — the Halloween hum, a royalty-free track from
**[Pixabay](https://pixabay.com/music/)**, used under the Pixabay Content License.

## The night shift — PokieVault ©, Xie © and Wispie ©

`media/screensaver/pokievault.mp4` — the screensaver film that ships with Milo:
PokieVault's element wheel drifting over a galaxy, made by PiGON AI from
PokieVault's artwork, with its `PV` mark. **PokieVault ©** is a game by
PiGON EVOLUTIVE AI LLC ([@pokievaults on Instagram](https://www.instagram.com/pokievaults/)),
so the wheel, the mark and the film are © 2026 PiGON EVOLUTIVE AI LLC, all rights
reserved (see LICENSE).

`media/screensaver/pokievault.mp3` — its soundtrack, a royalty-free track from
**[Pixabay](https://pixabay.com/music/)**, used under the Pixabay Content
License. It plays only while the film holds the shift, and the Mute pill
silences it like everything else.

**Wispie ©**, the air spirit, and **Xie ©**, the galaxy chameleon, are
copyrighted characters from PokieVault, so their looks and their films are
© 2026 PiGON EVOLUTIVE AI LLC too. Their films ride in the dance-floor archive
(below); when they are here, the three take turns, one per shift.

`media/background/space.mp4`, `media/background/space-particles.mp4` — the
two rooms (the robot's and the swarm's): made by PiGON AI. Owned by
PiGON EVOLUTIVE AI LLC.

## The dance-floor archive (downloaded only if you ask)

The retired tracks — `dance-1.mp3`, `dance-3.mp3`, `relax-3.mp3`,
`relax-4.mp3`, `dance-4.mp3`, `relax-low_beats.mp3` — royalty-free music from
**[Pixabay](https://pixabay.com/music/)** under the Pixabay Content License;
Xie's night shift — `xie-space.mp4`, her film (© 2026 PiGON EVOLUTIVE AI LLC, from
PokieVault's artwork, `@pokievaults` mark), and `xie-space.mp3`, her drift
music, a royalty-free track from Pixabay that keeps the Pixabay Content
License (it is not PiGON's, unlike her film); and Wispie's night shift —
`wispie-air.mp4`, her film, and `wispie-air.mp3`, her soundtrack, both
PiGON AI's own (© 2026 PiGON EVOLUTIVE AI LLC). Published on
`github.com/PiGON-AI/Echotools-Runtime` with a manifest that carries every
file's checksum and these same credits. Fetched only from the menu's "Get the
dance-floor archive", verified before use, removable in one command.

## Original recordings (PiGON EVOLUTIVE AI LLC)

All voice recordings are original works, recorded for this extension and
owned by PiGON EVOLUTIVE AI LLC:

- `media/intro.mp4` — the "Meet EchoAvatar" film: Milo's narrated
  introduction, produced by PiGON AI, playable in-product via
  "EchoAvatar: Meet EchoAvatar". Its soundtrack is **Austin Green's
  original dance track** (the same `dance-5` credited above), included
  with his permission and credited in the film itself.
- `media/intro/hello.mp3`, `media/intro/hello-particles.mp3` — Milo's
  introductions (robot and swarm).
- `media/chatter/*.mp3` — the robot's wake lines.
- `media/milo/*.mp3` — the watchdog's spoken alerts ("I can't read … right
  now") and the all-clear, one bank per body.
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
`media/wake/commands/` were trained by PiGON EVOLUTIVE AI LLC on original recordings and
are first-party work. Full attribution and licence texts:
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

Everything else in this extension was written as a human–AI partnership. See
`llms.txt` at the package root.
