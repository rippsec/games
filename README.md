# games

A collection of terminal-based games and gamified scripts written in Bash. The goal of this repo is to explore scripting concepts — input handling, signal trapping, concurrency, ASCII rendering — through playable, interactive programs.

## Games

### Hangman

A classic Hangman game that runs entirely in the terminal with progressive ASCII art and color feedback.

```
__  __
\\\/`/`/
 \\/  /
 /`/\  \
/`/()\  \
‾‾  ‾‾
```

**Features:**
- Pulls words from system dictionaries (`american-english` + `wordlist-probable.txt`) for a large, varied word pool
- Falls back to a local user copy (`~/.local/share/dict/`) if system dicts are absent — bundled wordlists included in the repo
- Filters to lowercase alpha-only words for a clean gameplay experience
- 6 attempts — the ASCII art builds up progressively with each wrong guess
- Duplicate guess detection with inline error messages
- Clean `Ctrl+C` handling via signal trap

**Usage:**
```bash
cd hangman
bash hangman.sh
```

**Dictionary resolution order:**
1. `/usr/share/dict/` (system)
2. `~/.local/share/dict/` (user local)
3. Script directory — copies to `~/.local/share/dict/` on first run

## Structure

```
games/
└── hangman/
    ├── hangman.sh           # Game script
    ├── american-english     # Bundled system wordlist
    └── wordlist-probable.txt # Bundled common-words wordlist
```

## Planned

More gamified scripts coming — each one focused on a different scripting concept.
