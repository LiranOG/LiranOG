# Theoretical Frameworks

**Liran M. Schwartz** · Independent Researcher · Haifa, Israel  
`scliran9@gmail.com` · [ORCID 0009-0008-8035-1308](https://orcid.org/0009-0008-8035-1308)

---

## Before you read

Everything in this document is speculative. None of the frameworks below has been peer-reviewed or submitted to a journal. They are structured hypotheses — internally consistent, formally articulated, and published to invite critique.

They are *candidates* — structures I find compelling, that I have worked hard to formalize, and that I am putting in front of the world in order to find out whether they have any contact with reality. If you are an expert in any of the relevant fields, I am asking for specific feedback, not agreement.

---

## Why I publish speculative work at all

A reasonable question, given everything above: if I know these frameworks are speculative, if I am aware that publishing them invites skepticism that may follow me into the engineering side of my portfolio, why publish at all?

Three reasons, in order of importance:

**One. The drawer is worse than the criticism.** A theoretical framework that sits unpublished in a folder on my hard drive cannot be improved by anyone who knows more than I do about its subject. The worst that happens by publishing is that experts point out the framework is wrong — at which point I learn something. The worst that happens by hiding is that I continue thinking I have something when I do not, and I never find out.

**Two. The honest version of the work includes its speculative components.** If I publish only the engineering and hide the theoretical frameworks that motivated parts of it, I am misrepresenting what I actually do. The SDSS pipeline was built to test FCT. The choice to build GRANITE-NR rather than something more practical was shaped by the same fascination with deep questions that produced CFD and CAT. Showing only one half is a lie of omission.

**Three. I want collaborators who are not deterred by speculation.** The people most likely to help me move any of this forward are people who can engage with speculative ideas without dismissing them on contact, while also being willing to tell me directly when I have made a mistake. I would rather filter for that audience up front than build a relationship that breaks the moment a non-trivial theoretical claim enters the conversation.

If speculative work is outside your interest, [RESEARCH.md](./RESEARCH.md) covers the engineering without reference to the theory. But if you can engage with speculation seriously — neither dismissing it because it is speculative nor accepting it because it sounds compelling — then we have something to talk about.

---

## The epistemic scale

Every framework below is marked with its current epistemic status:

| Status | Meaning |
|---|---|
| 🔴 **Speculative** | Internally consistent framework; no empirical validation; predictions not yet testable by me |
| 🟡 **Tested — Unresolved** | Empirical test attempted; result does not confirm the theory; open question |
| 🟢 **Grounded** | Built on peer-reviewed literature; the critique is about the synthesis, not the components |

None of the frameworks below has been peer-reviewed. None has been submitted to a journal. None should be treated as established science. They represent my best thinking, made public, in the hope that exposure to scrutiny will improve them or retire them.

---

## Table of Contents

1. [Fractal Cosmopsychism Theory (FCT / UIBIC)](#1-fractal-cosmopsychism-theory)
2. [Coupled Functional Differentiation (CFD)](#2-coupled-functional-differentiation)
3. [Civilization Asynchrony Theory (CAT)](#3-civilization-asynchrony-theory)
4. [The Chrono-Optical-Eusocial Fermi Model (COE-F)](#4-the-chrono-optical-eusocial-fermi-model)
5. [How to engage with this work](#how-to-engage-with-this-work)

---

## 1. Fractal Cosmopsychism Theory

**FCT / UIBIC (Universal Information Bottleneck Integrated Consciousness)**  
Status: 🟡 **Tested — Unresolved**  
[→ Repository](https://github.com/LiranOG/Fractal-Cosmopsychism-Theory) · [→ Empirical Dashboard](https://github.com/LiranOG/cosmic-ib-dashboard)

### Core claim

Consciousness is not a property unique to biological brains. It is a specific *type* of information processing — one that can in principle emerge wherever a physical system performs lossy compression of its environment in a way that maximally preserves predictive power.

The formal claim: consciousness emerges wherever a physical system instantiates the Information Bottleneck (IB) objective with sufficient efficiency, regardless of substrate. This is IB theory applied not to neurons but to any physical system that compresses environmental information for predictive use — including, at the extreme end, large-scale structure in cosmology.

### The mathematical framework

FCT is formalized as 13 equations (SYN-01 through SYN-13), of which two are the core:

**SYN-02R** (Information Bottleneck objective):
```
min_{p(t|x)} [ I(X;T) - β · I(T;Y) ]
```
where X is the environment representation, T is the compressed internal state, Y is the predicted future state, and β is the compression-relevance tradeoff.

**SYN-04** (Integrated Information analogue):
```
Φ_IB = I(X;T) · [1 - H(T|Y)/H(T)]
```
A modification of Integrated Information Theory (Tononi) that replaces the causal-structure constraint with an IB compression-efficiency constraint.

### What distinguishes FCT from standard IIT

Standard IIT claims consciousness requires integrated causal power (φ) across a system's elements. FCT replaces the causal-structure requirement with a compression-efficiency requirement. The practical difference: IIT implies consciousness requires biological-style neural integration; FCT implies it requires IB compression, which can in principle occur in non-biological substrates including — at the extreme end — galactic filament networks.

The galactic extension is the most controversial part. I do not claim galaxies are conscious in any human sense. I claim they may satisfy the formal conditions for the same *type* of information processing that underlies consciousness. This is a category distinction that matters, and I am careful about it in the full paper.

### Empirical test and result

To test FCT, I built a pipeline to measure η_IB (Information Bottleneck efficiency) in the cosmic large-scale structure using SDSS DR18 photometric data.

- **Measured:** η_IB ≈ 0.0045
- **Predicted by FCT:** η_IB ≈ 0.42
- **Discrepancy:** ~93×

This is a large gap. I have not explained it away. Three candidate explanations, none of which I can currently distinguish:

1. The IB estimator I used is too crude for the cosmic data structure (mutual information estimation in high-dimensional sparse data is a known hard problem)
2. The proxy I chose for "cosmic compression" does not capture what FCT actually predicts
3. FCT's prediction for η_IB at galactic scales is wrong

### Known limitations of FCT

| Limitation | Details |
|---|---|
| **The 93× empirical gap is unresolved** | The central scientific tension. Until explained, the framework is in an unverified state. |
| **The 13 equations are not peer-reviewed** | Internal consistency is checked. External validity by domain experts is not. |
| **The mapping from IB to "consciousness" is philosophically contested** | Even if the IB framework is mathematically sound at cosmic scales, the leap from "this system performs IB compression" to "this system has consciousness in any meaningful sense" is a separate claim that requires its own defense. |
| **The galactic extension is the most fragile component** | The core IB framework (SYN-02R, SYN-04) is on firmer ground than the cosmological scaling argument that produces the η_IB ≈ 0.42 prediction. The latter is where I most expect the framework to fail. |
| **No formal connection to existing consciousness literature** | I have not formally integrated FCT with Tononi's IIT, GWT (Global Workspace Theory), HOT (Higher Order Theories), or the Free Energy Principle. A serious philosophical defense would require this. |
| **The "Universal" in UIBIC overstates** | The framework claims IB compression occurs across many scales. It does not claim every system at every scale is conscious. The naming may suggest more than the framework delivers. |
| **No falsification criterion that I cannot personally adjust** | The 93× gap is currently explained by methodology rather than treated as a falsifying observation. A more rigorous version of FCT would commit, in advance, to a specific measurement methodology and accept the result. |

### Honest assessment

The IB core of FCT (SYN-02R, SYN-04) is grounded in real mathematics with real published literature behind it (Tishby; Schwartz & Tishby 2000; IIT in its various forms). The extension to cosmological scales is novel and speculative. The empirical result is not a confirmation — it is an unresolved tension, and I publish it as such.

---

## 2. Coupled Functional Differentiation

**CFD**  
Status: 🔴 **Speculative**  
[→ Repository](https://github.com/LiranOG/Coupled-Functional-Differentiation)

### Core claim

Human social systems — economies, institutions, civilizations — behave like coupled dynamical systems undergoing functional differentiation. The same mathematical structures that describe bifurcation, phase transitions, and attractor dynamics in physical systems apply to the evolution of human organizational structures over historical timescales.

### What the theory describes

CFD is a framework for understanding *why* human civilizations develop the specific failure modes they do. The core mechanism: as a social system increases in complexity and specialization (functional differentiation), the coupling between its subsystems becomes simultaneously stronger (more interdependent) and more brittle (less able to absorb perturbation).

This predicts:
- Complex civilizations are systematically more vulnerable to cascading failure than simpler ones, even when their absolute resilience appears greater
- The rate of specialization has a critical threshold above which the coupling structure becomes unstable
- Certain organizational topologies (highly centralized vs. distributed) have qualitatively different failure modes under stress

### What this is not

CFD is not a predictive model of specific historical events. It is a qualitative framework — a language for analyzing civilizational dynamics. It does not produce numerical predictions. It is closer to complex systems theory (Kauffman, Holland) applied to social science than to anything in physics proper.

### Known limitations of CFD

| Limitation | Details |
|---|---|
| **Not formalized mathematically** | The framework is described in prose and conceptual diagrams. There is no formal dynamical system, no equations of motion, no parameters that could be estimated from data. |
| **No specific quantitative predictions** | CFD does not say "civilizations with coupling parameter above X will collapse within Y years." It says "increased coupling produces brittleness." This is qualitative. |
| **No comparison to existing complex systems literature** | I have not formally placed CFD within the existing literature on complex adaptive systems, network resilience, or computational social science. Much of what CFD claims may already be formalized elsewhere under different names. |
| **No historical case study analysis** | A serious version of CFD would identify specific historical collapses (Rome, Maya, Bronze Age) and analyze them through the framework. I have not done this work. |
| **Overlaps with existing theories** | CFD's central claims overlap with Tainter's "Collapse of Complex Societies," Diamond's collapse framework, and various network theory results on cascade failure. The overlap has not been formally mapped. |
| **Risks being a "language without claims"** | If the framework is purely qualitative and overlaps with existing literature, it is unclear what specific value it adds. This is a real concern I have not resolved. |
| **Solo author bias** | The framework was developed by one person reflecting on history and systems. It has not been challenged by historians, economists, or complex systems specialists who might find it naive or incorrect. |

### What it would take to validate or retire CFD

CFD would require formalization into a quantitative dynamical systems model, followed by comparison against historical data on civilizational collapse and reorganization events. This is significant work I have not done. The framework as published is a structured intuition, not a tested model. If anyone with expertise in complex adaptive systems wants to look at it and tell me it is just restating known results in new vocabulary, I will accept that.

---

## 3. Civilization Asynchrony Theory

**CAT**  
Status: 🔴 **Speculative**  
[→ Repository](https://github.com/LiranOG/CAT-Simulation-Engine)

### Core claim

CAT proposes a mechanism for the Fermi Paradox — the observed absence of detectable extraterrestrial intelligence despite the statistical expectation that it should exist.

The claim: the absence of contact is explained not by the Great Filter alone (civilizations are destroyed before becoming spacefaring) and not by the Zoo Hypothesis (they are hiding from us) but primarily by **temporal asynchrony** — the window during which a civilization is both capable of interstellar communication and actively attempting it is narrow compared to the timescales of stellar and galactic evolution.

### The mechanism

Civilizations that survive long enough to attempt interstellar communication undergo rapid internal transformation — either toward post-scarcity structures that no longer prioritize expansion, or toward technological architectures that communicate in ways we would not recognize. The "broadcasting window" is short.

This combines with the observation that even a small temporal offset (millions of years, negligible in stellar terms) means two civilizations at comparable development levels are unlikely to be simultaneously in their broadcasting phase. The probability of overlap drops faster than the abundance of civilizations grows.

### Why I find this more compelling than the alternatives

The Great Filter is unfalsifiable in the absence of contact — any level of silence is consistent with it. The Zoo Hypothesis requires coordinated behavior across independent civilizations. CAT requires only that civilizations evolve and that broadcasting behavior is a transient phase. The latter seems mechanistically more plausible.

### Known limitations of CAT

| Limitation | Details |
|---|---|
| **Not formalized as a quantitative model** | CAT describes a mechanism. It does not give the duration of the "broadcasting window" as a function of any measurable parameter, and it does not produce a predicted contact probability as a function of galactic age. |
| **The "simulation engine" in the repo name is aspirational** | The repository describes agent-based simulation work that would explore CAT's statistical predictions. That work is in early stages. The framework as published is the structured argument, not a simulation result. |
| **Hand-waved timescale for the broadcasting window** | The central claim depends on the broadcasting window being short compared to stellar evolution timescales. I assert this; I do not derive it. A serious version of CAT would derive the window duration from specific assumptions about civilizational evolution. |
| **No engagement with existing Fermi Paradox literature** | I have read enough of the SETI literature to know that CAT is not entirely unprecedented (related ideas exist in Sagan, Drake, Freitas, Webb), but I have not formally placed CAT within that literature. |
| **Anthropic assumption risk** | CAT implicitly assumes that civilizations evolve in ways that resemble human technological development. If alien civilizations evolve along qualitatively different trajectories, the "broadcasting window" concept may not apply to them at all. |
| **Single-mechanism explanation in a multi-mechanism problem** | The Fermi Paradox almost certainly has multiple contributing causes. CAT proposes one mechanism. Even if CAT is correct, it cannot be the full answer. |

---

## 4. The Chrono-Optical-Eusocial Fermi Model

**COE-F / Three-Layer Fermi Model**  
Status: 🔴 **Speculative** (Layers 2 & 3) · 🟢 **Grounded** (Layer 1)

### What it is

This is my most developed attempt at a formal Fermi Paradox resolution — a three-layer model that stacks three independent mechanisms, each of which alone provides partial resolution, and which together produce a strong prior against observable contact.

**Layer 1 — Chrono-Optical Horizon:**  
The expansion of the observable universe means that even signals traveling at the speed of light from civilizations that have been broadcasting for billions of years may not yet have reached us, depending on when they originated and where. This is a hard physical constraint.

**Layer 2 — Asynchronous Bottleneck:**  
This is the CAT mechanism above — civilizations pass through a brief broadcasting window and then either go silent, transform, or collapse. The probability of two civilizations being in their respective windows simultaneously decreases with the duration of the window relative to cosmic timescales.

**Layer 3 — Eusocial Paradox (most novel layer):**  
Complex intelligence may systematically evolve toward eusocial organizational structures — not in the ant-colony sense, but in the sense of convergent internal coherence that reduces the motivation for external contact. A civilization that has achieved internal integration at the scale of its home system may simply have no compelling reason to signal outward, not due to hiding but due to a genuine lack of interest in entities it cannot yet model or relate to.

The symmetric formulation of Layer 3 — that this same dynamic applies to us — is the component I consider most original relative to published SETI literature. The claim that the absence of contact is partly explained by our own evolving eusociality, not just theirs, inverts the usual framing of the Paradox.

### Known limitations of COE-F

| Limitation | Details |
|---|---|
| **Layer 1 is physics; Layer 2 is speculation; Layer 3 is more speculative still** | The three layers are at different epistemic levels. Conflating them in a single model risks lending Layer 1's credibility to Layer 3 unjustifiably. |
| **No formal coupling between the three layers** | The model claims the three mechanisms combine to produce a strong prior against contact. The mathematical coupling — how the probabilities multiply or compound — is not derived. |
| **Layer 3 depends on assumptions about convergent civilizational evolution** | The claim that "complex intelligence evolves toward eusocial integration" is a strong empirical claim with a sample size of one (us). It may be entirely wrong. |
| **The "Eusocial Paradox" terminology may be misleading** | Using "eusocial" — a term with specific meaning in biology — for civilizational integration may suggest a tighter analogy than I actually mean. |
| **Symmetric formulation may not be original** | I claim Layer 3's symmetric formulation is novel relative to published SETI literature. I have searched the literature but not exhaustively. The argument may be in Freitas, Stephenson, or others I have not found. If it is, the novelty claim retires. |
| **No quantitative predictions** | The model does not say "given these mechanisms, we should expect contact with probability X by year Y." It is structurally similar to CAT in this respect. |
| **Anthropic and survivorship biases** | We are the one civilization we know about. Reasoning about typical civilizational evolution from a sample of one is methodologically fragile. |

### Epistemic status by layer

- **Layer 1 (Chrono-Optical Horizon):** Well-established physics. Critique here would have to engage with cosmological expansion and lightcone geometry.
- **Layer 2 (Asynchronous Bottleneck):** Speculative but mechanistically straightforward. Critique requires engaging with civilizational evolution timescales.
- **Layer 3 (Eusocial Paradox):** Most speculative; most novel; most likely to be wrong in ways I cannot see. If someone has seen this argument made formally elsewhere, I would genuinely want to know.

---

## How to engage with this work

If you are a researcher in any of the relevant fields — information theory, cosmology, complex systems, SETI, computational social science, philosophy of mind — and you find something worth engaging with here, I am interested in your critique at any level of skepticism.

I do not need you to be convinced. I need you to be specific about what is wrong, what is missing, and what would constitute evidence one way or the other.

The most useful feedback I can receive is not "this is too speculative" (I know that) but something like:

- "Your measurement of η_IB is methodologically flawed because it uses estimator X when the data structure requires estimator Y."
- "CFD's central mechanism is already formalized in this 2018 paper by Z, and your version is a less rigorous restatement."
- "The CAT broadcasting-window argument fails to account for [specific dynamic] that has been studied in [specific paper]."
- "Layer 3 of the COE-F model is already in Freitas (1983), here is the reference."
- "The mapping from IB compression to consciousness in FCT does not follow because [specific philosophical argument]."

Specific critique advances the work. Generic skepticism does not, but I understand and welcome it as a signal of how the work lands on first reading.

**Contact:** `scliran9@gmail.com` · GitHub Issues on the relevant repository · GitHub Discussions for broader theoretical questions.

---

*For the engineering projects that implement and test some of these ideas, see [RESEARCH.md](./RESEARCH.md).*  
*For the broader vision behind why I work on all of this, see [VISION.md](./VISION.md).*  
*To collaborate, see [COLLABORATE.md](./COLLABORATE.md).*
