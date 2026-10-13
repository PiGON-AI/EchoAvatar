# EchoAvatar — Troubleshooting

First stop, always: **View → Output → pick "EchoAvatar"** in the dropdown.
Milo narrates every decision — every playback and its source, every wake,
every command with its score, every refusal and its reason. Most mysteries
end there.

## No sound at all
- **Click Milo once.** Browsers (and therefore VS Code webviews) refuse
  autoplay until the page has been clicked — it's a policy, not a defect. A
  hint shows until you do.
- Check the **Mute pill** under the avatar.
- Milo speaks **EchoVoice's** audio. If EchoVoice itself is silent, start
  with [EchoVoice's troubleshooting](https://github.com/pigon-ai/echovoice/blob/main/TROUBLESHOOTING.md)
  — voice problems are usually its lane.

## Milo doesn't move when my agent speaks
- The panel opens (or wakes) on the first **spoken** response — the agent
  must actually be speaking through EchoVoice on this machine.
- Check Output → EchoAvatar for a `handoff:` line. No line = the audio never
  reached Milo; see EchoVoice's channel next.

## Milo answers in the OTHER editor (two editors, one repo)
If the same repository is open in two editors at once — two VS Code windows,
or VS Code plus another IDE like Antigravity — a reply may be spoken in the
*other* editor than the one you typed in. This is EchoVoice's exactly-once
promise working as designed: agents write their transcripts **per
repository**, not per window, so every reply is spoken by exactly one
editor — whichever claims it first. There is no reliable way to attach a
reply to the window it "belongs" to. The workaround: **mute EchoVoice in
the editor you're not actively using** (its status-bar toggle) — the other
one keeps the whole conversation.

## The tickertape shows an auto-name / naming your sessions
The strip under Milo names the Claude Code session being spoken. To name
sessions yourself (Claude Code only):
1. In the session's own text box, type `/rename [your window name]` and
   press Enter.
2. Reload that window: `Ctrl+Shift+P` → **Reload Window**.
3. The tickertape channels the new name from the next reply on.
With several sessions open, name each one ("components", "launch-day") and
you'll always know who's talking. An unnamed session shows Claude Code's
own auto-generated name.

## The ear doesn't hear me («milo» does nothing)
In order of likelihood:
1. **Did you tune?** Run **"EchoAvatar: Tune Milo to Your Voice"** — six
   words, three takes each, about 90 seconds. Before tuning, commands can
   misfire; after tuning they fire reliably. Judge the ear only after tuning.
2. **Is his window open?** A closed window is deliberate silence — with the
   wake word on his microphone stays open, but Milo only answers while he's
   on screen (a one-time toast explains this).
3. **The status bar**: a **microphone badge** appears whenever his
   microphone is open — all the time with the wake word on; with push to
   talk only while you hold his button (and about two seconds after). Wake
   word on but no badge = not listening — check the menu's ear line.
4. **The right microphone?** "EchoAvatar: Choose Wake Microphone" — and
   strongly prefer a **real external mic**: laptop built-ins, webcam mics,
   and speakerphone arrays measurably degrade recognition. This is the fix
   after tuning.
5. Output → EchoAvatar narrates every wake and command **with its score** —
   commands fire only above the **0.5 confidence bar**; if yours land just
   under it, Milo will offer to adjust that command's bar himself (the
   models don't change; the listening adapts).

## Voice commands misfire or don't fire
- Every phrase is listed in-product: menu → **"What can Milo hear?"**
- Said in **one breath**: «milo dance», «milo stop», «milo repeat»,
  «milo sleep», «hello milo». Said in **two steps** — say «milo», wait for
  his answer, then «open claude» / «open codex» / «open gemini» /
  «open kimi» / «open settings».
- «milo dance» said without a pause needs a clear, confident voice: a
  half-heard phrase is held back on purpose, so a sound in the room doesn't
  start the music. After «milo» and his answer, it fires more easily.
- The command window after a wake is ~9 seconds; after that, say his name
  again.
- Opening a CLI shows a cancellable notification first — click it to abort.

## Holding his microphone does nothing
1. **Is his ear on?** Milo's menu → how he listens: choose **Push to talk**
   (or Wake word). The first time, he asks for your OK and, if needed, sets
   up his audio engine.
2. **Free speech needs EchoVoice's speech pack.** EchoVoice's menu →
   **Prepare voice input** (about 150 MB, asked first), then **Reload
   Window** when it offers.
3. **Too short?** Hold the button while you speak and let go after your last
   word; a very short tap opens his menu instead.
4. On a computer where the speech pack isn't offered, Milo says so on
   screen; his wake word and commands still work.

## The microphone light stays on
- **With the wake word on, that's by design:** he has to hear «milo». The
  status-bar badge shows it.
- **With push to talk,** the light should go off about two seconds after you
  let go of his button. If it stays on, check the menu's ear line and
  Output → EchoAvatar.
- **If the microphone keeps failing** (unplugged, or blocked in your
  system's privacy settings), Milo stops after three tries and shows one
  message with "Open microphone settings" and "Choose a different
  microphone".

## Milo hears me but doesn't answer questions
- His brain is off until you turn it on: his menu → **Milo's brain** (one
  consent card). It needs **EchoMemory** installed.
- His brain needs a model behind it: **GitHub Copilot** signed in (VS Code)
  or **Ollama** (other editors). If none is there, Milo shows one pop-up
  saying so; after setting one up, **Reload Window**.

## Tech support / Milo's office won't open or stays blank
- The office is our website, `echotools.dev`, shown inside his window; it
  needs his window and an internet connection.
- If the page never loads, his own **← Milo** button appears after a few
  seconds and brings him back.
- The office takes typed text only. What you type there is kept to improve
  Milo (see the privacy policy on echotools.dev).

## Dance or Chill does nothing
- Check the `echoavatar.dance` setting.
- Speech always outranks music: if a reply arrives mid-song, the music stops
  and the reply plays. That's by design — music is the hobby.

## The floating window won't stay on top
Always-on-top pinning needs **VS Code 1.100+** on desktop. Older versions
float without pinning. See the `popOut`, `alwaysOnTop`, and `compactWindow`
settings.

## The screensaver never shows / won't leave
- Wispie takes the night shift (with Xie too, once you've fetched the
  dance-floor archive; they take turns) only when Milo has been quiet long
  enough to fall asleep, and any sign of life ends the shift immediately.
- On demand: **"EchoAvatar: Play Screensaver"**. Off entirely:
  `echoavatar.screensaver`. The Mute pill silences her soundtrack too.

## Installed but never activates
1. **Engine gate** — Help → About: the editor must report VS Code
   compatibility ≥ 1.90.
2. **The dependency** — EchoAvatar requires EchoVoice (it installs
   automatically from the marketplace; a manual VSIX install needs EchoVoice
   installed first).
3. **Remote/WSL** — EchoAvatar deliberately runs on your local machine
   (`extensionKind: ui`): that's where your screen, speakers, and microphone
   are. In remote setups, install it locally, not in the remote.
4. **Activation crash** — Help → Toggle Developer Tools → Console: a red
   stack trace naming the extension is the murder weapon. Please file it as
   an issue with the trace.

## Where things live
- Settings: per editor, under the `echoavatar.*` namespace
- The ear's FFmpeg engine: the extension's private global storage
  (`ear-runtime/`), downloaded once with your consent, checksum-verified
- Ear clips (only if you opted in): global storage (`ear-clips/`), capped,
  removable with **"EchoAvatar: Delete Stored Ear Clips"**
- Calibrated thresholds: your user `settings.json`
  (`echoavatar.commandThresholds`) — "Reset Milo's Ears to Standard" undoes
  them
- The short recording made when you hold to talk: global storage (`talk/`),
  deleted as soon as it's turned into text
- Which window owns the microphone: `~/.echoavatar/ear-owner.json` (no audio,
  no content)
- The dance-floor archive, only if you fetched it: global storage
  (`packs/`), removable with "Remove the Dance-Floor Archive"
- Your name and email for Milo's office, only if you said "Remember me":
  VS Code's secret storage — "Forget me in Milo's office" in his menu
- The complete network and storage inventory: [DISCLOSURES.md](DISCLOSURES.md)

*This guide was distilled from real field testing — including the tuning
flow's coaching pass and the closed-window lesson, both of which exist
because real users hit them first.*
