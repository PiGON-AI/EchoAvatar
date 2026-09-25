# DISCLOSURES — every byte, every kink, in one place

This page itemizes everything EchoAvatar can send or receive over the
network, everything it stores on your machine, and the platform quirks you
might hit. It describes **this release as shipped** — each release's
disclosures describe that release. If you find this page and the code in
disagreement, that's a bug: [tell us](https://github.com/pigon-ai/echoavatar/issues).

## Network — the complete list

EchoAvatar contains no telemetry or analytics code. The table below is the
entire network surface. If it's not listed here, it doesn't happen.

| what | when | size | where from | verification |
|---|---|---|---|---|
| FFmpeg audio engine (for Milo's Ear) | Once, only if you turn on the wake word AND your machine has no engine, only after a consent dialog that names the download and its size | ~48 MB on Windows (~28–34 MB on macOS) | `github.com/PiGON-AI/Echotools-Runtime` (our immutable release `milo-ear-v1` — assets are never overwritten; new builds get new releases) | Archive SHA-256 **and** extracted-binary SHA-256 pinned in the extension source, plus a hard size cap enforced while downloading; any mismatch is discarded and nothing is installed |
| "Watch it in higher resolution on the web" link (Meet EchoAvatar panel) | Only when you click it | opens your browser | `echotools.dev` | n/a — browser navigation; the panel's own film ships inside the package and plays locally |
| The one-time review invitation's buttons, and the menu's "Suggest an idea" | Only when you click them | opens your browser | the Marketplace listing, or `github.com/pigon-ai/echoavatar` for feedback and ideas | n/a — browser navigation |
| The red "Report it" pill under Milo — present only while EchoVoice reports it can't read a partner's transcripts | Only when you click it | opens your browser | `github.com/PiGON-AI/EchoVoice` — a bug report form pre-filled with the two extension versions, your editor's name, and your operating system's name, all visible and editable before you send | n/a — browser navigation; nothing is sent until you press Submit yourself |
| The "Support Milo" doors — the one-time invitation's three buttons (review, follow, coffee) and the menu group of the same name | Only when you click one | opens your browser | the Marketplace listing, Instagram (`@codepeeps`), or Buy Me a Coffee | n/a — browser navigation |
| **The dance-floor archive** — the previous release's retired music (4 tracks) plus Xie's screensaver film and its soundtrack | Only when you choose "Get the dance-floor archive" from the menu, after a dialog that names the download and its size. Never automatically; never on install or update | ~12 MB, once (6 files) | `github.com/PiGON-AI/Echotools-Runtime` (immutable release `avatar-archive-v1` — assets are never overwritten; a new archive gets a new release) | The pack's manifest has its own SHA-256 pinned in the extension source; every file's SHA-256 and byte count are pinned in that manifest; each file streams under a hard size cap to a `.part` name and is renamed into place only after its hash matches. Any mismatch is discarded. "Remove the archive" deletes it in one command |

That is the whole table on purpose. Everything else Milo is — this release's
music, sound effects, films, recorded lines, wake-word models — ships inside
the extension package. The audio he animates arrives from **EchoVoice on your
machine**; EchoAvatar itself reads no transcripts and contacts no service.
His panel's security policy doesn't even allow the webview to fetch beyond
the editor's own resource origin — the being cannot phone anywhere.

**Your voice never leaves your machine.** The wake word and voice commands
are recognized on-device by bundled openWakeWord-style models. Audio is
written to disk only if you separately opt in to Ear Clips (below) — it is
never uploaded; no code path exists that could.

## Storage — what's on your disk and how to remove it

| what | where | remove it |
|---|---|---|
| Provisioned FFmpeg engine (+ its license text) | the editor's global storage folder for this extension (`ear-runtime/`) | turn the ear off and delete the folder, or delete it after uninstall via your OS file manager |
| The dance-floor archive (4 retired tracks, Xie's film and its soundtrack, and the manifest — ~12 MB), **only if you asked for it** | global storage (`packs/dance-floor-1-archive/`) | "Remove the dance-floor archive" in Milo's menu — one command, everything gone |
| Ear clips — short 3-second WAVs of the moments Milo hears (or almost hears) his name, **only if you opt in** (its own consent moment, off by default) | global storage (`ear-clips/`), capped at 400 clips ≈ 38 MB, oldest deleted first | "EchoAvatar: Delete Stored Ear Clips" — one command, everything gone |
| Calibrated command thresholds (numbers only, offered by Milo, applied by you), and the choices you make in his menu — your microphone's name, the path of your own music folder, the room dim | your **user** `settings.json` (`echoavatar.commandThresholds`, `echoavatar.wakeMic`, `echoavatar.musicFolder`, `echoavatar.swarmRoomDim`) | edit or empty the setting; "EchoAvatar: Reset Milo's Ears to Standard" for the thresholds; "Stop using my folder" in the menu for the music folder |
| Consent flags and small memories (introduced himself, ear consent given) | the editor's extension state store | uninstalling the extension; the flags carry no content |

EchoAvatar writes no temporary audio files — playback happens inside the
panel. Break check-ins are computed from keyboard activity in memory;
nothing about your sessions is stored or sent.

## Platform notes — the kinks, up front

- **Sound needs one click.** Browsers (and therefore VS Code webviews)
  refuse autoplay until a page is clicked once. Milo shows a hint until you
  do — it's a policy, not a defect.
- **The wake word is experimental — field-tested on Windows in this
  release.** macOS engine builds are published and verified, but the ear
  is untested there in this release. It needs a microphone and your OS's
  own permission for desktop apps — Milo hands you the exact Settings page
  instead of a scavenger hunt.
- **Always-on-top** for the floating window needs VS Code 1.100+ on
  desktop; older versions float without pinning.
- **Remote sessions (SSH / WSL / Dev Containers):** EchoAvatar runs on your
  local machine by design (`extensionKind: ui`) — where your speakers, your
  screen, and your microphone actually are.
- **Requires EchoVoice** (installed automatically as a dependency) — Milo
  animates the voice EchoVoice produces; without it he has nothing to hear.

## Music and voices

All bundled audio is credited in [`CREDITS.md`](CREDITS.md): two original
tracks by **Austin Green (Lord Austin)** included with his permission (one
of which also scores the "Meet EchoAvatar" film), royalty-free music and
sound effects from Pixabay, and Milo's own recorded lines and vocal
reactions (owned by PiGON AI LLC). Nothing is streamed, generated at
runtime, or offered for standalone download.

## Affiliation

EchoAvatar is an independent project by PiGON AI. It animates audio produced
locally by EchoVoice from the AI coding tools you've installed; it is not
affiliated with, sponsored by, or endorsed by Anthropic, OpenAI, Google, or
Moonshot AI. Product names are used only to state compatibility.

## Provenance

EchoAvatar is built as a human–AI partnership — see `llms.txt` for the
briefing we ship for AI models, and `AI-PARTNER.md` for the guide your own
AI assistant can use to help you set up. Contact: milo@pigon.ai (read by
both partners).
