# Mafia Faction — Template

How to build a new Mafia faction folder, or bring an existing stub up to the same standard as the Chinese/Russian files. Copy this folder, rename it to the faction's name (lowercase, matching existing conventions: `chinese/`, `russian/`, `korean/`, `brazilian/`), and fill in each section.

## Files in This Template

- `overview.md` — the faction's core identity: lineage, what they traffic, technology specialty, key events, cultural notes, cross-faction connections.
- `48-laws.md` — which of Robert Greene's 48 Laws of Power this faction follows and which they break, mirroring the existing Chinese/Russian files.

## Before You Start: Two Things That Block Real Content

1. **Lineage is a four-stage problem, and Stage 3 is blocked on InnerTepeniaGDD Phase 3.** It's not a simple one-step "real-world nation → Mafia" relabeling. The actual chain is: (1) real-world nation (historical/locator fact only, pre-2564) → (2) a specific Tepenian exile-era city's neo-culture, ~250 years, complete for all 35 cities via Phase 1c/2 → (3) a further-composite post-Long-Night-War orbital/Mars neo-culture, another ~200–300 years (roughly 6+ generations at a standard ~30-year generational span) — this is InnerTepeniaGDD's own Phase 3, and it's empty (`.gitkeep` only) as of last check → (4) the Mafia's own specific culture, which forms *within the story itself* over Books 1–3, out of whatever Stage 3 turns out to be. Stage 4 is never handed to us by Phase 3 — it's this series' own content to author once Stage 3 exists to build it from. Don't invent Stages 1–3 ahead of Phase 3 landing — see `reference-neo-races-and-cultures` and `feedback-no-national-stereotypes` in memory, and the "All nation-derived factions" item in `TODO.md`.
2. **No National Stereotypes.** A faction's real-world or ancestor-city origin is a locator fact, never an explanation for its culture, behavior, or conflicts. Self-test: if a sentence's meaning would change when the origin nation is swapped for a different one, rewrite it.

Until Phase 3 lands, this template is safe to use for structural/mechanical content (what a faction traffics, its technology, its role in the plot) — but the Lineage and Identity sections should stay marked TBD rather than guessed at.

## Build Checklist

1. Fill in **Lineage** first — even if Stages 1–3 are currently just "TBD, blocked on Phase 3," record the placeholder real-world nation and (if known) the candidate ancestor Tepenian city. Stage 4 (the Mafia's own culture) can be drafted once Stage 3 exists to build it from.
2. Fill in **Identity** once Lineage is settled enough to ground it honestly. Avoid stereotype-as-explanation language.
3. Fill in **What They Traffic** and **Technology Specialty** — the faction's concrete role in the DNA-computing economy.
4. Fill in **Key Events** — crossover moments with other factions/characters (check other factions' Key Events for shared events, e.g. the IoT assassination appears in multiple files).
5. Fill in **Cross-Faction Connections** and **Cultural Notes** as they emerge.
6. Fill in `48-laws.md`'s Followed and Broken lists once Identity is developed enough to support them.

## Reference Examples

- `factions/mafias/chinese/` — most complete existing example
- `factions/mafias/russian/` — first Mafia to form, also complete
- `factions/mafias/korean/` and `factions/mafias/brazilian/` — stubs, useful for seeing what "not yet developed" looks like
