# Phase 1 — Foundations

Series premise, structural frameworks, faction overviews, and the world skeleton. This phase must be stable before reliable beat sheets can be written.

**Status: In progress**

---

## Goals

- [ ] All faction overviews complete (not stubs)
- [x] Series premise documented
- [x] KWML + Harmon Circle + 3-act frameworks mapped
- [x] Universe timeline established
- [x] Faction motivations (Want/Need/Idea) for all four major players
- [ ] All 6 society files substantive (not placeholders)
- [x] World technology document complete
- [x] World locations document complete
- [x] World society document complete

## What "Foundation-Level" Means

A faction overview is foundation-level when it answers:
- What do they do, and how?
- What is their philosophy?
- What is their role across the 7-book arc?
- What is their relationship to the series' central conflict (Freedom vs. Evolutionary Pressure)?

A society file is foundation-level when it answers:
- How did this culture survive to the ~3000s?
- What are their defining characteristics in this era?
- What role do they play in the story (minor color, major faction, etc.)?

## Outstanding

- Brazilian Mafia overview (stub → full)
- Serbian Mafia overview (stub → full)
- Earthtech 48-laws (empty → full, pending name decision)
- Resistance 48-laws (empty → full)
- All 6 society files (placeholders → substantive)

## Phase 1 is Complete When

All four mafia factions, Earthtech, the Resistance, the Memes, and the E-Thots have full overviews. All 6 society files have at least a paragraph of substantive content per major heading.

---

## Untrack the Final-Text Folder

**The actual conclusive, copyrightable manuscript prose for this series must never be tracked by this git repo.** This repo (`TheCryptographHelixDD`) is the design-document/outline layer only — fine to keep public. The real prose lives in `../official text/Book 1` through `Book 7`, a sibling folder one level up, deliberately kept outside this repo entirely rather than gitignored inside it. That's the current convention and the strongest version of "untracked" — don't move it in.

If that ever changes (e.g. prose moves to a per-volume `text/` folder inside `books/book-XX/volume-Y/`), add the specific path to `.gitignore` *before* writing any real content into it — `.gitignore` already has defensive `text/` patterns as a fallback safety net, but don't rely on those alone; add an explicit entry the same way `CurrentNovelDocs` does per-novel. If prose is ever accidentally committed, it's not enough to just untrack it going forward — it also needs purging from git history (`git-filter-repo`, then force-push), since the goal is keeping it out of the public repo before copyright is filed, not just out of future commits.
