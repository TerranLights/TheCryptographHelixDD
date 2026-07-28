# Solar Positioning System — 3D Celestial Navigation

*(Working title only — see Naming, below. Referred to here as "the System" or "the Solar Datum.")*

## Why This Exists

Earth-surface GPS only needs two numbers (latitude, longitude) because it's solving a 2D problem: every point of interest sits on the surface of a sphere of essentially fixed radius. Two reference points — the equator (defined by Earth's rotation) and the Greenwich meridian (an arbitrary zero-point convention) — are enough to fix a location anywhere on that 2D manifold.

Open space is not a 2D manifold. A ship, station, or shellworld can be anywhere in a genuine 3D volume, at any distance from the Sun. That means a working "space GPS" needs **three** independent numbers to fix a position, not two: two angles (to fix direction) plus a radius (to fix distance). This document specifies where those three numbers come from and how they're defined.

## Origin

**The center of the Sun.** Every measurement in the System is heliocentric — distances and angles are all reckoned from this single point, the way Earth-surface GPS reckons everything from Earth's center.

## The Reference Frame — Three Mutually Perpendicular Axes

### Axis 1 — The Polaris Line

Defined as the direction from the Sun toward Earth's north celestial pole (the point in the sky the Earth's rotational axis points at), **frozen at a specific founding epoch** rather than continuously re-measured. "Polaris" is the traditional name because, at the founding epoch, the star Polaris sat almost exactly on this line and was the obvious, unmistakable naked-eye reference for it.

This line does **not** stay pointed at the physical star Polaris forever. Earth's axis precesses — it slowly traces a cone in space over a ~26,000-year cycle (the same phenomenon responsible for the "Age of Aquarius" concept in real-world astrology, driven by lunisolar torque on Earth's equatorial bulge). Polaris only sits close to true celestial north for a historically narrow window. Within roughly a thousand years of the founding epoch, the true pole will have visibly drifted away from the star — by a matter of many degrees, not an unnoticeable amount.

**The System handles this deliberately, not by accident:** the Polaris Line itself never moves — it's a frozen mathematical direction, fixed once at the founding epoch and never redefined. What changes over time is only the *published correction offset* between "the frozen Polaris Line" and "wherever the actual pole points today" (equivalently, "how far the star Polaris itself has visibly drifted from the Line that still bears its name"). An in-universe body is responsible for periodically re-measuring and republishing that offset — see Institutional Maintenance, below. Anyone navigating with the System uses the frozen Line as the true mathematical zero-point and applies the current published correction only when they need to physically sight or aim at the actual star.

This is not a fictional contrivance — it mirrors how real-world celestial navigation already works today. Polaris is already about 0.7° off true celestial north right now, and navigators already apply a small standard correction for it. The System just extends that same practice across a much longer timescale, and formalizes the correction as a periodically-published institutional product rather than a fixed, memorized constant.

### Axis 2 — The Regulus Line

The second axis needed a bright, easy-to-identify reference roughly perpendicular to Axis 1 — i.e., roughly on the plane through the Sun that sits at a right angle to the Polaris Line (the heliocentric equivalent of "the celestial equator"). No bright naked-eye star sits *exactly* on that plane, so the star used had to be evaluated on two separate criteria simultaneously:

- **Declination** — angular distance from the celestial equator (the plane perpendicular to the Polaris Line). This measures fitness for Axis 2's *orthogonality* to Axis 1.
- **Ecliptic latitude** — a different quantity: angular distance from the ecliptic, the plane containing most of the solar system's planetary orbits. This measures how useful the resulting reference plane actually is for navigating *among the planets* — a separate concern from pure orthogonality to Axis 1.

These two planes (the celestial equator and the ecliptic) are permanently offset from each other by about 23.4° — Earth's axial tilt. No single star, and no single plane, can satisfy both criteria exactly at once. The two bright candidates that come closest to satisfying both simultaneously are Regulus (α Leonis) and Spica (α Virginis):

| Star | Apparent magnitude | Declination | Ecliptic latitude |
|---|---|---|---|
| **Regulus** (α Leonis) — *selected* | 1.35 | +11.97° | +0.46° |
| Spica (α Virginis) | 0.97 (brighter) | −11.16° | −2.06° |

**Regulus was selected** as sitting closer, in combined terms, to the ideal point (exactly 0° on both measures) than any other sufficiently bright, easy-to-find star.

Critically, Regulus's actual direction is **not** used directly as Axis 2 — it is off Axis 1's exact perpendicular plane by about 12° (its declination). The true Axis 2 direction is obtained by mathematically **projecting** the frozen-epoch direction to Regulus onto the plane exactly perpendicular to Axis 1 — i.e., subtracting off the component of Regulus's direction that runs along Axis 1, then normalizing what remains. This projected, idealized direction — not the star's literal position — is the true, exact Axis 2. Like Axis 1, it is frozen at the founding epoch, and a separately-published correction offset tracks how far the actual star Regulus has since drifted from "the Regulus Line" that bears its name (Regulus has its own proper motion on top of the shared precession drift, so this offset accumulates independently from Axis 1's).

### Axis 3 — Derived, Not Chosen

Axis 3 is not an independent decision. Once Axis 1 and Axis 2 are fixed and exactly perpendicular to each other, Axis 3 is fully and automatically determined: it is their cross product, which is guaranteed to be exactly 90° from both. There is no third star, no third sighting, and no third correction offset to maintain — Axis 3 is a pure mathematical consequence of the first two choices, not a fourth data point.

## A Known, Deliberate Trade-off

Because Axis 1 is defined as the true Polaris direction (Earth's rotational axis) rather than the ecliptic pole, the resulting fundamental plane (the plane containing Axis 2 and Axis 3, perpendicular to Axis 1) is the **celestial equatorial plane, not the ecliptic**. It sits roughly 23.4° off the plane most of the solar system's planets actually orbit in. This was chosen deliberately — Polaris and Regulus are both recognizable, bright, easy-to-sight references, and Regulus in particular happens to be a very close practical compromise (0.46° off the ecliptic) despite the System's fundamental plane not being the ecliptic itself. A system built around the true ecliptic pole would be marginally more "convenient" for pure planetary navigation, but the ecliptic pole (in the constellation Draco) has no comparably bright naked-eye star sitting on it — so it fails the "easy to find" requirement that motivated this whole design in the first place.

## Institutional Maintenance

Both Axis 1 and Axis 2 require a periodically-republished correction offset, since precession (and, for Regulus, ordinary proper motion) continuously drags the real stars away from the frozen mathematical Lines that bear their names. This is exactly analogous to how modern hydrographic/geodetic offices already publish periodically-updated datums and corrections in the real world. Some in-universe body — an Astrometric Bureau, a Navigational Almanac Office, or similar (name TBD, see Open Decisions) — would be the canonical authority responsible for:

- Maintaining the precise frozen-epoch definitions of Axis 1 and Axis 2 as immutable mathematical constants
- Periodically re-measuring the actual current positions of Polaris and Regulus
- Publishing updated correction offsets (angle and bearing) between each frozen Line and its namesake star's current true position
- Almost certainly publishing these on some regular cadence (an "Almanac," updated annually, per-decade, or per some other in-universe unit)

This is a rich, mostly-untapped seed for in-universe texture: outdated charts using a stale correction table, a smuggler's route thrown off by using an old Almanac, a plot beat that hinges on the difference between "official" and "actual" bearings, a historical dispute over when the founding epoch was actually set, etc.

## Expressing a Position

A full position in the System requires three numbers — this is the fundamental way it differs from 2D Earth-surface GPS, which gets away with two:

1. **Radial distance** — distance from the Sun's center, in whatever distance unit the setting uses (AU is the natural real-world default; a setting-specific unit could be introduced instead).
2. **An angle within the fundamental plane** — analogous to longitude, measured from the Regulus Line (Axis 2) around toward Axis 3. (Working term: "Solar Longitude." Alternative naming TBD.)
3. **An angle out of the fundamental plane** — analogous to latitude, measured from the fundamental plane toward the Polaris Line (Axis 1) or away from it. (Working term: "Solar Latitude." Alternative naming TBD.)

This is, structurally, an ordinary spherical coordinate system (r, θ, φ) centered on the Sun — the same basic shape as the equatorial coordinate system real astronomers already use for the whole sky (Right Ascension, Declination, distance), just re-centered from Earth to the Sun and built from a deliberately-chosen pair of bright reference stars instead of the abstract vernal equinox point real astronomy uses.

## Real-World Grounding

This whole design is not a fictional invention bolted onto real physics — it's a close parallel to how real astrometry already solved the identical problem:

- **Equatorial coordinates (RA/Dec)** are exactly this method, centered on Earth instead of the Sun, using Earth's rotational axis as the polar axis and the vernal equinox as the zero-longitude reference.
- **The ICRS/ICRF** (International Celestial Reference System/Frame, adopted 1998) replaced the older star- and equinox-based reference frames for precisely the reason this document accounts for: stars and equinoxes drift due to precession and proper motion, so real modern astrometry now fixes its reference frame using extremely distant quasars that show no measurable drift at all, then relates everyday star positions back to that frozen frame via well-understood correction models.
- **Real celestial navigators today** already use Polaris with a small, known correction rather than treating it as sitting exactly at the pole.

The System recreates all three of these real techniques faithfully: a frozen mathematical reference frame (like the ICRS), a periodically-updated correction table for practical use (like real navigational almanacs), and named, recognizable stars as user-facing sighting aids (like real-world Polaris navigation) — rather than inventing a new, physically implausible mechanism.

## Glossary

- **Declination** — angular distance of an object north/south of the *celestial equator* (the plane perpendicular to Earth's/the System's rotational-pole axis). Not the same as ecliptic latitude.
- **Ecliptic latitude** — angular distance of an object north/south of the *ecliptic* (the plane containing most planetary orbits). Not the same as declination.
- **Precession** — the ~26,000-year cyclical drift of Earth's rotational axis direction, caused by lunisolar gravitational torque on Earth's equatorial bulge. The root cause of both Polaris's and the equinoxes' long-term drift.
- **Proper motion** — a star's own actual motion through space relative to the Sun, independent of precession. Affects Regulus's drift on top of the shared precessional drift.
- **Frozen epoch** — a specific fixed moment in time at which a reference direction is mathematically defined once and never re-derived, as distinct from a "live" reference that continuously tracks a moving object.

## Open Decisions (TBD)

- **Founding epoch** — what specific year the System's frozen reference directions were actually fixed at. A plausible in-universe window would be sometime during the Second Interwar Period (2564–~2812), once off-world infrastructure (Phobos/Deimos, early Mars colonization) became substantial enough to need solar-system-wide navigation — but this is a suggestion, not a decision. See `series-overview/universe-timeline.md`.
- **System name** — "Solar Positioning System" / "the Solar Datum" are placeholder working titles used in this document, not settled canon.
- **Coordinate term names** — "Solar Longitude" / "Solar Latitude" are placeholders; something more setting-flavored may fit better.
- **Maintaining institution's name** — "Astrometric Bureau" / "Navigational Almanac Office" are placeholder suggestions for whichever body publishes the correction tables.
- **Distance unit** — whether the setting uses AU, a custom in-universe unit, or something else for the radial coordinate.

## Cross-References

- `series-overview/universe-timeline.md` — for founding-epoch candidate dating against the Second Interwar Period
- `world/technology.md` — for other setting technology this coordinate system would interoperate with
- `world/locations.md` — for the solar-system geography this system is meant to navigate
