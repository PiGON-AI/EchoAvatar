# DISCLOSURES — every byte, every kink, in one place

This page itemizes everything EchoAvatar can send or receive over the
network, everything it stores on your machine, and the platform quirks you
might hit. It describes **this release as shipped** — each release's
disclosures describe that release. If you find this page and the code in
disagreement, that's a bug: [tell us](https://github.com/PiGON-AI/echotools/issues/new?template=bug.yml&product=EchoAvatar).

## Network — the complete list

EchoAvatar contains no telemetry or analytics code. The table below is the
entire network surface. If it's not listed here, it doesn't happen.

| what | when | size | where from | verification |
|---|---|---|---|---|
| FFmpeg audio engine (for Milo's Ear) | Once, only if you turn on Milo's ear (push to talk or the wake word) AND your machine has no engine, only after a consent dialog that names the download and its size | ~48 MB on Windows (~28–34 MB on macOS) | `github.com/PiGON-AI/Echotools-Runtime` (our immutable release `milo-ear-v1` — assets are never overwritten; new builds get new releases) | Archive SHA-256 **and** extracted-binary SHA-256 pinned in the extension source, plus a hard size cap enforced while downloading; any mismatch is discarded and nothing is installed |
| The film links in the Meet EchoAvatar panel ("Watch on echotools.dev", "Watch on Instagram") | Only when you click one | opens your browser | `echotools.dev`, or Instagram (`@codepeeps`) | n/a — browser navigation; the film doesn't ship in the package, and the panel itself loads nothing remote |
| The one-time review invitation's buttons, and the menu's "Report a problem" and "Suggest an idea" (and the Report bugs pill) | Only when you click them | opens your browser | the Marketplace listing, or `github.com/PiGON-AI/echotools`, the suite's one home for reports and ideas (the form opens with EchoAvatar chosen) | n/a — browser navigation |
| The red "Report it" pill under Milo — present only while EchoVoice reports it can't read a partner's transcripts | Only when you click it | opens your browser | `github.com/PiGON-AI/echotools` — the suite's bug report form, with EchoVoice chosen, pre-filled with the two extension versions, your editor's name, and your operating system's name, all visible and editable before you send | n/a — browser navigation; nothing is sent until you press Submit yourself |
| The "Support Milo" doors — the one-time invitation's three buttons (review, follow, coffee) and the menu group of the same name | Only when you click one | opens your browser | our listing on the store your editor uses (the Microsoft Marketplace in VS Code, Open VSX in other editors), Instagram (`@codepeeps`), or Buy Me a Coffee | n/a — browser navigation |
| **Get EchoMemory** — the button on the pop-up when you reach for Milo's brain without EchoMemory, and on the one-time note after this update | Only when you click it | opens EchoMemory's page in your editor's Extensions view (if that fails, in your browser) | the store your editor installs from: the Microsoft Marketplace in VS Code, Open VSX in other editors | n/a — the editor's own store; installing is your click there |
| **The dance-floor archive** — the previous release's retired music (4 tracks) plus Xie's screensaver film and its soundtrack | Only when you choose "Get the dance-floor archive" from the menu, after a dialog that names the download and its size. Never automatically; never on install or update | ~12 MB, once (6 files) | `github.com/PiGON-AI/Echotools-Runtime` (immutable release `avatar-archive-v1` — assets are never overwritten; a new archive gets a new release) | The pack's manifest has its own SHA-256 pinned in the extension source; every file's SHA-256 and byte count are pinned in that manifest; each file streams under a hard size cap to a `.part` name and is renamed into place only after its hash matches. Any mismatch is discarded. "Remove the archive" deletes it in one command |
| **Milo's office** (Tech support) — our website `echotools.dev/office/embed`, shown inside Milo's window | Only when you open Tech support and agree to the notice that says it's our website, shown from outside | the page itself, like any web page | `echotools.dev` | The frame may play sound and write to your clipboard, nothing else: camera and microphone are refused, and a sandbox keeps anything it opens inside it. Milo accepts only a fixed set of messages from it, from that address only. The office takes typed text only: Milo never reads or sends your logs, files or images, and what you type or paste is part of the conversation, which `echotools.dev` keeps and uses to improve Milo (see its privacy policy) |
| What Milo tells his office when it opens | Each time the office opens, and only then | well under 1 KB | sent to `echotools.dev` | **Versions and states only:** which EchoTools you have and their versions, your editor's name and version, your operating system (Windows, macOS or Linux), light or dark theme, whether Milo is docked and his window's size, and — only if EchoVoice provides it — Voice's engine name, whether voice input is ready, and how many muted rows you have. No file paths, user names, repository names, file contents, keys or notes |
| Your name and email, for the office | Only if you ask the office to remember you, then answer **Remember me** in VS Code's own dialog; afterwards each time the office opens | a few bytes | sent to `echotools.dev` only — never to a test or preview address | Kept in VS Code's secret storage (below); "Forget me in Milo's office" in his menu removes it and tells an open office to clear its copy |
| Links from the office (Privacy, Terms, our GitHub, the stores, the coffee page) | Only when you click one in the office | opens your browser | only `echotools.dev`, `pigon.ai`, `github.com/PiGON-AI`, `buymeacoffee.com/pigon`, our Marketplace and Open VSX pages; any other address is refused | n/a — browser navigation |

That is the whole table on purpose. Everything else Milo is — this release's
music, sound effects, films, recorded lines, wake-word models — ships inside
the extension package. The audio he animates arrives from **EchoVoice on your
machine**; EchoAvatar itself reads no transcripts. Apart from his office
(above, only when you open it), his panel's security policy doesn't allow
the webview to fetch beyond the editor's own resource origin.

### What goes through his sibling tools

Milo works with EchoVoice and EchoMemory. EchoAvatar hands them things on
your machine; what *they* send is listed on their own disclosure pages.

| what | when | goes to |
|---|---|---|
| **Your words when you talk to Milo** (held microphone, "Hello Milo", or typed in his notebook) | Only for words that aren't one of his own commands, and only after you turn his brain on (one consent card, then your model's own consent). Off by default | EchoAvatar passes the **text** to EchoMemory on your machine; EchoMemory sends it to the model you chose: GitHub Copilot in VS Code, or Ollama (on your machine, or Ollama's cloud if you picked a cloud model), together with what Milo needs to answer: your saved notes, today's date and time, EchoTools' guides, and, only when a question needs them, your project's file and script names, its own commands and skills, and your usage numbers. See EchoMemory's disclosures |
| **Turning your speech into text** | Each time you hold his microphone or say "Hello Milo" | Nowhere: EchoVoice's Whisper pack does it on your machine. Downloading that pack is listed in EchoVoice's disclosures |
| **Codex's usage line and the Check Claude usage button** (break care, 3- and 5-hour check-ins) | Only at those check-ins, and the panel only on your click | EchoAvatar asks EchoMemory on your machine for the line (how Memory gets it is on its disclosure page); the button opens Claude Code's own panel |

**Your voice never leaves your machine.** The wake word and voice commands
are recognized on-device by bundled openWakeWord-style models. Audio is
written to disk only as the short talk recording (deleted once it's
transcribed) and, if you separately opt in, as Ear Clips (below). It is
never uploaded; no code path exists that could.

## Storage — what's on your disk and how to remove it

| what | where | remove it |
|---|---|---|
| Provisioned FFmpeg engine (+ its license text) | the editor's global storage folder for this extension (`ear-runtime/`) | turn the ear off and delete the folder, or delete it after uninstall via your OS file manager |
| The dance-floor archive (4 retired tracks, Xie's film and its soundtrack, and the manifest — ~12 MB), **only if you asked for it** | global storage (`packs/dance-floor-1-archive/`) | "Remove the dance-floor archive" in Milo's menu — one command, everything gone |
| Ear clips — short 3-second WAVs of the moments Milo hears (or almost hears) his name, **only if you opt in** (its own consent moment, off by default) | global storage (`ear-clips/`), capped at 50 MB, oldest deleted first | "EchoAvatar: Delete Stored Ear Clips" — one command, everything gone |
| Calibrated command thresholds (numbers only, offered by Milo, applied by you), and the choices you make in his menu — your microphone's name, the path of your own music folder, the room dim | your **user** `settings.json` (`echoavatar.commandThresholds`, `echoavatar.wakeMic`, `echoavatar.musicFolder`, `echoavatar.swarmRoomDim`) | edit or empty the setting; "EchoAvatar: Reset Milo's Ears to Standard" for the thresholds; "Stop using my folder" in the menu for the music folder |
| A short recording each time you **hold to talk** (or Milo listens hands-free), so EchoVoice's Whisper can turn it into text on your machine | global storage (`talk/`); each one is deleted as soon as it's transcribed, and nothing is sent anywhere | automatic |
| Which VS Code window owns the microphone, so two windows never listen at once (no audio, no content) | `~/.echoavatar/ear-owner.json`, refreshed every 2 seconds while the ear is on | deleted when the ear stops; safe to delete anytime |
| A tiny empty marker per wake word, so only one window answers "Milo" (no audio, no content) | your system's temp folder (`echoavatar-wake-…`) | swept automatically after a minute |
| Your name and email for Milo's office, **only if you said "Remember me"** | VS Code's secret storage (your operating system's keychain; never `settings.json`, never synced). If your system has no keychain, nothing is kept | "Forget me in Milo's office" in Milo's menu |
| Consent flags and small memories (introduced himself, ear consent given, the office notice agreed) | the editor's extension state store, and the office notice's "agreed" in his window's own storage | uninstalling the extension; the flags carry no content |

Playback happens inside Milo's window. The only audio EchoAvatar writes is
the short recording above when you hold to talk, deleted as soon as it's
transcribed, and the ear clips, only if you opted in. With push to talk the
microphone is open only while you hold his button and about two seconds
after you let go;
with his wake word on, it stays open so he can hear «milo», whether or not
his window is open. The status-bar badge shows a microphone whenever it's
open. Break check-ins are computed from keyboard activity in memory;
nothing about your sessions is stored or sent.

## Platform notes — the kinks, up front

- **Sound needs one click.** Browsers (and therefore VS Code webviews)
  refuse autoplay until a page is clicked once. Milo shows a hint until you
  do — it's a policy, not a defect.
- **The wake word is experimental — field-tested on Windows and on an
  Apple-silicon Mac in this release** («milo» and his commands fired on
  both). Intel Macs are untested. Push to talk works on
  Windows and Apple-silicon Macs, where EchoVoice offers its Whisper pack. It needs a microphone and your OS's
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

All bundled audio is credited in [`CREDITS.md`](CREDITS.md): three original
tracks by **Austin Green (Lord Austin)** included with his permission (one
of which also scores Milo's intro film on echotools.dev), royalty-free music and
sound effects from Pixabay, and Milo's own recorded lines and vocal
reactions (owned by PiGON EVOLUTIVE AI LLC). Nothing is streamed, generated at
runtime, or offered for standalone download.

## Affiliation

EchoAvatar is an independent project by PiGON Evolutive AI. It animates audio produced
locally by EchoVoice from the AI coding tools you've installed; it is not
affiliated with, sponsored by, or endorsed by Anthropic, OpenAI, Google, or
Moonshot AI. Product names are used only to state compatibility.

## Provenance

EchoAvatar is built as a human–AI partnership — see `llms.txt` for the
briefing we ship for AI models, and `AI-PARTNER.md` for the guide your own
AI assistant can use to help you set up. Contact: milo@echotools.dev.
