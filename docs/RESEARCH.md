# Research & Engineering Portfolio

**Liran M. Schwartz** · Independent Researcher · Haifa, Israel  
`scliran9@gmail.com` · [ORCID 0009-0008-8035-1308](https://orcid.org/0009-0008-8035-1308) · [@LiranOG](https://github.com/LiranOG)

---

## How to read this document

This is a technical inventory of the research and engineering work I have built, alone, as an independent researcher with no institutional affiliation. Every project is described with the level of precision that a domain expert would expect — including the parts that don't work yet, the benchmarks that haven't run, and the gaps between what the code does and what it eventually should do.

I do not claim institutional credentials I don't have, and I don't soften statuses I haven't earned. If you find anything in this document that overstates the work, treat it as a bug and report it.

This document covers the **engineering and applied physics** side of my portfolio. For the speculative theoretical frameworks that motivate some of this work — and that I keep deliberately separated from the engineering — see [THEORIES.md](./THEORIES.md). For the broader context behind why I do any of this, see [VISION.md](./VISION.md). To contribute, see [COLLABORATE.md](./COLLABORATE.md).

---

## Universal disclaimers — applies to everything below

Before any project-specific notes, the following limitations apply to **every project** in this document, by virtue of how the work was produced. They are not optional caveats; they are structural facts.

- **No institutional affiliation.** I work without university backing, without a peer group on the inside of any of these domains, and without research advisors. Nothing here has been vetted by an academic committee.
- **No external code review.** Every line of physics code in these repositories was written by me, read by me, and tested by me. The unit test suites are extensive, but a single developer's tests reflect a single developer's blind spots.
- **No funding.** All compute is desktop-class (i5-8400 / i5-12600KF, 16–32 GB RAM, WSL2). No cluster, no GPU compute beyond CPU testing, no cloud budget. This places hard ceilings on what can be benchmarked at production resolution.
- **No formal training in numerical relativity.** My knowledge of CCZ4, GRMHD, post-Newtonian expansions, IB theory, and the rest is self-taught from textbooks, papers, and direct work. This is sufficient to build, but it is not sufficient to guarantee I have not made conceptual errors that a trained NR specialist would catch immediately.
- **Single-perspective bias.** Every architectural decision, every physics formulation choice, every initialization strategy reflects the judgment of one person. Where I have been wrong in the past, the documentation says so. Where I am wrong now and don't know it, the documentation cannot help.
- **Active hiatus (May–August 2026).** Response times during this window are slower than during active development. Issues remain open; nothing is abandoned.

These are the constraints. The work below was produced inside them, and every project's limitations should be read against this background.

---

## Table of Contents

1. [GRANITE-Astrophysics-Suite — Theoretical & Kinematic Archive](#1-granite-astrophysics-suite)
2. [GRANITE-NR — Numerical Relativity Engine](#2-granite-nr)
3. [VORTEX — Relativistic N-Body Simulator](#3-vortex)
4. [LOITER-SIM — Autonomous Swarm Simulation](#4-loiter-sim)
5. [SDSS Cosmic IB Analysis](#5-sdss-cosmic-ib-analysis)
6. [OADF — Adiabatic Buccal Condensation](#6-oadf)
7. [Status Summary](#status-summary)

---

## 1. GRANITE-Astrophysics-Suite

**The Complete Theoretical, Kinematic, and Computational Archive of Extreme Multi-Body Gravitational Physics**  
`HTML` · `JavaScript` · `WebGL` · `LaTeX` · Analytical physics manuscripts  
[→ Repository](https://github.com/LiranOG/GRANITE-Astrophysics-Suite) · [DOI: 10.5281/zenodo.19502264](https://doi.org/10.5281/zenodo.19502264)

**Status:** Complete archive — actively referenced as the foundational layer of GRANITE-NR and VORTEX.

---

### What it is

The GRANITE-Astrophysics-Suite is not a simulation engine. It is the **origin record** — the chronological, immutable history of every intellectual step that preceded the C++ engine. It exists to answer a question any serious reader should ask of a numerical relativity code written by a solo independent researcher: *where did the physics come from, and how do you know it is right?*

The answer is documented in three layers, in the strict order in which they were built:

```
GRANITE-Astrophysics-Suite/
│
├── 01_Theoretical_Limit/    ← Layer I:   The mathematics was solved analytically
├── 02_Kinematic_Engines/    ← Layer II:  The physics was explored interactively
└── 03_GRANITE_Engine/       ← Layer III: The engine was specified and built
```

The dependency is enforced without exception:

> **No C++ module was designed until the mathematics demanded it.**  
> **No physics was implemented until it had been derived in closed form.**  
> **No architecture was chosen until the analytical predictions specified it.**

This is not retrospective rationalization. It is the founding constraint of the project — and the directory structure is the audit trail.

---

### The founding methodology — the exact build order

This is the chronological order in which the project actually unfolded. Not a logical diagram drawn after the fact, but a record of what was built when and why.

**Step 1 — The physics was solved analytically.**  
Before any code was written, every observable across both scenarios was derived in closed form, on paper. The NRCF, PRISM, SYNAPSE, AUE, and NEXUS frameworks were completed analytically. This phase produced quantitative predictions — specific numbers, frequency bands, energy budgets — for events that no existing tool could simulate. Only when this phase was complete did implementation begin.

**Step 2 — GRANITE-NR was built, driven entirely by the Septad.**  
The first implementation target was the Septad — the 7-body vacuum GR scenario. The C++ engine was designed from the ground up to handle what the Septad's analytical predictions required: CCZ4 constraint damping for long cascade timescales, AMR dynamic range spanning BH horizons to parsec-scale separations, and Ψ₄ extraction calibrated against the PRISM coherent-scaling prediction. The Octad did not exist as an implementation target at this stage. GRANITE was, at its origin, a Septad engine.

**Step 3 — The Octad emerged from questions the Septad could not answer.**  
Once the Septad scenario was analytically solved and the engine was being built to address it, new questions emerged that the vacuum-GR framework was structurally incapable of answering. What happens when the collapsing bodies are not pure black holes? What is the full multi-messenger budget when matter, radiation, and nuclear physics are present? These questions did not come from the literature — they came from working through the Septad's physics far enough to reach the boundary of what a pure-GR description can say. The Octad is the response.

**Step 4 — VORTEX was built around the Octad.**  
The Octad's eight-body, tri-species dynamics — qualitatively different approach-phase kinematics, tidal disruption events, mass-defect mergers — demanded an interactive laboratory that the Septad's simpler geometry had not required. VORTEX was built specifically to explore the Octad parameter space: testing the NEXUS cascade phases interactively, verifying the ECLIPSE integrator progression, validating the post-Newtonian approximations against analytical predictions before committing them to the C++ engine.

**Step 5 — GRANITE-NR and VORTEX were coupled.**  
With both engines mature, the coupling became the natural next step: GRANITE-NR's HDF5 simulation outputs feeding VORTEX as a high-fidelity 3D playback viewer. The two projects, developed for different scenarios along different tracks, converged into a unified simulation and visualization system.

---

Every major architectural decision in GRANITE-NR traces to a specific equation in `01_Theoretical_Limit/`:

| GRANITE-NR Module | Architectural Driver |
|---|---|
| CCZ4 formulation (not BSSN) | SYNAPSE cascade timescale required active constraint damping over long evolution |
| Valencia GRMHD | AUE uncertainty audit proved stellar disruption requires exact conservation on curved spacetime |
| M1 radiation transport | Analytical energy budget exposed a ~×10⁶ error in the naive EM burst estimate — only photon diffusion resolves it |
| AMR (≥12 levels target) | Dynamic range from BH horizons to circumbinary disk spans ~10⁸ — uniform grids are computationally impossible |
| Ψ₄ GW extraction at multiple radii | PRISM N²-scaling prediction required multi-radius validation to confirm coherence vs. incoherence regime |

The engine architecture follows directly from the analytical results — each module was specified by the mathematics before implementation began.

---

### The two research scenarios

The entire theoretical structure is organized around two extreme astrophysical events, separated by a single dimensionless parameter — the **Compactness Ratio**:

$$\mathcal{C} = \frac{R_{\ast}}{R_s} = \frac{R_{\ast}\,c^2}{2GM}$$

| Regime | C value | Governing physics | Scenario |
|---|---|---|---|
| **Geometric** — vacuum GR | C = 0 (pure BH) | Spacetime curvature; GW-dominated energy budget | **The Septad** |
| **Hydrodynamic** — matter | C ≫ 1 | Tidal disruption, nuclear burning, neutrino emission, EM transients | **The Octad** |
| **Transition** | C ~ 1 | Both regimes compete simultaneously | NS-NS mergers |

These are not arbitrary choices. They represent the two extremes of the compactness spectrum — the cleanest test cases for the two physically distinct regimes that a full-physics NR engine must eventually handle.

#### The Septad — Seven-Body Vacuum GR Scenario

The name is precise: *Septad* = seven. This is a 7 N-body gravitational collapse scenario — the ultimate target being seven supermassive black holes in symmetric configuration undergoing simultaneous radial coalescence.

The current flagship implementation uses **five SMBHs of 10⁸ M☉ each**, arranged in a symmetric gravitational pentagon at one parsec separation (the B5_star benchmark). This is not a simplification of the concept — it is the first validated step in a deliberate progression: 5-body → 7-body → 8-body, each step requiring both the engine maturity and the HPC resources to execute at production resolution. The 5-body run is where GRANITE-NR currently stands. The 7-body target follows once GPU porting and full AMR reflux are complete.

This is the vacuum GR scenario. No matter, no radiation, no nuclear physics — only curved spacetime and the merger of some of the most massive objects the universe produces. The question is not whether this is astrophysically common. It is whether the physics can be described completely and correctly, in closed form, before a numerical grid is ever laid down.

The analytical prediction chain for the Septad spans four frameworks (NRCF → PRISM → SYNAPSE → AUE), each building on the results of the previous one. The final predictions, derived analytically for the N-body symmetric case, are:

- **Total GW energy radiated:** E_GW ≈ 8.93 × 10⁶¹ erg (coherent N²-scaling regime)
- **Final merged mass:** M_f = 4.29 × 10⁸ M☉
- **Final spin parameter:** a*_f = 0.857
- **Merger cascade duration:** determined by SYNAPSE phase-space integration
- **Peak GW frequency:** in the nHz band — relevant to Pulsar Timing Array (PTA) observations

#### The Octad — Eight Bodies, Three Species

**Three neutron stars + two Wolf-Rayet supergiants + five R136a1-class ultra-massive stars converging on the same galactic nucleus.**

This is the hydrodynamic scenario. Eight bodies, three physically distinct species, four sequential merger phases, and a complete multi-messenger energy budget spanning gravitational waves, electromagnetic transients, and neutrino emission. The Octad is the test case for every physics module the Septad does not exercise — GRMHD, M1 radiation, nuclear burning, tidal disruption.

The analytical prediction chain for the Octad is structured as a four-phase cascade:

| Phase | Event | Primary physics |
|---|---|---|
| I | Ultra-massive star coalescence | Hydrodynamic merger; PISN candidate |
| II | Wolf-Rayet binary interaction | Wind stripping; mass transfer; pre-SN dynamics |
| III | Neutron star binary inspiral | GW-driven merger; SGRB candidate |
| IV | Remnant consolidation | Final BH formation; accretion disk dynamics |

**Central analytical results (NEXUS framework):**
- **Final remnant mass:** M_f ≈ 1239 M☉
- **GW bands active:** three distinct frequency ranges across the four phases
- **Neutrino luminosity peak:** quantified analytically during Phase III
- **Nucleosynthetic yield:** r-process elements from NS-NS merger ejecta

---

### Layer I — `01_Theoretical_Limit/` — The Analytical Manuscripts

Seven peer-review-grade analytical manuscripts. Five interlocking theoretical frameworks. Every observable derived to closed-form precision before numerical implementation began.

#### Framework dependency hierarchy

The frameworks form a strict mathematical dependency chain — each requires the results of its predecessors:

```
NRCF → PRISM → SYNAPSE → AUE        [Septad chain]
                       → NEXUS       [Octad extension]
                       → Comparative [Cross-scenario bridge]
                       → Engine Spec [Implementation mandate]
```

#### The seven frameworks

**NRCF — Numerical Relativity Collapse Framework**  
*Foundation layer. Establishes the geometric description of symmetric N-body radial collapse.*

The central result is the **geometric shape factor** for N-body symmetric collapse:

$$s_N = \frac{1}{4}\sum_{k=1}^{\lfloor N/2 \rfloor} \csc\!\left(\frac{\pi k}{N}\right)$$

This factor encodes how the geometry of the initial configuration — pentagon, hexagon, arbitrary N-gon — affects the gravitational wave emission and the collapse dynamics. It is the input to every subsequent framework in the Septad chain.

**PRISM — Polyhedral Radial Infall Scenario Model**  
*First-order prediction layer. Derives the GW energy budget from the NRCF geometry.*

Central result: the **coherent N²-scaling** of gravitational wave energy in symmetric multi-body collapse:

$$E_{\text{GW}} \propto N^2 \cdot \eta^2 \cdot M_{\text{total}}^2 / R_0$$

For the Septad (N=5 current flagship, N=7 target), this gives E_GW ≈ 8.93 × 10⁶¹ erg — a number that immediately specifies the strain amplitude and signal duration any detection instrument (LISA, PTA) would need to observe. PRISM also establishes when the collapse transitions from the coherent (N²) to the incoherent (N) scaling regime — which determines whether the signal is detectable as a coherent burst or as a stochastic background.

**SYNAPSE — Systematic N-body Analysis of Phase-Space Evolution**  
*Full cascade prediction layer. Integrates the complete merger sequence.*

SYNAPSE takes the NRCF geometry and PRISM energy budget and integrates the full merger cascade — the sequence of N → N-1 → ... → 1 mergers, each with its own timescale, mass loss, spin evolution, and GW emission.

Key results for the Septad:
- Final merged mass: M_f = 4.29 × 10⁸ M☉ (accounting for GW mass-energy loss at each step)
- Final spin: a*_f = 0.857 (angular momentum budget through the cascade)
- Full merger timescale from the phase-space integral
- Constraint damping requirement — the result that forced the choice of CCZ4 over BSSN

**AUE — Astrophysical Ultimate Estimator**  
*Systematic uncertainty layer. The most important document for the engine architecture.*

AUE is the analytical uncertainty audit — a systematic quantification of the error budget across every observable in the Septad prediction chain. Its purpose is not to produce predictions but to specify, from first principles, what precision any numerical engine must achieve to add information beyond the analytical estimate.

This is the document that specified the GRANITE-NR engine requirements:
- Minimum grid resolution per observable
- Required convergence order for constraint violation
- Acceptable tolerance on GW strain extraction
- The ~×10⁶ error in naive EM burst estimates that mandated M1 radiation transport
- The exact-conservation requirement on curved spacetime that mandated Valencia GRMHD over non-conservative schemes

AUE is, in a precise sense, the requirements document for GRANITE-NR. Every limitation in the engine's current state (see Section 2) can be mapped to a specific AUE requirement that has not yet been met.

**NEXUS — Neutron-star Extreme Scenario**  
*The Octad analytical framework. Four-phase tri-species cascade.*

NEXUS is the Octad counterpart to the SYNAPSE framework — the complete analytical treatment of the eight-body tri-species merger. It is structurally more complex than SYNAPSE because the three species (neutron stars, Wolf-Rayet stars, ultra-massive stars) interact through qualitatively different physical mechanisms at each phase of the cascade.

Central results:
- M_f ≈ 1239 M☉ (final remnant after all four phases)
- Three active GW frequency bands across the cascade
- Neutrino luminosity peak quantified analytically during the NS-NS phase
- r-process nucleosynthesis yield from NS-NS merger ejecta
- The Compactness Barrier as the organizing parameter distinguishing Phase I from Phase III dynamics

**Comparative Analysis — Septad vs. Octad**  
*Cross-scenario bridge. The Compactness Barrier as unifying principle.*

This manuscript formalizes the C = R*/Rs parameter as the organizing principle of the entire theoretical framework — showing that the Septad and Octad are not arbitrary choices but the two natural extremes of a single continuous parameter space. The analysis shows which physics modules activate at which compactness values, providing the activation logic that determines which GRANITE-NR modules engage for any given simulation configuration.

**Engine Specification — The GRANITE Blueprint**  
*The translation layer. Mathematics → architecture.*

This is the bridge document — the formal translation from the analytical predictions of the five frameworks above into a concrete software architecture specification. It is the document that authorized the construction of the C++ engine.

Every module in GRANITE-NR, every design decision, every trade-off between competing implementations traces back to a specific section of this document. The Blueprint is not aspirational documentation written after the fact. It was written before the first C++ file was created, and the engine was built to satisfy it.

---

### Layer II — `02_Kinematic_Engines/` — The Interactive Laboratory

Twenty-six browser-native HTML/JavaScript engines. Real-time physics at 60 fps. Zero installation, zero dependencies. The computational laboratory used to verify analytical derivations before numerical benchmarks existed.

Before the C++ engine existed to validate the analytical predictions, these interactive engines served as the computational laboratory — implementing the NRCF equations of motion, the SYNAPSE cascade logic, the NEXUS four-phase energy budgets, and post-Newtonian 2.5PN radiation reaction in real time, in the browser.

They are not toys. They are functional physics engines — and they were the primary tool for verifying the analytical derivations were internally consistent before numerical relativity benchmarks existed to confirm them.

#### Engine families

| Subdirectory | Contents | Role |
|---|---|---|
| `ENAE_7_Septad/` | PRISM, SYNAPSE, AUE engines | Direct implementations of the Septad analytical frameworks as live interactive simulations |
| `ENAE_8_Octad/ECLIPSE/` | 3 progressive N-body integrator versions | Evolution from basic Verlet integration through adaptive timestepping to the 4th-order Hermite scheme that became VORTEX |
| `ENAE_8_Octad/VORTEX/` | 7 WebGL 3D simulation engines | Direct predecessors of VORTEX ETERNITY — version history of how VORTEX was developed |
| `ENAE_8_Octad/FIRST_HALF/` | ASTRAL, CHRONOS, CONFLUENCE, GENESIS | Pre-merger approach-phase dynamics for the Octad cascade |
| `ENAE_8_Octad/SECOND_HALF/` | NEXUS, O.M.E.G.A., PROMETHEUS, others | Post-merger phases; PISN dynamics; final BH formation |
| `Standalone/` | Compactness Barrier visualization | Interactive cross-scenario comparison engine |

---

### Layer III — `03_GRANITE_Engine/` — The Genesis Archive

This layer does not contain C++ source code. The production engine lives in GRANITE-NR (Section 2). What this layer contains is the **Genesis Archive** — the founding document of the entire project.

**[THE GENESIS OF GRANITE](https://github.com/LiranOG/GRANITE-Astrophysics-Suite/blob/main/03_GRANITE_Engine/THE_GENESIS_OF_GRANITE.md)** is the manifesto that records, in chronological order:

- The precise questions that were asked before any code was written
- The analytical path from question to derivation to specification
- The point at which the mathematics became complex enough that analytical methods reached their limit — the moment a numerical engine became the only honest way forward
- The design decisions that followed from the mathematics, documented as they were made

It is, among other things, an answer to a question every serious reader should ask of any ambitious solo computational physics project: *why should I trust this was built correctly?*

The answer the Genesis Archive gives: because the physics was solved before the code was written, the code was specified before it was compiled, and every module can be traced back to the equation that demanded it.

---

### Relationship to GRANITE-NR and VORTEX

The GRANITE-Astrophysics-Suite is not a separate project that happens to share a name with GRANITE-NR. It is the **necessary precondition** for both engines — the work that had to be done before anything could be responsibly built. The relationship follows the exact build sequence:

| Stage | From Suite | → | To Engine |
|---|---|---|---|
| 1 — Analytical foundation | NRCF + PRISM + SYNAPSE (Septad chain) | → | Benchmark targets and module requirements for GRANITE-NR |
| 1 — Analytical foundation | AUE uncertainty audit | → | Specification of minimum precision requirements per module |
| 2 — GRANITE-NR built (Septad-driven) | Engine Blueprint specification | → | GRANITE-NR CMake module structure and physics kernel design |
| 3 — Octad questions emerge | NEXUS four-phase cascade | → | GRMHD + M1 radiation module requirements |
| 4 — VORTEX built (Octad-driven) | ECLIPSE integrator evolution | → | VORTEX Hermite integrator architecture |
| 4 — VORTEX built (Octad-driven) | VORTEX engine family (26 versions) | → | VORTEX ETERNITY Gold Master |
| 5 — Coupling | Genesis Archive | → | Unified simulation + visualization system; founding narrative |

The Suite is both the **requirements phase** and the **chronological record** of a project whose implementation lives in GRANITE-NR and VORTEX. Neither engine is intelligible without it.

---

### Licensing

The Suite employs a dual-licensing structure reflecting the dual nature of its contents:

| Domain | License | Scope |
|---|---|---|
| **Source code** | GPL-3.0 | All JavaScript engines, WebGL renderers, simulation logic |
| **Academic content** | CC BY-SA 4.0 | All analytical manuscripts, derivations, technical documentation |

### Known limitations of the Suite

The Suite contains the foundational theoretical work for everything that followed, but it has limitations that are important to state explicitly:

| Limitation | Details |
|---|---|
| **Not peer-reviewed** | None of the seven manuscripts has been submitted to a journal or reviewed by external NR specialists. Internal consistency is verified; external correctness is not. |
| **Solo derivation** | Every derivation was carried out by me, alone, without a colleague to cross-check the algebra. Errors of sign, factor, or formulation that a peer would catch immediately may still be present. |
| **Idealized geometries** | The Septad's perfectly symmetric N-body configuration is a research idealization — astrophysically, such a configuration is dynamically unstable and would not persist. The framework is a clean-limit study, not a prediction of an observable event. |
| **N-body cascade assumptions** | SYNAPSE assumes symmetric collapse to produce the cascade timescale. Real BH systems with arbitrary mass ratios, eccentricities, and spin orientations will deviate. The framework establishes upper-limit predictions, not realistic forecasts. |
| **NEXUS four-phase decomposition** | The clean separation into four sequential phases (PISN → WR → NS-NS → remnant) is a simplification. Real tri-species systems will have overlapping phases and feedback between them that NEXUS does not model. |
| **Empirical validation is partial** | GRANITE-NR has not yet completed a full merger run on either scenario. The analytical predictions are therefore unverified by the engine they motivated. |
| **Kinematic engines are not physics engines** | The 26 HTML/JS engines implement the analytical equations as live simulations, but they are not full-physics solvers. They cannot validate the underlying physics — only demonstrate that the analytical predictions are computationally tractable. |
| **DOI and Zenodo deposit** | The Zenodo deposit gives the work an archival identifier, not peer validation. The DOI is a citation handle, not an endorsement. |

---

## 2. GRANITE-NR

**General-Relativistic Adaptive N-body Integrated Tool for Extreme Astrophysics**  
`C++17` · `OpenMP` · `MPI` · `HDF5` · `Python`  
[→ Repository](https://github.com/LiranOG/Granite-NR) · [DOI: 10.5281/zenodo.19502264](https://doi.org/10.5281/zenodo.19502264)

**Current release:** v0.6.8 *(Architecture & Stability — released 9 May 2026)*

### What it is

GRANITE-NR is an open-source C++17 numerical relativity and GRMHD engine built from the ground up to simulate extreme astrophysical events — binary and multi-body black hole mergers, neutron star dynamics, accretion disk physics. It implements:

- **CCZ4 spacetime evolution** with active constraint damping (κ₁=0.02, η=2.0) and moving-puncture gauge
- **Valencia GRMHD** with HRSC shock-capturing (MP5/PPM/PLM), HLLE/HLLD Riemann solvers, and constrained transport (∇·B = 0 to machine precision)
- **Dynamic Berger-Oliger AMR** with per-step regridding, puncture-tracking, trilinear prolongation, and volume-weighted restriction (up to 12 levels; production validated at 4)
- **M1 radiation transport** (compiled, unit-tested; not yet wired into RK3 loop — v0.7 target)
- **Newman-Penrose Ψ₄ GW extraction** at multiple radii (50–500 r_g)
- **107 GoogleTest unit tests** across 20 suites (CCZ4, GRMHD, AMR, horizon finder, M1, HDF5 I/O, initial data)

### Validated benchmarks

| Configuration | Resolution | t_final | ‖H‖₂ reduction | NaN events |
|---|---|---|---|---|
| Single puncture (Schwarzschild) | 64³, 4-level AMR | 500 M | ×84.8 | 0 |
| Binary BH inspiral (equal-mass) | 64³, 4-level AMR | 500 M | ×61.3 | 0 |
| Binary BH inspiral (equal-mass) | 96³, 4-level AMR | 500 M | ×67.4 | 0 |

All benchmarks run on a single desktop workstation (Intel i5-8400, 16 GB RAM, WSL2). Fully reproducible from the repository.

### Known open limitations (v0.6.8)

These are the technical limitations of the engine as currently published. They are stated in the order of their importance to the work the engine is meant to do.

| Issue | Impact | Target |
|---|---|---|
| `--resume` CLI not yet wired (checkpoint write works) | Long runs non-resumable without code change | v0.7 |
| M1 not integrated into RK3 evolution loop | Radiation inactive in production | v0.7 |
| AMR reflux correction is a stub (computed but not applied) | Accuracy limitation at coarse-fine interfaces | v0.8 |
| AMR prolongation is trilinear (2nd-order) only | Limits accuracy gain from refinement levels | v0.8 |
| No GPU path (GTX 1050 Ti not viable for FP64) | Desktop-only resolution | Post GPU porting |
| t=500M BBH reaches early inspiral only — no merger observed | SXS waveform comparison not yet possible | v0.8–v0.9 |
| Lapse stabilizes at ~0.93 rather than the expected trumpet solution value (~0.3) | Known open issue under investigation; suggests gauge condition or initial data subtlety | Under investigation |
| Anomalous resolution convergence ordering in some scans | Suggests subtle issue in the convergence test setup or in the AMR refinement criteria | Under investigation |
| Production benchmarks validated at 4 AMR levels, not the 12-level target for B5_star | Limits dynamic range below what the flagship scenario requires | v0.7+ |
| Native Windows unsupported; macOS Homebrew not CI-gated | Limits CI coverage; macOS issues cannot be caught automatically | v0.8+ |
| Recoil velocity computation throws `std::runtime_error` (not implemented) | One specific diagnostic unavailable | v0.7 |
| Only `postprocess/` module lacks dedicated unit tests | Coverage gap; all other physics modules have test suites | v0.7 |

### Wider honest assessment of GRANITE-NR

Beyond the per-issue table, I want to be explicit about what GRANITE-NR is and is not at this stage:

- **It is** a working CCZ4 + GRMHD + AMR engine that maintains constraint convergence over 500 M of binary BH inspiral on a desktop machine. That is a real, measurable, reproducible achievement.
- **It is not** a validated production NR code in the sense that Einstein Toolkit, GRChombo, or SpECTRE are validated. The benchmark library is small, no merger has been observed, no comparison against the SXS catalog exists, and no external NR specialist has reviewed the implementation.
- **It is not yet** what the GRANITE-Astrophysics-Suite specified. The Blueprint specified the full machine. The current engine implements roughly 70–80% of what the Blueprint required. The remaining work is documented in the roadmap.
- **Honest assessment of readiness:** roughly 60–65% of the way to being publication-ready for a numerical relativity venue with full validation. The architecture and code quality are strong; the physics validation is partial; the production runs are pending HPC access I do not have.

### Roadmap (honest version)

- **v0.7.0** (Q4 2026): GPU CUDA kernels, checkpoint restart, M1 wired into RK3
- **v0.8.0** (Q1 2027): Tabulated nuclear EOS + reaction network
- **v0.9.0** (Q2 2027): Full SXS catalog comparison (~60 BBH configs)
- **v1.0.0** (Q3 2027): B5_star flagship run + JOSS publication

The path to v0.9 requires HPC resources I do not currently have. This is documented honestly in the repository — the roadmap reflects aspiration, not guaranteed delivery.

---

## 3. VORTEX

**Interactive Browser-Native Relativistic N-Body Simulator**  
`JavaScript` · `WebGL` · `GLSL` · `Chart.js`  
[→ Live Demo](https://liranog.github.io/VORTEX) · [→ Repository](https://github.com/LiranOG/VORTEX)

**Status:** Stable — Gold Master released as part of GRANITE v0.6.6.

### What it is

VORTEX is a standalone, zero-dependency browser application implementing post-Newtonian N-body dynamics with real-time WebGL rendering. No installation required — runs in any modern browser.

**Physics engine:**
- 4th-order Hermite predictor-corrector integrator with Kahan compensated summation
- Dynamic Aarseth timestepping
- **1.5PN Lense-Thirring** frame-dragging (spin-orbit coupling)
- **2.5PN radiation reaction** (gravitational wave inspiral energy loss)
- Mass-defect mergers with momentum conservation
- Tidal Disruption Events (TDE)

**Architecture:** Zero-allocation hot path — all computation on pre-allocated Float32Arrays with no per-frame GC pressure.

**Research-grade diagnostics:**
- Live orbital eccentricity vs. semi-major axis panels
- GW chirp frequency sweep (f_GW)
- Relativistic velocity parameter (β²)
- Gravitational isobar contours (marching-squares)
- ISCO proximity warnings

**18 astrophysical scenarios:** GW150914 (LIGO merger), Sagittarius A* N-body cascade, Solar System, EMRI, ZKL (Kozai-Lidov), and others.

**Known open issue:** The 2PN conservative correction term is not yet implemented. This is the only documented gap in the post-Newtonian expansion at the target accuracy level. It does not affect qualitative behavior but limits quantitative precision at high eccentricity. This is the documented priority for the next development cycle.

### Wider honest assessment of VORTEX

The 2PN gap is the most prominent missing piece, but it is not the only one. A complete account of VORTEX's limitations:

| Limitation | Details |
|---|---|
| **No 2PN conservative correction** | The most prominent gap. Limits quantitative accuracy at high eccentricity. |
| **No 3PN, 3.5PN, 4PN, or 4.5PN terms** | Higher-order PN corrections that become important near merger are absent. VORTEX is accurate in the inspiral regime; near-merger behavior is approximate. |
| **No EOB resummation** | The Effective One Body formalism, which is the standard way to extend PN expansions to the strong-field regime, is not implemented. |
| **No tidal deformability** | For NS-NS or NS-BH scenarios, tidal effects on the inspiral are absent. |
| **No QNM ringdown** | After merger, the ringdown phase is not modeled — VORTEX terminates the orbital evolution at merger. |
| **No GW recoil kick** | The momentum carried away asymmetrically by GW emission, which gives merger remnants their characteristic "kick velocity," is not computed. |
| **No spin precession at higher PN orders** | Only 1.5PN Lense-Thirring is implemented. Higher-order spin-orbit and spin-spin couplings are absent. |
| **Not validated against external N-body codes** | VORTEX has not been benchmarked against established codes (rebound, NBODY7, BHTree). Its internal Hermite integrator is correct against the analytical references I used, but external cross-validation is missing. |
| **Browser performance ceiling** | Single-threaded JavaScript with Float32 precision. Cannot match the speed or precision of a compiled C++ N-body code on the same problem. |
| **Single-file architecture** | The entire codebase is one HTML file. This is intentional for distribution simplicity, but it makes large-scale collaboration on the code difficult. |
| **No analytical regression tests** | The 18 scenarios produce visually correct behavior, but there is no automated test that asserts, e.g., "GW150914 produces a chirp frequency within X% of the observed value." Verification is by inspection, not by assertion. |

### Coupling with GRANITE-NR

The long-term vision for VORTEX is to serve as a high-fidelity playback viewer for GRANITE-NR's HDF5 simulation output — ingesting the spacetime data and rendering it interactively in the browser. This coupling is a post-v1.0 target.

---

## 4. LOITER-SIM

**Deterministic Multi-Agent Simulation Engine for Autonomous UAV Swarms**  
`C++17` · `Python`  
[→ Repository](https://github.com/LiranOG/LOITER-SIM)

**Status:** Pre-alpha — Design and specification phase. **No executable simulation code is published yet.**

### What it is

LOITER-SIM is a simulation framework targeting the physics and decision-making of autonomous drone swarms in adversarial environments — specifically counter-UAS (C-UAS) and multi-agent reinforcement learning scenarios.

The repository currently contains:
- Full architecture specification
- Physics and sensor modeling documentation
- Governance structure and specification framework
- Milestone roadmap targeting v1.0 in Q3 2028, with implementation scheduled to begin Q1 2027

### Transparency note

LOITER-SIM is listed publicly because the specification documents are real, complete, and open to expert review and critique. The binding test for this project — whether committed implementation code appears by Q2 2027 — will determine whether it advances past the design phase.

The August 2026 return from hiatus is the planned start of active implementation. All specification documents remain readable and stable.

### Known limitations of LOITER-SIM

LOITER-SIM has more limitations than any other project in this portfolio, by virtue of being earlier in its lifecycle:

| Limitation | Details |
|---|---|
| **No executable code published** | The repository contains specifications, design documents, and roadmap material only. Nothing yet runs. |
| **Implementation date is aspirational** | Q1 2027 implementation start, Q3 2028 v1.0 — these are dates I have committed to publicly, but they are not contractually binding to anyone. |
| **Specifications are unreviewed** | No external expert in C-UAS, multi-agent RL, or autonomous systems has reviewed the design. Errors in the architectural assumptions may exist. |
| **Domain sensitivity** | C-UAS is a sensitive domain with overlap into defense applications. The project is explicitly civilian-focused (simulation only, no operational targeting), but the line between "simulation framework" and "operational tool" requires careful navigation that has not yet been formally addressed. |
| **No sensor model validation** | The sensor modeling in the spec assumes idealized noise models that may not match real-world EO/IR/RF sensor performance. |
| **No external dataset or scenario library** | Real C-UAS validation requires representative scenario data that I do not currently have access to. |
| **Single-developer scoping risk** | The roadmap may be unrealistic for one person. The 2027 implementation start may slip, or the v1.0 scope may need to shrink. |

---

## 5. SDSS Cosmic IB Analysis

**Python Pipeline for Cosmic-Scale Information Bottleneck Measurement**  
`Python` · `HEALPix` · `Astropy` · `scikit-learn`  
[→ SDSS_Data Repository](https://github.com/LiranOG/SDSS_Data) · [→ Dashboard Repository](https://github.com/LiranOG/cosmic-ib-dashboard)

**Status:** Functional pipeline — empirical results published.

### What it is

This pipeline processes SDSS DR18 photometric galaxy survey data to measure what I call the Information Bottleneck efficiency (η_IB) of the cosmic large-scale structure — testing a specific quantitative prediction from the Fractal Cosmopsychism Theory (FCT).

**Pipeline components:**
- HEALPix sky mapping and angular power spectrum estimation
- TDA (Topological Data Analysis) persistent homology for void/sheet/filament classification
- Information Bottleneck mutual information estimation (T-Web classification)
- Streamlit interactive dashboard for result visualization

**Empirical result:** η_IB ≈ 0.0045 (measured from SDSS DR18)

**Theoretical prediction (from FCT):** η_IB ≈ 0.42

The ~93× discrepancy is the central unresolved tension of this project. Possible explanations:
1. The IB estimator I used is methodologically too crude for the cosmic data structure
2. The proxy I chose for "cosmic compression" does not capture what FCT actually predicts
3. FCT's prediction for η_IB at galactic scales is wrong

I cannot currently distinguish between these. The data and code are open. The most useful contribution a qualified cosmologist or information theorist could make is to look at the measurement methodology and tell me which is most likely true.

> **Important:** This pipeline was built to test a theoretical prediction from FCT, which is a speculative framework (see [THEORIES.md](./THEORIES.md)). The pipeline itself — as a data processing and measurement tool — is independent of whether FCT is correct.

### Known limitations of the SDSS Cosmic IB analysis

| Limitation | Details |
|---|---|
| **The 93× discrepancy is unresolved** | The central scientific issue. Until the gap between measurement and prediction is explained, the result is a tension, not a confirmation or refutation. |
| **IB estimator may be too crude** | Information Bottleneck mutual information estimation in high-dimensional sparse data is a known hard problem. I used a relatively simple estimator. A more sophisticated estimator (e.g., MINE, KSG with appropriate corrections) might give a substantially different number. |
| **Proxy for "cosmic compression" is heuristic** | The choice of which observable to treat as the "compressed representation" T in the IB framework was made by physical reasoning, not derived from first principles. A different choice could change the predicted value of η_IB by orders of magnitude. |
| **DR18 only — no cross-survey validation** | The pipeline has been run on SDSS DR18. It has not been cross-validated against DES, DESI, Euclid, or other surveys. A measurement that depends on the survey is not yet a robust measurement. |
| **Photometric only — no spectroscopic confirmation** | The T-Web classification uses photometric data. Spectroscopic data would give cleaner void/sheet/filament identification. |
| **TDA persistent homology stability** | Persistent homology results can be sensitive to noise and sampling density. The TDA component of the pipeline has not been formally tested for stability under perturbations. |
| **Pipeline tests a speculative theory** | Even if the measurement is methodologically perfect, it tests a theory (FCT) that is itself unvalidated. The pipeline's scientific value is currently coupled to the theory's status. |
| **Streamlit dashboard is illustrative, not interactive analysis** | The dashboard visualizes results. It is not a tool for re-running the analysis with different parameters. |

---

## 6. OADF

**Oral Adiabatic Decompression Fog — Physics of the Mouth-Pressure Vapor Puff Phenomenon**  
`LaTeX` · `TikZ` · Physics research paper  
[→ Repository](https://github.com/LiranOG/OADF-Adiabatic-Buccal-Condensation)

**Status:** Complete — working paper (not submitted to any journal).

### What it is

OADF is a formal physics analysis of a phenomenon most people have experienced but nobody has rigorously modeled: the visible vapor puff produced by exhaling pressurized air through a small oral aperture.

**Deliverables:**
- 21-page LaTeX academic paper with 30+ equations and TikZ diagrams
- 30-source bibliography
- English and Hebrew HTML document versions
- Central result: a closed-form expression for post-expansion supersaturation, including a worked numerical example

This is one of the most complete projects in the portfolio — a defined physical problem, a formal treatment, and a verifiable closed-form result. It is also, intentionally, a demonstration that the scientific methodology applies equally well to questions both grand and mundane.

### Known limitations of OADF

| Limitation | Details |
|---|---|
| **Working paper — not peer reviewed** | The paper has not been submitted to any journal and has not been reviewed by atmospheric physicists or thermodynamicists. The derivation is internally consistent; external correctness is not certified. |
| **Idealized geometry** | The oral aperture is modeled as a circular orifice with idealized boundary conditions. Real human anatomy is more complex and varies between individuals. |
| **No experimental measurements** | The paper is theoretical only. No measurements of actual vapor puff formation have been made to validate the closed-form supersaturation expression. |
| **Representative numerical example, not measured parameters** | The worked numerical example uses physically reasonable parameter values, but these are not measured for a specific real case. |
| **30-source bibliography is broad, not deeply verified** | I have cited 30 sources, but I have not personally verified that every cited source supports the specific claim I attribute to it at the level a referee would. |
| **Topic is mundane** | OADF is a complete piece of theoretical work, but the phenomenon it describes is of limited scientific significance. Its value is primarily methodological — demonstrating that any well-posed physical question deserves rigorous treatment. |

---

## Status Summary

| Project | Domain | Status | Artifacts Available | Validated |
|---|---|---|---|---|
| GRANITE-Astrophysics-Suite | Analytical Physics + Interactive Simulation | Complete archive | ✅ Manuscripts + HTML engines | ✅ Internally consistent analytical chain |
| GRANITE-NR | Numerical Relativity | Active (v0.6.8) | ✅ Full C++17 engine | 🚧 Under development — inspiral validated, merger pending |
| VORTEX | PN N-Body Simulation | Stable | ✅ Single-file HTML | 🚧 Under development — 18 scenarios live, 2PN correction pending |
| LOITER-SIM | UAV Swarm Simulation | Design Phase | ⚠️ Spec only | ❌ |
| SDSS Cosmic IB | Observational Analysis | Functional | ✅ Python pipeline | ✅ Results published |
| OADF | Atmospheric Physics | Working Paper | ✅ LaTeX/HTML | ✅ Closed-form result |

---

*For the theoretical frameworks that motivate some of this work, see [THEORIES.md](./THEORIES.md).*  
*For the broader vision and philosophy behind all of it, see [VISION.md](./VISION.md).*  
*To collaborate or contribute, see [COLLABORATE.md](./COLLABORATE.md).*
