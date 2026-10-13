# Changelog

## 1.1.0 — Milo talks back

**Why 1.1.** Until now Milo listened for a handful of words and danced. Now
you can talk to him. Hold his microphone and ask, or say "Hello Milo", and he
answers in his own voice and writes the answer in his notebook. His window is
redesigned around that: one microphone under him, a menu of pills, a notebook,
and a status strip that tells you how he's listening. This release ships
together with EchoVoice 1.1.0 and EchoMemory, and Milo's brain comes from
EchoMemory.

### Talk to Milo

- **Hold to talk.** Hold the microphone under Milo, speak, and let go. Tap it
  instead and his menu opens. Space and Enter do the same from the keyboard,
  and **EchoAvatar: Talk to Milo** opens the mic for keyboards and voice
  control.
- **Three ways to listen,** your choice in his menu: **Off**, **Push to talk**
  (the mic opens while you hold his button and closes about two seconds
  after you let go), or **Wake word** (say his
  name, hands-free, plus the button). Everything he hears is recognized on
  your machine. Free speech uses EchoVoice's on-device Whisper pack; nothing
  you say leaves your computer to be transcribed.
- **"Hello Milo"** opens his ear for a question; "Milo" alone and his phrases
  ("Milo, dance", "Milo, stop", "Milo, sleep", "Milo, repeat") are each their
  own door. **"Milo, talk"** opens the mic hands-free and **"Milo, stop"**
  closes it, and so does a pause: he closes the mic when you stop talking.
- **"Anything else?"** After he answers a spoken question, Milo asks once
  whether there's more, and listens for your answer. At most three rounds,
  never after his own little lines.
- **He knows his own ears.** *What can Milo hear?* lists every phrase.
  *Check Milo's hearing* scores six phrases per microphone. *Tune Milo to my
  voice* now includes "Hello Milo". Two misses in a row and he asks whether
  it's the right microphone, with a card to choose another.
- **One ear per machine.** With several VS Code windows open, only one
  listens; pressing his button in another window moves the ear there.
- **Your microphone, only when you need it.** In push to talk the
  microphone opens when you press his button and closes about two seconds
  after you let go, and the status-bar mic badge shows only while it's
  actually open. If the microphone keeps failing, he stops after three tries
  and tells you once how to fix it.
- **Hold to interrupt.** Holding his microphone quiets whatever EchoVoice is
  reading, so he never hears himself as your words.
- **He hears you, not the room.** His name needs a little more certainty,
  and "Milo, dance" said without his name first needs more still, so a sound
  in the room doesn't open his mic or start the music. The hands-free mic
  never opens over playback, and a clip that runs on without a pause (a video
  in the room) is dropped, not answered.

### His brain

- **Milo answers questions.** With EchoMemory installed and your one-time
  yes, anything you say that isn't one of his own words goes to his brain:
  **GitHub Copilot** in VS Code, or **Ollama** (local or cloud) in editors
  without Copilot. His status strip says which. Nothing is turned on for you,
  and every change he proposes to your memory waits for your yes.
- **He answers from the notes you've saved** and shows only the notes he
  actually drew on. Ask about a tool (a slash command, a skill, a hook, an MCP
  server) and he answers from EchoMemory's catalog, with up to three tips you
  can save as notes, each saved once.
- **When he can't do something,** he can draft an email to the team in your
  own mail app. Nothing is sent for you.
- **When there's no model behind him,** one clear pop-up says what's missing
  (GitHub Copilot in VS Code, or Ollama elsewhere) and offers to reload
  VS Code once it's set up.
- **When EchoMemory isn't installed,** Milo says so the moment you talk or
  type to him or turn his brain on, and a **Get EchoMemory** button opens its
  page in your editor's Extensions view. After this update, a one-time note
  says the same thing.

### The notebook

- **One page for everything he says.** His answers type out on a paper page
  at the pace of his voice, with older pages a tap away. Each answer can be
  saved as a note, copied, or rated 👍 / 👎.
- **You write to him there.** The old text box is gone: the notebook's
  writing line is where you type to Milo.
- Its footer links (Tech support, Support Milo, the Code Peeps) open in a VS
  Code tab where your editor has one.

### His new room

- **Three doors along the bottom:** **Menu** on the left, the **microphone**
  centred under Milo, the **Notebook** on the right (it reads "Aa" until you
  first open it).
- **The menu is two pages of pills.** The first holds what matters most:
  Inbox, Report bugs, Tech support, Contact, Mute, Pop out / Dock, Support
  Milo. The second: Dance or Chill, Stop, My music…, Read emojis, Robot or
  Swarm, Ambient, Rate us, Screensaver, and Hide (only when he floats).
- **The status strip** shows one fact at a time (how he listens, which
  microphone, which brain, your Inbox), pauses under your mouse, and carries
  a green Inbox dot that turns into a count when notes are waiting.
- **Readable everywhere.** A− and A+ change the size of everything in his
  window, and no text is ever smaller than 11 px on screen.
- **Calmer.** The encouragement bubbles are retired, and every control says
  what it does when you hover over it. The corner never tucks away before
  you've used it once.
- **Hide comes back.** Hide (floating only) now always brings him back: from
  his menu's *Open Milo*, on the next reply, or from his icon in the side bar.

### Milo's office

- **Tech support opens Milo's office inside his window.** After a short
  notice that says it's our website, `echotools.dev`, he drops out of view,
  pops out if he was docked, and the office opens. "← Milo" brings him back,
  docked again if he was.
- **The office is boxed in.** It may play sound and use the clipboard,
  nothing else: no camera, no microphone, and nothing it opens can leave his
  window.
- **The office knows your setup.** When it opens, Milo tells it which
  EchoTools versions you have, your editor, your operating system, your
  theme, and his window's size, so it can answer for your exact setup.
  Nothing else: no file names, paths, code or user names.
- **Remember me.** If you ask the office to remember you, VS Code asks
  first; your name and email are kept in your editor's secure keychain and
  handed only to `echotools.dev`. **Forget me in Milo's office** in his menu
  erases them from the keychain and asks an open office to forget its copy.
- **Links from the office** (Privacy, Terms, our GitHub, the stores) open in
  your browser; any other address is refused.
- **Get help from Milo, from every EchoTools menu.** EchoVoice's,
  EchoAvatar's and EchoMemory's menus all open his office in his window.
- **The notice says what's kept.** The office takes typed text only (no
  files, images or logs); its conversations are kept and used to improve
  Milo, as its notice and our privacy policy say.

### Break care

- **At the 3- and 5-hour check-ins,** Milo adds Codex's real usage when
  EchoMemory has a fresh reading, and a **Check Claude usage** button that
  opens Claude Code's own Usage panel. He never guesses a number.

### His menu

- **Trimmed to what the pills can't do, in four sections like EchoVoice's
  menu:** *Milo* (open him, his introduction, idle shape, room brightness,
  the dance-floor archive), *Listening* (how he listens, what he can hear,
  tuning, the hearing check), *His brain* (**Milo's brain**, and Forget me
  once his office remembers you) and *Help* (**Get help from Milo**, **Show
  the EchoAvatar log**, Report a problem, Suggest an idea, the walkthrough,
  settings). Everything removed is still a command.
- **Report a problem** and **Suggest an idea** now open forms in one home,
  `github.com/PiGON-AI/echotools`, with your versions filled in.

### Milo is getting shredded

- **About 10 MB lighter: 51 MB → 41 MB to download.** His four-minute intro
  film now lives on [echotools.dev](https://echotools.dev/#echoavatar) and
  [Instagram](https://www.instagram.com/codepeeps/). **EchoAvatar: Meet
  EchoAvatar** opens a panel with both links and his quick tips.
- The walkthrough is new: watch Milo's film, meet him and his room, wake his
  sound, **talk to him**, pick his resting shape.

### Fixed

- A partner's reply no longer waits in silence when Milo's window hasn't been
  clicked yet: if he can't make sound within a second and a half, EchoVoice
  plays the reply itself.
- Silence is nothing said: a quiet clip never reaches his brain as a word.
- No console window ever blinks open on Windows when he starts a helper.
- The contact address is `milo@echotools.dev`.
- **The license, made plain:** the code is MIT; Milo, Wispie and Xie are
  © 2026 PiGON EVOLUTIVE AI LLC, all rights reserved (see LICENSE).

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
