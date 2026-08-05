# Changelog

## 0.18.53 — 2026-08-03

The launch-eve polish: everything six independent judges and our first
outside tester agreed on.

- **Mute now silences the screensaver too.** Xie's drift soundtrack was the
  one sound the Mute button couldn't reach — it connected straight to the
  speakers. Watch the night shift with your own music on. (Thanks, Austin.)
- **Original music by Austin Green (Lord Austin).** A fifth dance track for
  the robot and a fifth chill track for the swarm — the first outside artist
  in Milo's world. Links in CREDITS.
- **You can finally discover what Milo hears.** The "ear ready" message now
  lists the commands; a new "What can Milo hear?" menu item (and command)
  shows all eight with how to say them; and saying his name while his window
  is closed now explains itself once instead of silently ignoring you.
- **You'll always see when his ear is on — for real now.** A microphone
  badge appears in the status bar whenever Milo is actually listening, and
  disappears the moment he isn't. The consent card promised this; now the
  product keeps it.
- Mac users get Mac instructions in the microphone-permission message
  (it used to point at Windows settings).
- Corrected the screensaver description (no more phantom "Meet Xie" button;
  PokieVault spelled right) and removed two stale walkthrough pages that
  described features that don't exist.

## 0.18.52 — 2026-07-29

- **"Open settings" is parked until its model is retrained.** The voice
  command shipped yesterday with a model that turned out to hear some
  synthetic test voices but not real people reliably — verified with
  cross-tests against every other command. Rather than ship a word that
  ignores you, it's out of this launch. Milo's ask-with-pills experience
  stays built in and returns the moment a stronger model lands.
- Eight voice commands ship, all field-verified: Milo dance / stop /
  repeat / sleep, and open Claude / Codex / Gemini / Kimi.

## 0.18.51 — 2026-07-29

- **"Open settings" now talks back.** Say "Milo… open settings" and instead
  of guessing which settings you meant, Milo asks — three pills appear in his
  window: EchoVoice, EchoAvatar, or all of VS Code. Click one and that page
  opens. Click "never mind" (or just ignore him for 12 seconds) and the
  question goes away quietly. If his window is closed, the command opens the
  Echo suite's settings directly rather than doing nothing.
- **Removed the "Teach Windows my voice too" button** from the tuning
  completion message. It launched Windows' speech-training wizard to help an
  experiment that ended — ten minutes of a stranger's time feeding a dead
  lane.

No changes to how Milo listens.

## 0.18.50 — 2026-07-29

Lighter on your machine, shorter to set up. Listening behavior is otherwise
unchanged from 0.18.49.

- **Milo stops working through silence.** After you say his name, command
  models used to keep scoring every slice of audio for the full nine-second
  window — even when nobody was talking. They now run only while a voice is
  in the room (and for about a second after), which cuts the ear's busiest
  moment by roughly two-thirds. In a noisy room he simply behaves exactly as
  before — the gate only ever errs toward listening more.
- **"Tune Milo to my voice" is 15 takes, not 33.** It now covers his name and
  the four commands that genuinely vary by voice — "Milo sleep", "Milo
  dance", "Milo stop", "Milo repeat". The "open …" commands fire reliably
  without tuning, so asking three takes each was ceremony.
- **The "computer" command is retired.** It was the last word that needed the
  old say-"Milo"-then-wait cadence, and Open Claude / Codex / Gemini / Kimi
  cover the doors people actually open. It may return later as "Milo open
  terminal".
- **The Windows speech-race experiment setting is gone.** The experiment
  ended two builds ago; the switch did nothing and advertising it was
  dishonest. Removing the setting changes no behavior.

Verified before shipping: the three trained commands with recorded test audio
fire at exactly the same rates through the new gate as without it — it skips
silence, never speech.

## 0.18.49 — 2026-07-29

**Milo listens exactly the way he did in 0.18.46 again.**

0.18.47 changed how he hears, and two of those changes made him harder to
talk to — his four one-breath commands ("Milo dance", "Milo stop", "Milo
repeat", "Milo sleep") and eventually his own name. Rather than keep patching
the patch, the entire listening path is restored to the 0.18.46 version that
worked, byte for byte.

Kept from the newer builds, because none of it touches listening: the
third-party licences and notices this package owes, and the corrected
description of what it downloads.

## 0.18.48 — 2026-07-29

Two fixes from 0.18.47 made Milo harder to talk to. Both reverted.

- **The four spoken-in-one-breath commands work again.** "Milo dance", "Milo
  stop", "Milo repeat" and "Milo sleep" had become nearly impossible to
  trigger: 0.18.47 required a pause after his name before any command could
  fire, and there is no pause inside a single-breath phrase.
- **Milo hears his own name again.** The new audio buffer held 640
  milliseconds, but recognizing the wake word needs about 1.28 seconds of
  sound — so the start of "Milo" could be discarded before he ever heard it.
  The buffer now holds four seconds.

Kept from 0.18.47, because those were right: Milo stops listening while his
own voice is playing, audio survives split sample frames, he reports ready
only once he is really hearing, one window owns the microphone, and turning
the ear off always wins.

## 0.18.47 - 2026-07-29

- Saying only "Milo" can no longer be mistaken for a command. Milo waits for
  the wake phrase to end and for new speech before command models can act.
- Milo stops listening while his own voice is playing, then starts a fresh
  command window when the reply or wake acknowledgment ends.
- Microphone audio now survives split sample frames, cannot build an unbounded
  stale queue, and reports ready only after capture actually begins.
- Only one VS Code window owns Milo's microphone listener. Turning the ear off
  now wins even if an older consent, download, or microphone prompt finishes
  late.
- Voice handoffs fail safely instead of hanging, and a minimized floating Milo
  reliably rebuilds his docked renderer for the next reply.

## 0.18.46 — 2026-07-29

- **«Open Gemini» opens a panel, not a terminal.** In VS Code it opens
  Gemini Code Assist's chat in the left activity bar. In Antigravity — where
  Gemini *is* the editor — it opens the agent panel on the right. Same word,
  the right door for wherever you're working.
- Doors are checked against the editor's command registry before anything
  runs, so a command an editor doesn't have is skipped rather than attempted
  and failed. If no panel exists at all, the CLI in a terminal is still the
  last resort — better a terminal than silence.

## 0.18.45 — 2026-07-29

Three new voice commands, trained by Myriam.

- **«Milo stop»** — stops speech and the music together.
- **«Open Gemini»** — say "Milo", wait for him, then the command.
- **«Open settings»** — the model ships and listens, but has no action yet.
  Saying it does nothing on purpose; the version that asks *which* settings
  you mean arrives with Milo's spoken replies.
- **«Summarize» is retired for now.** It opened EchoMemory, which isn't part
  of this launch. It returns with EchoMemory as the single-breath "Milo
  summarize".

Ten command heads now listen. Nothing else changed.

## 0.17.9 — 2026-07-18

Round three of the independent review.

- **Replacement reasons:** when one clip replaces another mid-utterance, the
  replacing id now travels with the event. Deliberate user actions (Dance,
  Say hi) resolve the interrupted reply as spoken; any UNEXPECTED
  replacement declines the handoff so EchoVoice falls back to classic
  playback instead of losing the reply silently.
- CREDITS.md now inventories every original recording (intro, wake lines,
  break check-ins, scroll-tease, vocal reactions, soundscapes), making the
  third-party notices' "full inventory" claim true.
- llms.txt formatting fix; the shared public issue tracker is documented as
  deliberate (it is the only public tracker until the storefront repo
  exists at launch).


## 0.17.8 — 2026-07-18

Round two of the independent multi-model review.

- **The asleep-reply fix, documented properly** (it shipped late in 0.17.7
  without a changelog entry): a reply arriving while the robot slept woke
  him, and his recorded wake line then replaced the very reply that woke
  him, stranding EchoVoice's queue. Triple-guarded: the wake quip yields to
  active speech; personality clips never play during a reply handoff; a
  replaced utterance resolves its caller immediately.
- A replaced utterance now reports a distinct "replaced" event (loudly
  logged) rather than posing as a normal completion, so any unexpected
  replacement path is diagnosable by name.
- **Third-party notices reconciled with CREDITS.md:** the relax tracks are
  now credited, and the notices correctly attribute the Pixabay reaction
  sound effects instead of claiming all non-music audio as original.
- Internal review notes are excluded from the package (and the ignore rules
  now guard against similar strays).
- Settings and README now describe the docked-view-default / floating-panel
  behavior accurately, including that always-on-top pinning needs VS Code
  1.100+ (older versions float without pinning).
- Copyright holder stated consistently (PiGON AI LLC); bundle banners share
  the professional register and point to llms.txt.

## 0.17.7 — 2026-07-18

Hardening and accuracy release, driven by an independent multi-model review.

- **Packaging compliance:** the extension now ships its MIT LICENSE and a
  THIRD_PARTY_NOTICES.md covering the bundled three.js renderer and the
  Pixabay-licensed music (per-track credits in CREDITS.md).
- **Documentation rewritten to match the shipped product** — the README now
  describes the two experiences, break check-ins, the tickertape, transport
  behavior, and the exact privacy posture (no telemetry, no network
  requests, all media bundled). The AI-directed `llms.txt` briefing is
  disclosed in the README.

## 0.17.0 – 0.17.6 — 2026-07-16 → 2026-07-18

The two-experiences series:

- **Two bodies, two experiences** — the particle swarm (default; minimal and
  quiet, with a classical "Chill" mode that morphs the particles through
  shapes) and the robot (playful; lip-sync screen-face, upbeat dance tracks,
  recorded greetings and wake lines, short text asides, a scroll-tease
  easter egg driven by the eye-tracking signal).
- **Speech preempts music** — an incoming response stops any playing track,
  visuals and controls included.
- **Recorded break check-ins** at 90 minutes / 3 hours / 5 hours of
  continuous keyboard time, each with its own off switch.
- **The session tickertape** under the avatar names the Claude Code session
  being spoken; names set with `/rename` survive Claude Code updates.
- **Stop wired to EchoVoice** — stopping the avatar halts the speech queue,
  so playback doesn't restart mid-transcript.
- Body switching works while docked; the halo appears only during speech and
  dance; WebGL context loss recovers instead of crashing.

## 0.1.0 – 0.16.x — 2026-07-09 → 2026-07-15

Initial development: the particle being, audio engine with real-time
analyser, docked/floating windows, per-agent color identities, emoji
reactions with bundled sounds, backgrounds, idle shapes, and the EchoVoice
playback handoff.
