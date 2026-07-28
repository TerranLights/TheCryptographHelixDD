# Solar Positioning System — 3D Celestial Navigation

*(Working title only — see Open Decisions, below. Referred to here as "the System.")*

**This is the foundational geometric system underlying all directionality, positioning, and heading in The Cryptograph Helix.** Any time the series needs to describe where something is, which way something is pointing, or how two locations relate to each other in three-dimensional space, it is expressed in terms of this reference frame.

## Why This Exists

Earth-surface GPS only needs two numbers (latitude, longitude) because it's solving a 2D problem: every point of interest sits on the surface of a sphere of essentially fixed radius. Two reference facts — the equator (defined by Earth's rotation) and the Greenwich meridian (an arbitrary zero-point convention) — are enough to fix a location anywhere on that 2D manifold.

Open space is not a 2D manifold. A ship, station, or shellworld can be anywhere in a genuine 3D volume, at any distance from the Sun. A working "space GPS" needs **three** independent numbers to fix a position, not two: two angles (to fix direction) plus a radius (to fix distance). This document specifies where those three numbers come from and how they're defined.

## Origin

**The center of the Sun.** Every measurement in the System is heliocentric — distances and angles are all reckoned from this single point, the way Earth-surface GPS reckons everything from Earth's center.

## The System Is Built From Three Planes

Rather than picking three axis-lines directly, the System is most cleanly understood as three mutually perpendicular *planes*, each passing through the Sun's center. Each axis is simply the line perpendicular to one of these planes — so the planes and the axes are two descriptions of exactly the same geometry; either can be used to derive the other.

### Plane 1 — The Invariable Plane

The fundamental reference plane. The Invariable Plane is the true, physically-grounded "average" orbital plane of the entire solar system — the plane perpendicular to the solar system's total angular momentum vector, weighted by every planet's actual mass and motion (dominated in practice by Jupiter and Saturn, the two largest contributors of angular momentum). It sits only about 1.6° from the more commonly cited ecliptic (Earth's own orbital plane specifically), but is the more physically correct choice for a plane meant to represent "where the planets orbit" as a whole, rather than just where Earth happens to orbit.

This plane satisfies the original design requirement directly: a fundamental reference plane that actually aligns with the solar system's own geometry, cutting through the majority of the planets' orbital planes.

**Axis 1**, the line perpendicular to the Invariable Plane, is called **the Polaris Line** — a name that is, deliberately and permanently, disconnected from its literal meaning. See below.

### Plane 2 — The Regulus Meridian

Constructed as: the plane that contains Axis 1 (the Polaris Line), rotated around that line until it also contains — as closely as mathematically possible — the actual direction from the Sun to the star Regulus (α Leonis).

Because *any* plane containing Axis 1 is automatically perpendicular to Plane 1 (this is just what it means for a line to be a plane's normal — every plane through that line is perpendicular to the plane it's normal to), Plane 2 is guaranteed to intersect the Invariable Plane at an exact 90° angle, with no additional adjustment required to enforce that.

The line where Plane 2 meets Plane 1 is **Axis 2**, called **the Regulus Line** — the "0°" reference direction within the Invariable Plane, the heliocentric equivalent of the Greenwich meridian.

**Why Regulus:** the correct criterion for this choice is minimizing **ecliptic latitude** (angular distance from the Invariable Plane/ecliptic) — not declination, which would be the relevant criterion only if Axis 1 pointed at the literal celestial pole rather than the Invariable Plane's normal. Regulus's ecliptic latitude is only about +0.46°, the closest of any sufficiently bright, easily identifiable naked-eye star:

| Star | Apparent magnitude | Ecliptic latitude |
|---|---|---|
| **Regulus** (α Leonis) — *selected* | 1.35 | +0.46° |
| Spica (α Virginis) | 0.97 (brighter) | −2.06° |
| Aldebaran (α Tauri) | 0.86 (brighter) | −5.5° |
| Antares (α Scorpii) | 1.09 | +4.5° |

Because Regulus already sits so close to the Invariable Plane, the correction needed to obtain the true Axis 2 direction is tiny — Regulus's real position is nudged by less than half a degree to land exactly on the plane. This is a dramatically smaller correction than an equivalent construction anchored to the celestial equator would have required (which would have needed a ~12° correction — see Design History, below, for why that approach was rejected).

### Plane 3 — The Third Plane

The remaining coordinate plane, perpendicular to both Plane 1 and Plane 2. This perpendicularity is automatic — it is a structural property of any three mutually-perpendicular reference planes, not something separately imposed or measured. Its normal is **Axis 3**, lying within the Invariable Plane at exactly 90° from the Regulus Line. Axis 3 is not an independent choice: it falls out of Axis 1 and Axis 2 as their cross product, with no third star, no third sighting, and no third correction offset ever required.

## The Polaris Line: A Deliberately Disconnected Name

Axis 1 is named "the Polaris Line" for historical/traditional reasons, **not because it points toward the star Polaris.** It doesn't. The Polaris Line is the normal to the Invariable Plane — a direction determined entirely by the solar system's mass distribution — while the real star Polaris marks the direction of Earth's rotational axis, a physically unrelated quantity. The two directions are separated by roughly 23.4° (the same angle as Earth's axial tilt) — a large, obvious, and permanent gap, not a small rounding error that grows with time.

This is not an approximation that drifts into inaccuracy — it is disconnected from the star by design, from the moment the System was defined. Whether an in-universe historical explanation exists for why the name persisted anyway (e.g., an earlier, literal Polaris-based system later superseded by this one, with the traditional name surviving the redefinition) is an open question — see Open Decisions.

One practical consequence: unlike Regulus, there is no bright naked-eye star sitting at or near the Invariable Plane's pole to serve as a direct visual reference for Axis 1. The direction has to be established through instrumentation — star trackers, gyroscopic platforms, or triangulation against multiple known stars — rather than by a single naked-eye sighting the way historical Polaris navigation worked. Given the setting's existing technology (DNA computing, brain-encryption systems, shellworld engineering), this is a trivial capability for any spacefaring faction in the story, not a plausibility gap.

## Design History: Why Not the Celestial Pole

An earlier version of this design used Earth's actual rotational axis (the literal Polaris direction) for Axis 1 instead of the Invariable Plane's normal. That approach was rejected for two compounding reasons, both worth recording since they explain why the current design looks the way it does:

1. **Misalignment with the planets.** A plane perpendicular to Earth's rotational axis is the celestial equatorial plane, not the Invariable Plane — the two are offset by the same ~23.4° obliquity, meaning the fundamental reference plane would have sat at a steep, unhelpful angle to where the planets actually orbit.
2. **Poor long-term stability.** Earth's rotational axis precesses through a full circle roughly every 26,000 years, drifting on the order of 13–15° per millennium. The Invariable Plane, by contrast, only shifts due to much weaker, slower gravitational perturbations between the planets — on the order of a fraction of a degree per millennium, roughly an order of magnitude more stable. Anchoring the System to Earth's rotational axis would have required substantial, visibly-growing corrections within the story's own timescale; anchoring it to the Invariable Plane keeps those corrections small and slow-growing throughout.

The current design keeps the traditional name "the Polaris Line" (see above) as the one surviving artifact of that earlier approach, while using the astronomically superior Invariable-Plane definition underneath it.

## Institutional Maintenance

Both Axis 1 and Axis 2 still require periodically-republished correction offsets — nothing in a real, multi-body solar system is ever perfectly fixed forever. The Invariable Plane itself drifts slowly due to planetary perturbations, and Regulus has its own proper motion (independent of any precession-like effect) carrying it slowly away from the frozen Regulus Line. Both effects are far smaller and slower than the celestial-pole-based design would have produced, but they are not literally zero.

**The Tepenian Astrometric & Navigational Authority (TANA)** is the canonical in-universe body responsible for:

- Maintaining the precise frozen-epoch definitions of Axis 1 and Axis 2 as immutable mathematical constants
- Periodically re-measuring the actual current positions of the Invariable Plane's pole and the star Regulus
- Publishing updated correction offsets (angle and bearing) between each frozen Line/Plane and its current true position
- Doing so on some regular in-universe cadence (an "Almanac," updated per-decade, per-generation, or on whatever cycle fits)

This is a rich, mostly-untapped seed for in-universe texture: outdated charts using a stale correction table, a smuggler's route thrown off by an old Almanac, a plot beat hinging on the gap between "official" and "actual" bearings, a historical dispute over exactly when the founding epoch was set, etc.

## Expressing a Position

A full position in the System requires three numbers — the fundamental way it differs from 2D Earth-surface GPS, which only needs two:

1. **Radial distance** — distance from the Sun's center, in whatever distance unit the setting uses (AU is the natural real-world default; a setting-specific unit could be introduced instead — see Open Decisions).
2. **An angle within the Invariable Plane** — analogous to longitude, measured from the Regulus Line around toward the Third Plane's axis. (Working term: "Solar Longitude.")
3. **An angle out of the Invariable Plane** — analogous to latitude, measured from the Invariable Plane toward the Polaris Line (or away from it). (Working term: "Solar Latitude.")

Structurally, this is an ordinary spherical coordinate system (r, θ, φ) centered on the Sun — the same basic shape as the equatorial coordinate system real astronomers already use for the whole sky (Right Ascension, Declination, distance), just re-centered from Earth to the Sun, re-founded on the Invariable Plane instead of Earth's equator, and anchored to a deliberately-chosen bright reference star instead of the abstract vernal equinox point real astronomy uses.

## Real-World Grounding

This design is not a fictional invention bolted onto real physics — it closely parallels how real astrometry solved the identical problem:

- **Equatorial coordinates (RA/Dec)** use exactly this method, centered on Earth, with Earth's rotational axis as the polar axis and the vernal equinox as the zero-longitude reference.
- **The Invariable Plane** is a real, established astronomical concept — genuinely the more physically meaningful "solar system plane" compared to the ecliptic, precisely because it accounts for every planet's contribution rather than just Earth's.
- **The ICRS/ICRF** (International Celestial Reference System/Frame, adopted 1998) replaced the older star- and equinox-based reference frames for exactly the reason this document accounts for: stars and equinoxes drift due to precession and proper motion, so modern astrometry now fixes its reference frame using extremely distant quasars that show no measurable drift, then relates everyday star positions back to that frozen frame via well-understood correction models.
- **Real celestial navigators today** already use Polaris with a small, known correction rather than treating it as sitting exactly at the pole — the same practice this System formalizes and extends across a much longer timescale.

## Glossary

- **Invariable Plane** — the true, mass-weighted average orbital plane of the entire solar system (dominated by Jupiter and Saturn), distinct from but very close (~1.6°) to the ecliptic (Earth's own orbital plane specifically).
- **Ecliptic** — the plane of Earth's own orbit around the Sun. Commonly used as a stand-in for "the solar system's plane," though the Invariable Plane is the more precise choice.
- **Declination** — angular distance of an object north/south of the *celestial equator* (the plane perpendicular to Earth's rotational axis). Not the same as ecliptic latitude, and not the relevant measure for this System, since Axis 1 is not the celestial pole.
- **Ecliptic latitude** — angular distance of an object north/south of the *ecliptic*/Invariable Plane. This is the relevant measure for evaluating candidate stars for Axis 2.
- **Precession** — the ~26,000-year cyclical drift of Earth's rotational axis direction, caused by lunisolar gravitational torque on Earth's equatorial bulge. Responsible for Polaris's long-term drift from true celestial north — a phenomenon this System deliberately avoids depending on, by not anchoring Axis 1 to the celestial pole in the first place.
- **Proper motion** — a star's own actual motion through space relative to the Sun, independent of precession. The reason Regulus's position still requires a periodically-updated correction, even though the Invariable Plane itself is comparatively stable.
- **Frozen epoch** — a specific fixed moment in time at which a reference direction is mathematically defined once and never re-derived, as distinct from a "live" reference that continuously tracks a moving object.

## Open Decisions (TBD)

- **Founding epoch** — what specific year the System's frozen reference directions were actually fixed at. A plausible in-universe window would be sometime during the Second Interwar Period (2564–~2812), once off-world infrastructure (Phobos/Deimos, early Mars colonization) became substantial enough to need solar-system-wide navigation — but this is a suggestion, not a decision. See `series-overview/universe-timeline.md`.
- **Whether "the Polaris Line" has an in-universe origin story** — e.g., an earlier, literal Polaris-anchored system later superseded by the current Invariable-Plane design, with the traditional name surviving the change — versus the name simply being an unexplained traditional convention with no in-story history attached. Not yet decided.
- **System name** — "Solar Positioning System" is a placeholder working title used throughout this document, not settled canon.
- **Coordinate term names** — "Solar Longitude" / "Solar Latitude" are placeholders; something more setting-flavored may fit better.
- **Distance unit** — whether the setting uses AU, a custom in-universe unit, or something else for the radial coordinate.

## Cross-References

- `series-overview/universe-timeline.md` — for founding-epoch candidate dating against the Second Interwar Period
- `world/technology.md` — for other setting technology this coordinate system would interoperate with
- `world/locations.md` — for the solar-system geography this system is meant to navigate
