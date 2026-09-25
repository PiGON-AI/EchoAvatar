# Changelog

## 1.0.0

**Why 1.0.** Milo speaks, sees when a partner's transcripts stop making sense
and says so, works without a mouse, respects your reduced-motion setting,
tells you exactly what he costs and what leaves your machine (nothing, unless
you ask), and ships with a watchdog, a report door, and a verified archive.
The preview label comes off. Everything below is what changed since 0.19.4.

- **Dance Floor 2.0 — every track has its own choreography.** Milo no longer
  dances to a generic beat. Each of the robot's five tracks has a performance
  Myriam authored by hand — nods, jumps that land, spins, sways, shivers on
  the busy parts, faces that change with the music, and words that appear on
  his body at the right moment. The swarm's five chill tracks flow through
  their own shape cycles. Everything follows the actual song position, so
  pause, resume and replay stay in step, and every cue ends when the music
  does. A real alert from the watchdog still wins over any dance, your
  reduced-motion setting still stills him, and dancing can be switched off
  entirely. Your own music and the archive's tracks keep the classic
  beat-reactive dance.
- **A new dance floor.** Two new dance tracks — a second original by
  Austin Green (Lord Austin) and a summer track — and two new chill tracks,
  alongside three familiar ones per body. The tracks they replace haven't
  gone anywhere: they're in the **dance-floor archive**, one click away in
  Milo's menu (*Get the dance-floor archive*, ~12 MB, fetched from our GitHub
  only when you ask, every file checked against a pinned fingerprint before it
  can play, removable in one command). The first time you dance after
  updating, Milo offers it once — and never nags.
- **Milo dances to your music.** *My music…* in his menu opens a folder
  picker; your mp3, wav, ogg and m4a files join his playlist (`dance` and
  `chill` subfolders sort the moods, a flat folder feeds both). They never
  leave your machine.
- **The swarm's room can be dimmed** — *Room brightness (swarm)…* in the menu,
  five steps from "as filmed" to "almost night" — so a being made of light
  pops against the film without losing its colour. The robot's room is never
  dimmed.
- **The screensaver's speaker button is ours now** — a drawn line icon in the
  house cyan instead of an emoji.
- **Milo actually sleeps under the screensaver.** He used to keep animating at
  full speed underneath the film where nobody could see him; now he stops
  rendering the moment the film has faded in and wakes the instant the shift
  ends. Quieter fans, longer battery, nothing visible changed.
- **Wispie takes a shift.** Wispie, the air spirit, joins Xie on the night
  shift — they take turns, one per shift, remembered across sessions. Xie's
  film rides in the archive; Wispie's ships with Milo, looping without a
  seam. Both carry a small `@pokievaults` mark — that's where the characters
  come from.
- **The room dims the longer he sleeps.** A shift arrives as filmed, and if
  nobody comes back it settles over the first five minutes into a calmer,
  softly vignetted look — the way a room does when everyone's gone. It's one
  still layer the compositor fades; no per-frame work, so it costs nothing.
  The moment you're back, the next shift starts bright again.
- **New 3D rooms for both bodies.** The robot floats in a wormhole — a lit grid
  floor, debris drifting past, light bending around the dark — and the swarm
  drifts in a deeper, quieter whirl of its own. Both were made for this
  release, looped seamlessly so the room never jumps, and encoded down to
  1.5 MB each so they cost almost nothing. They're built to enhance, not to
  distract: the robot's room is bright behind a glossy body; the swarm's is
  dim by design so a being made of light stays the brightest thing in the
  frame — and *Room brightness (swarm)…* in the menu lets you tune exactly
  how dark, lifting the swarm's glow as the room goes down.
- **Support Milo, three doors.** The one-time invitation after 25 replies now
  offers ⭐ Review · 💙 Follow · ☕ Coffee, and the menu has a *Support Milo…*
  group with the same three, visible whenever you want them and never pushed.
- **The package holds its weight:** new music, a new screensaver and new rooms
  in, and the extension grew by about 3 MB — 45 to 48 MB to download.

## 0.19.4

- **Milo tells you when he can't hear a partner — and what to do about it.**
  Your coding partners save their conversations in files we don't control,
  and if one of them changes its format, EchoVoice goes quiet — and until now,
  quiet-because-broken looked exactly like quiet-because-idle. Now EchoVoice
  notices when a transcript changed but nothing in it made sense, and Milo
  shows it: red X's for eyes (the swarm wears a red **!**), a line under him —
  *"I can't read Claude Code right now"* — and he says so out loud, each body
  in its own voice, once per machine (not once per open window), waiting his
  turn if a partner is mid-reply. A red **Report it** pill
  appears under him for exactly as long as the problem lasts; one click opens
  a bug report in your browser, pre-filled with the versions, your editor, and
  your OS — all visible and editable before you send. It's us, not you, and
  now you can tell us in one click. Everything clears the moment things make
  sense again.
- **Milo works without a mouse.** His window is a real button — Tab to it (or
  run **Focus on Milo View** and land right on him), press Enter, and a screen
  reader hears exactly what to do: wake his sound, or say hi once it's awake.
  The voice-tuning card and the
  "which settings?" card are proper dialogs now: their small dismiss links are
  real buttons, Escape closes them, and the keyboard is never left stranded.
  Every control shows a visible focus ring. His action pills can be reached by
  Tab even while faded, and they no longer vanish while you're on one. Xie's
  speaker button tells assistive tech whether it's muted. And when Milo can't
  read a partner, a screen reader hears it, not just sees it.
- **Milo respects your reduced-motion setting.** If your system asks for less
  motion, he holds still: no hovering or swaying, no spinning halo, no dance
  moves or body bounces; the swarm stops turning and drifting and changes shape
  in a snap instead of a glide. He still blinks, still looks at you, still
  moves gently with speech — a living Milo, just a still one. Follows the OS
  setting live, no reload needed.
- **Under the hood.** The debug overlay (`echoavatar.debugOverlay`) now shows
  Milo's frame rate and worst frame, so "is he stuttering?" has a number. And
  the messages waiting for his window to load are bounded, so a window that
  never finishes loading can't quietly eat memory.

## 0.19.3

- **Xie got her own speaker.** The most-asked-for fix since launch: you can
  now mute the screensaver's soundtrack without muting Milo — a speaker
  button on the night shift itself (it won't wake him), or the new
  `echoavatar.screensaverSound` setting. The Mute pill still silences
  everything, as a master mute should.
- **💡 Suggest an idea** — a new menu item that opens our suggestion box.
  Tell us what to build next; we actually read it.
- **Coming soon: EchoMemory** — a peek at the suite's next organ in the
  readme, plus a Support Milo section for the CodePeeps keeping the
  lights on. ☕

## 0.19.2

- EchoAvatar wears its mark: ™ on the listing name (the readme had it
  already).
- Milo asks for a review — once, ever: after 25 replies genuinely spoken
  through him (his own chatter and music don't count), a single
  invitation with a "Don't ask again" that means it.

## 0.19.1

- EchoVoice's Marketplace identifier changed to `pigonai.echo-voice`
  (same product, same name — a store-side identifier migration); Milo's
  dependency now points at the new ID so the automatic install keeps
  working everywhere.

## 0.19.0 — Initial public release

EchoAvatar gives your AI coding partner a visible, living presence in
VS Code — Milo, a particle being who moves with your partner's actual
voice. This first public release includes:

- **Two bodies, switchable anytime**: the swarm — thousands of particles
  resting in a shape you choose, becoming a brain while your partner
  speaks — and the robot, a hovering screen-face who lip-syncs, greets
  you, chats, and dances.
- **Voice-synced animation on every EchoVoice tier** — system voices,
  Kokoro, Piper, and ElevenLabs. Each partner keeps its own color while it
  speaks, and a session tickertape names who's talking.
- **Dance & Chill**: bundled royalty-free tracks plus originals by Austin
  Green (Lord Austin) — Milo finds the actual beat. Speech always
  preempts music.
- **Milo's Ear** (experimental, Windows, off by default): say «milo» and
  he answers in his own voice; eight voice commands, recognized entirely
  on your machine. Consent-first setup, a one-time checksum-verified
  audio-engine download, and a 90-second tuning flow that teaches his ear
  your voice.
- **Xie's night shift**: when Milo falls asleep, the galaxy chameleon
  drifts in as his screensaver — visual-only, ships in the package.
- **Break check-ins**: after 90 minutes, 3 hours, and 5 hours at the
  keyboard, a gentle recorded word — computed locally, stored nowhere.
- **Emoji reactions** (off by default): your partner's emojis trigger
  small animations and soft bundled sounds.
- **A narrated introduction**: "EchoAvatar: Meet EchoAvatar" — Milo gives
  the tour himself, with a full transcript and quick tips.
- **Private by construction**: no telemetry or analytics code; the ear's
  settings are machine-scoped; every byte that can touch the network is
  itemized in DISCLOSURES.md — it's one short table.
- **Pairs with EchoVoice** (required; installs automatically) — EchoVoice
  does the talking, Milo does the being.

Changes from here on are listed per release, in plain language.
