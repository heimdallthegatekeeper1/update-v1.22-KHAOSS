KHAOSS v1.22
A local multi-agent stack: the AionUi desktop app (team orchestration UI) + the Hermes agent runtime
    • a CPU-only voice stack (piper TTS / whisper.cpp STT, optional XTTS voice cloning).
Phase-1 package. This is the clean scaffolding + installer + example teams + voice stack. The heavy app/runtime are fetched and built by the installer (see aionui/SETUP.md, hermes/SETUP.md). It ships no teams, conversations, keys, or operator data.
Install
./install.sh                      # full install + self-verify into ~/.khaoss
./install.sh --voice-only         # just the voice stack + self-verify
KHAOSS_HOME=/tmp/khaoss ./install.sh   # install into a fresh location
The installer downloads the CPU-only models, starts the voicebox, and self-verifies (health → synth → transcribe). Voice cloning (XTTS) is optional and deferred.
Example teams
Generic starter teams live in example-teams/ (Personal Assistant · Research Pod · Build Squad · Debate Circle). Create them in AionUi after setup; pick the leader's Hermes profile at creation.
Your AI, your choice (privacy first)
Run the Personal Assistant local (Ollama — nothing leaves your machine) or privacy-scrubbed cloud (strongest models; the regex scrub redacts secrets/PII before anything leaves). Privacy is the default. See PRIVACY_AND_AI_CHOICE.md.
Provider keys
You supply your own provider keys locally (entered into the app / the general Hermes profile). None are bundled. Choosing local means no key and no cloud at all.
Verify it's clean
./scan_clean.sh    # must report 0 hits; see CLEAN_SCAN.log
Components
    • AionUi — Electron team-orchestration UI. See aionui/SETUP.md.
    • Hermes — agent runtime. See hermes/SETUP.md.
    • Voicebox — voicebox/tts_server.py (piper TTS + whisper.cpp STT on :8770).
