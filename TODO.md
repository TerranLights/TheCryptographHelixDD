# The Cryptograph Helix — To-Do List

A running reference of outstanding design work, organized by urgency. Update as items are completed or reprioritized.

---

## Decision Required *(blocking other work)*

These require a deliberate call before downstream work can proceed. None can be resolved through research or writing alone.

- [ ] **Earthtech — final name**
  Current working name "Earthtech" is a placeholder. 14 candidates documented in `reference/future-ideas.md`. Blocks: all content referencing this faction by name, Howie's full character file, any real-world analogy notes.

- [ ] **Colombian e-thot — character name**
  Current file uses "Colombian e-thot" as a descriptor, not a name. Candidates exist in `factions/e-thots/colombian/overview.md` (Zarita, Celestina, Veronica, etc.). Blocks: all narrative beat work, the parallel-plot file, any character-level 48-laws entries that reference her by name.

- [ ] **"Framejacking" — term ownership check**
  Currently understood to be Dennis E. Taylor's term. If confirmed, needs renaming before the series is public-facing. Blocks: `world/technology.md`, Russian Mafia overview, series pitch materials.

- [ ] **Solar Positioning System — naming, founding epoch, and Polaris Line origin story**
  `world/navigation.md` specifies the full 3D heliocentric coordinate system (Invariable Plane, Regulus Meridian/Regulus Line, derived Third Plane/Axis 3) — this is the foundational system for **all** directionality in the series, per the user (see `project-solar-positioning-system` in memory). The maintaining institution is now named — **the Tepenian Astrometric & Navigational Authority (TANA)**. Still placeholders: the system's own name, the two coordinate terms ("Solar Longitude"/"Solar Latitude"), the distance unit used for the radial coordinate, and the founding epoch year the reference frame was originally fixed at (candidate window: sometime in the Second Interwar Period, 2564–~2812). Also undecided: whether "the Polaris Line" (a name deliberately disconnected from the actual star Polaris, which sits ~23.4° away) has an in-universe origin story — e.g. an earlier literal-Polaris system later superseded — or is just an unexplained traditional name. None of these block using the system conceptually, but should be settled before it appears on the page.

- [ ] **"Nearly 900 years" line — reconcile with fluid opening date**
  `series-overview/themes-and-structure.md`'s Philosophical Architecture section says robot personhood was settled "nearly 900 years before the story opens" (measuring from Jeju-do, 2318, or the Falkland Treaty, 2564). That figure only holds if Cryptograph Helix opens ~3200s; the series' actual opening date is officially fluid at ~3000s–3100s, where the true gap is roughly 600–800 years. Flagged 2026-07-11 — left as-is intentionally pending the opening-date decision. Revisit once the opening year firms up (either adjust the prose or let it justify locking to ~3200s).

- [ ] **All nation-derived factions — blocked on InnerTepeniaGDD Phase 3 (cross-mingled "neo-neo-race" model, confirmed 2026-07-27)**
  InnerTepeniaGDD's new "Neo-Races and Neo-Cultures" project (see `reference-neo-races-and-cultures` in memory) synthesizes each Tepenian city's own new composite people, **named for the city itself** (Zhongshanese, Shirayukese, Sinheungese, Rotheran, Marambian, Belgranian, Sanaian, etc.) — never for whichever real-world nation happened to be demographically largest there. A city's national demographic breakdown is raw *input* to that synthesis, never the naming or identity itself. Two earlier framings of this problem (a "two-generation" model, then a "which nation is Primary where" search treating Russia/Brazil's lack of a dominant city as a problem) were both wrong and retracted — both were still nation-centric thinking, which the whole neo-race framework exists to move past.

  **The confirmed model:** (1) real-world nations, pre-2564 — historical input only → (2) Tepenian exile-era city neo-races, ~250 years to 2812, named per-city (Phase 1c cataloging complete for all 35 cities; Phase 2 naming/synthesis mostly not done) → (3) off-world diaspora, ~5–8 generations from the Long Night War (2812) to roughly Book 3's era — these city-neo-races don't stay put as discrete communities; they subdivide and **cross-mingle with each other** across orbital infrastructure and Mars cities → (4) **"neo-neo-races"** — new, second-order composite peoples from that cross-mingling, not reducible to any single Antarctic ancestor city — this is the level the Mafias are actually built from → (5) the Mafia's own specific culture, which per `plot/parallel-plots/mafia.md` doesn't exist when Book 1 opens and instead coalesces within the story itself over Books 1–3.

  This means the real task isn't "trace each Mafia to one city and rename it [City]ese" — it's modeling which specific combination of city-populations plausibly cross-mingled together in a given orbital/Martian setting, and synthesizing what new neo-neo-race that blend produces. That's genuinely new creative work, likely beyond what InnerTepeniaGDD's Phase 3 will hand us ready-made even once it exists (Phase 3 isn't scoped yet, and sounds oriented toward the orbital population generally, not toward modeling specific cross-city blends). A build template exists at `factions/mafias/z-template/` but its current "Lineage" section still describes the retracted single-city model and needs updating to match. User's call: **wait for InnerTepeniaGDD's Phase 3 to actually be developed** before reworking any of this, not to do it independently now. Phase 3 was empty (`.gitkeep` only) as of last check.

  Also confirmed along the way (still factually useful, kept in memory): Zhongshan is the *only* Tepenian city where the founding nation (China) stayed demographically Primary throughout, unbroken — everywhere else shows demographic displacement from the founding nation. "Soyuz" (previously on record as a Russian city destroyed in the Long Night War) is confirmed defunct/untraced in current canon — don't use that name without re-verifying first. A local clone of InnerTepeniaGDD exists at `/home/kuroskalacs/Documents/Doll-Fi/media/games/Inner Tepenia/InnerTepeniaGDD/` — check that on disk before making web calls.

---

## High Priority

- [ ] **Audit E-thots-by-nationality structure against the "No National Stereotypes" rule**
  The parent Tepenian Universe Timeline repo established a binding rule (`Reference/No_National_Stereotypes.md`): a faction/place's real-world national origin is a locator detail only, never an explanation for its culture, conflict, or behavior. Confirmed 2026-07-12 that this applies to Cryptograph Helix, not just Inner Tepenia. The Mafia factions and the Resistance have their own, deeper version of this issue tracked separately above under Decision Required (cross-mingled multi-city "neo-neo-race" lineage, blocked on InnerTepeniaGDD Phase 3) — this item is scoped to the E-thots-by-nationality structure specifically, which needs its own review pass for places where national stereotype is used as explanatory logic. See `feedback-no-national-stereotypes` in memory.

- [ ] **Books 2–6 — beat sheets**
  All seven books have `overview.md` + `volume-1/` + `volume-2/` folders, but Books 2–6 are stubs (see `dev-road-map/01-completion-matrix.md` for per-volume status). Each volume needs its beat sheet filled in (Inciting Incident, Act 1–3 beats, Mirror Moment, All Is Lost, climax). Start with Book 2's Volume 1 (`books/book-02-the-autonomy-allele/volume-1/structure/main story/Save the Cat.md`) to unblock the monomyth's second iteration.

- [ ] **Monomyth — iterations 2–7**
  `plot/monomyth.md` has structure for all 7 iterations but only iteration 1 has any substantive content. Complete the KWML archetype + all 8 Harmon steps for each remaining iteration. Depends on beat sheets above for Books 2–6.

- [ ] **Brazilian Mafia — full development**
  `factions/mafias/brazilian/overview.md` is a stub. Needs: origin story, philosophy, how they encode data, what role they play per book, 48-laws mapping. Look at Chinese and Russian files as templates.

- [ ] **Korean Mafia — full development**
  `factions/mafias/korean/overview.md` is a stub. Needs: origin story, philosophy, specialty, role per book, 48-laws mapping. The Jeju-do legacy (robot personhood ruling from Unified Korea, 2318) is the cultural seed — a criminal organization descended from the civilization that formalized rights is a rich contradiction to develop.

- [ ] **Resistance — 48-laws**
  `factions/resistance/48-laws.md` is empty. The faction overview exists; the 48-laws analysis needs writing.

- [ ] **Earthtech — 48-laws**
  `factions/earthtech/48-laws.md` is empty. Howie's character file and the faction overview exist as source material.

- [ ] **Memes — 48-laws (broken list)**
  `factions/memes/48-laws.md` has the followed list but the broken list is TBD. Complete it.

---

## Medium Priority — Characters

- [ ] **László — books 2–3 arc design**
  He first appears at 2.10. His personal Harmon cycle doesn't begin until 4.1. His role in Books 2 and 3 needs to be established: what does he observe, how does he avoid involvement, what breaks his detachment? See `characters/laszlo.md` and `plot/parallel-plots/laszlo.md`.

- [ ] **Colombian e-thot — voice and personality**
  The 3-act arc and 48-laws are complete. What's missing: her actual voice, mannerisms, contradictions, the specific way she seduces, and how her arc in Act 3 (turning toward the Resistance) manifests emotionally. Blocked partly by the name decision above.

- [ ] **E-thots — remaining archetypes**
  `factions/e-thots/overview.md` lists all 8 seduction archetypes with nationalities. Only the Colombian (Siren) is developed. At minimum, the archetypes that appear in Books 1–4 need individual character files.

- [ ] **Howie — full character development**
  `factions/earthtech/howie.md` has origins and methods but needs: KWML archetype placement, 48-laws mapping, dialogue voice, and how his defeat (if any) connects to Book 7's resolution.

---

## Medium Priority — World and Story

- [ ] **Society files — all 6 ethnic groups**
  All files in `societies/` are placeholders with structure only. Each needs substantive content: cultural characteristics, how they survived into the ~3000s era, what role they play in the story, any relevant customs or beliefs. Priority order: Hungarians (Resistance), Finns (co-survivor culture), Chinese, Colombians, Greeks, Germans.

- [ ] **Earth-era nations — develop from Tepenian demographics**
  The standalone-universe names (Suwedistan, al-Manya, The Caliphate) have been removed. What Germany, the UK, Sweden, and other European nations look like in the ~3000s needs to be worked out from the Tepenian universe's demographic logic. Germans are significant (leading European census group in Tepenia); UK and Sweden's Tepenian-era fates are TBD. See `world/society.md`.

- [ ] **World — missing locations**
  `world/locations.md` covers major sites but smaller or incidental locations need filling in as the beat sheets develop: specific Venus gulag details, the Belt colony where X happens, named Jovian shellworld districts.

- [ ] **Reference ebooks — read and synthesize**
  A library of reference PDFs/EPubs is in `reference/ebooks/` (local only, gitignored). Begin reading and distilling composite ideas into `philosophy/insights.md`, `philosophy/possibilities.md`, and any new philosophy or world files as needed. No format required — extract only what is genuinely useful.

- [ ] **"Framejacking" — mechanism detail**
  `philosophy/possibilities.md` has a brief note. Needs: how it feels subjectively, what the physical drug delivery looks like, withdrawal profile, how the Russian Mafia weaponized the schematics, and how Earthtech tried to suppress it. Blocked pending name resolution.

- [ ] **Missing drive — beat files**
  An external drive was referenced as possibly containing additional beat sheet notes. Reconnect and search when available.

---

## Long-Term / Low Urgency

- [ ] **Series title — final decision**
  Candidates are in `series-overview/title-candidates.md`. No decision needed until closer to querying/publishing. Keep the list updated as new candidates emerge.

- [ ] **Per-book titles — final decisions**
  Same folder. Current preferred choices are marked ✓ but none are locked.

- [ ] **Unsorted notes — review and redistribute**
  `reference/unsorted-notes.md` contains raw notes not yet placed into proper sections. Items like "time-cable reality," the metal band crisis, and the Anicetus arc need eventual homes. Process when a relevant section is being actively developed.

- [ ] **Stale Navigational Almanac plot beat — mechanism/character resolved 2026-08-10, book placement still open (Book 6 or Book 7)**
  Mechanism unchanged from the original idea (a stale correction-offset
  Almanac creating a gap between "official" and "actual" bearings — see
  `world/navigation.md`'s Institutional Maintenance section), now given a
  specific trigger and a delivering character: a minor new character — a
  TANA Space Traffic Controller, see `characters/tana_controller.md` — who
  notices a lone ship's bearing doesn't match the official charts, remarks
  "Oh, that's odd. Just one ship," and moves on. **Cross-project tie-in:**
  that ship belongs to *The Not-Departure series* (a separate Doll-Fi
  audio-drama project, not a CH subplot), set concurrently with whichever
  book this lands in — Doc's ship, en route to Saturn, shortly to be
  destroyed in "dead space." **Book 6 vs. Book 7 — not yet decided.** Book
  6 has a specific advantage worth weighing (open Mafia/Earthtech warfare,
  Earthtech still fully active pre-Book-7-annihilation, matching what
  Not-Departure's own antagonist needs), but this is a consideration, not a
  decision — both remain live candidates, same as the original entry. See
  that project's `Tepenian_Reinterpretation.md` §1 and
  `structure/Dev-Road-Map/02-Blocking-Decisions.md` for the other side of
  this connection. Exact chapter placement, once the book is chosen, still
  TBD either way.

- [ ] **Outer Tepenia 1 — GDD start**
  The Jovian Metasystem civilization that emerges at the end of Book 7 is the founding era of Outer Tepenia 1. Start a separate GDD repo when Cryptograph Helix's Book 7 ending is sufficiently developed to seed it. See `reference/continuity-guidelines.md`.

- [ ] **Outer Tepenia 2 and New Centauri — GDD starts**
  Further out. Begin only after Outer Tepenia 1 is underway.

- [ ] **Trace the Fused Beat Structure bridge in the knowledge graph**
  `/graphify` built a full knowledge graph of this repo (`graphify-out/graph.json`, 2026-08-24). The highest-betweenness bridge node is "Fused Snyder/Bell/Truby/Campbell Beat Structure" (`reference/story-structure-definitions.md`), connecting the Books 1-2 community to the World & Continuity community. Worth tracing with `graphify query` to see whether that's a meaningful structural link or just an artifact of every Craft Reference file pointing back to the same shared definition.

---

## Completed

- [x] Full repo restructure — all notes migrated from x-to-be-organized-then-discarded/ and external Dolls drive into clean Markdown hierarchy
- [x] Series premise documented — `series-overview/premise.md`
- [x] KWML, Harmon Circle, 3-act, and monomyth frameworks — `series-overview/themes-and-structure.md`
- [x] Universe timeline — `series-overview/universe-timeline.md` (Inner Tepenia → Cryptograph Helix → Outer Tepenia 1 & 2 → New Centauri)
- [x] Title candidates — `series-overview/title-candidates.md`
- [x] Faction motivations table (Want/Need/Idea) — `series-overview/faction-motivations.md`
- [x] World: technology, locations, society, outer-tepenia files created
- [x] All 6 society files created (placeholders; hindus.md removed per decision)
- [x] Chinese Mafia — full overview and 48-laws
- [x] Russian Mafia — full overview and 48-laws
- [x] Brazilian and Serbian Mafia — stub files created
- [x] Earthtech — overview, Howie file, 48-laws placeholder
- [x] E-thots — overview (all 8 archetypes), Colombian overview and 48-laws
- [x] Resistance — overview created
- [x] Memes — overview and partial 48-laws
- [x] All 4 parallel-plot Harmon arcs (Mafia, Meme Nation, Colombian E-Thot, László)
- [x] László character sheet — `characters/laszlo.md` (full 48-laws, Want/Need/Idea, Harmon circle)
- [x] All 7 book files created — `books/01` through `books/07`
- [x] Series map — `plot/series-map.md`
- [x] Monomyth file created — `plot/monomyth.md` (iteration 1 substantive; 2–7 structured stubs)
- [x] Philosophy files — insights.md, possibilities.md, 48-laws-reference.md
- [x] Reference files — future-ideas.md (14 Earthtech name candidates), unsorted-notes.md, continuity-guidelines.md
- [x] eBooks gitignore — `reference/ebooks/` excluded from GitHub
- [x] Indian faction and society removed entirely from repo
- [x] Serbian Mafia replaced with Korean Mafia — demographically grounded in Tepenian census; Jeju-do legacy as cultural seed
- [x] Standalone-universe nation names removed (Suwedistan, al-Manya, The Caliphate) — flagged for replacement based on Tepenian demographic logic
- [x] American English confirmed as repo standard
