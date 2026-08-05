# Third-Party Notices

EchoAvatar bundles the following third-party software and media. Full license
texts are reproduced or linked below as their licenses require.

## three.js

The webview renderer bundles [three.js](https://threejs.org/)
(npm package `three`), used under the MIT License:

```
The MIT License

Copyright © 2010-2024 three.js authors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

## ONNX Runtime (Milo's Ear)

The wake-word listener runs its models on
[ONNX Runtime](https://github.com/microsoft/onnxruntime) (© Microsoft
Corporation), used under the **MIT License**. It ships as `media/ear/ort/`
(`ort.node.min.js`, `ort-wasm-simd-threaded.mjs`,
`ort-wasm-simd-threaded.wasm`).

Licence text: `media/ear/ort/LICENSE-onnxruntime.txt`. Upstream's own
third-party notices (protobuf, zlib, ONNX, Eigen and others) are reproduced
verbatim in `media/ear/ort/LICENSE-onnxruntime-thirdparty.txt`.

## openWakeWord feature models (Milo's Ear)

Milo's Ear is built on the [openWakeWord](https://github.com/dscripka/openWakeWord)
architecture (© David Scripka), and **bundles two of its shared feature
models unmodified**, under the **Apache License 2.0**:

- `media/wake/melspectrogram.onnx` — the audio front end
- `media/wake/embedding_model.onnx` — the shared speech-embedding model

Licence text: `media/wake/LICENSE-openwakeword-apache-2.0.txt`.

These two files are general-purpose feature extractors and contain no
wake-word of their own. Everything they feed is first-party: `media/wake/milo.onnx`
(the "Milo" wake word) and every model under `media/wake/commands/` were
trained by PiGON AI LLC on original recordings, are © PiGON AI LLC, and are
not derived from openWakeWord's pre-trained models.

## Downloaded at runtime, only if you turn on Milo's Ear

- **FFmpeg** — [ffmpeg.org](https://ffmpeg.org/). Milo's Ear needs FFmpeg to
  read the microphone. If the machine doesn't already have one on PATH,
  EchoAvatar offers to fetch a pinned build; the archive and the extracted
  binary are both SHA-256-verified against hard-coded digests before use, and
  declining leaves the ear off.

  FFmpeg is **executed as a separate downloaded program**, not linked into or
  shipped with this extension — so its licence never reaches this package. A
  copy of the licence text for the exact build in use is written beside the
  binary as `FFMPEG-LICENSE.txt` at install time, and that file is the
  authority on its terms.

## Bundled music and audio

Third-party audio, all used and redistributed under the
[Pixabay Content License](https://pixabay.com/service/license-summary/):

- Music under `media/dance/` and `media/relax/` — royalty-free tracks from
  [Pixabay Music](https://pixabay.com/music/), except `dance-5.mp3` and
  `relax-5.mp3`, which are original works by Austin Green (Lord Austin),
  included with the artist's permission — see
  [CREDITS.md](CREDITS.md) for attribution and links.
- Reaction sound effects under `media/reactions/` (excluding
  `media/reactions/MILO/`) — royalty-free effects from
  [Pixabay Sound Effects](https://pixabay.com/sound-effects/).

The full audio inventory, including which assets are original PiGON AI LLC
works (voice recordings under `media/chatter/`, `media/breaks/`,
`media/intro/`, `media/scrolling/`, `media/reactions/MILO/`, and the ambient
soundscapes), is listed in [CREDITS.md](CREDITS.md).
