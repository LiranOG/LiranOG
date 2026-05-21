# Portfolio Reading Guide

**A map of the four extended documents in this profile. Read this first if you are not sure where to start.**

---

## The shortest possible version

If you only take one thing from this guide, take this:

> **Read the engineering as engineering.**  
> **Read the theories as hypotheses — labeled, status-marked, and unvalidated unless explicitly noted.**  
> **Read the vision as personal motivation, not as evidence.**  
> **Read the collaboration document if you can actually help with something.**

That sentence is the entire guide compressed. The rest of this document expands it.

---

## The four documents at a glance

| Document | Length | Tone | Best for | What you will find |
|---|---|---|---|---|
| **[RESEARCH.md](docs/RESEARCH.md)** | ~6,500 words | Cold, technical, factual | Engineers, physicists, HPC reviewers, NR specialists, technical recruiters | The actual portfolio: GRANITE-NR, VORTEX, the Astrophysics Suite, SDSS Cosmic IB, LOITER-SIM, OADF — with benchmarks, limitations, and honest roadmaps |
| **[THEORIES.md](docs/THEORIES.md)** | ~3,400 words | Structured, epistemically careful | Information theorists, cosmologists, complex systems researchers, SETI theorists, philosophers of mind | FCT/UIBIC, CFD, CAT, COE-F — speculative theoretical frameworks with explicit status markers and per-framework limitations |
| **[VISION.md](docs/VISION.md)** | ~6,300 words | Personal, philosophical, direct | Anyone who wants the human context — why any of this exists, what I think is at stake, what I am actually trying to say | The motivation behind the work: complexity, the Kardashev transition, the Great Filter, what truth means to me |
| **[COLLABORATE.md](docs/COLLABORATE.md)** | ~2,100 words | Operational, specific | Domain experts who can help with something concrete — running a benchmark, reviewing code, critiquing a theory, identifying prior literature | Per-project specific asks, response time expectations, how to reach me, what useful contribution looks like |

Each document serves a different purpose and should be evaluated by the standard appropriate to its category.

---

## Recommended first read

For most readers — engineers, physicists, technical reviewers, anyone making a first-pass judgment about whether this portfolio is worth taking seriously — start with:

### **[RESEARCH.md](docs/RESEARCH.md)**

This is the right entry point because it lets you evaluate the work as engineering before anything else. It opens with universal disclaimers (solo developer, no institutional affiliation, no funding, no external code review — applying to everything below). It then goes through each of the six projects with the same structure: what it is, current validated state, comprehensive known limitations, honest roadmap.

If you read only `RESEARCH.md` and walk away, you will have an accurate picture of what has actually been built and what hasn't. That is, I think, the most important thing for a reader to come away with.

After `RESEARCH.md`, choose your next document based on what you actually care about — see the audience-specific paths below.

---

## Audience-specific reading paths

These paths assume you have already read `RESEARCH.md`, or that you are going to. They tell you what to read next based on your domain.

### If you are a numerical relativity / GRMHD researcher

1. **[RESEARCH.md](docs/RESEARCH.md)** — focus on Section 1 (Astrophysics Suite — the analytical work behind GRANITE-NR) and Section 2 (GRANITE-NR itself, including the comprehensive limitations table).
2. **GRANITE-NR repository** directly — look at `tests/`, `src/ccz4/`, `src/grmhd/`, `src/amr/`. The 107 GoogleTest unit tests across 20 suites are where the implementation claims can be verified.
3. **[COLLABORATE.md](docs/COLLABORATE.md)** Section "GRANITE-NR" — specific tasks where outside expertise would matter, including the lapse stabilization anomaly and the convergence ordering issue.
4. Skip `THEORIES.md` unless you are also interested in the speculative consciousness framework. The engineering does not depend on it.

### If you are an astrophysicist or general physicist

1. **[RESEARCH.md](docs/RESEARCH.md)** in full — the six projects span numerical relativity, post-Newtonian dynamics, observational cosmology, atmospheric thermodynamics, and architectural specification work.
2. Treat each project by its maturity level: GRANITE-NR is active code, VORTEX is stable, SDSS is functional, OADF is a working paper, LOITER-SIM is spec only, the Astrophysics Suite is a closed archive.
3. **[THEORIES.md](docs/THEORIES.md)** — only after separating validated physics from speculative frameworks. The SDSS pipeline tests a prediction from FCT; the prediction is unconfirmed.
4. **[COLLABORATE.md](docs/COLLABORATE.md)** — for anything you can specifically help with.

### If you are an information theorist or work on consciousness

1. **[THEORIES.md](docs/THEORIES.md)** Section 1 — Fractal Cosmopsychism Theory (FCT/UIBIC). This is the framework that applies Information Bottleneck theory to consciousness across scales. Read the limitations table carefully — the galactic extension is the most fragile component.
2. **[RESEARCH.md](docs/RESEARCH.md)** Section 5 — the SDSS Cosmic IB analysis pipeline that empirically tests FCT. The measured η_IB ≈ 0.0045 vs predicted ≈ 0.42 is a ~93× gap that is not yet explained.
3. **[COLLABORATE.md](docs/COLLABORATE.md)** — the FCT-specific asks. The most useful contribution would be diagnosing whether the empirical gap is methodological or theoretical.

### If you work on SETI / Fermi Paradox / complex systems

1. **[THEORIES.md](docs/THEORIES.md)** Sections 2–4 — CFD (Coupled Functional Differentiation), CAT (Civilization Asynchrony Theory), and the Chrono-Optical-Eusocial Fermi Model.
2. Treat them as structured speculative arguments, not as validated models. Each section has a per-framework limitations table.
3. **[COLLABORATE.md](docs/COLLABORATE.md)** Theoretical Contributions section — the highest-value contribution here would be pointing me to existing literature that already formalizes mechanisms I claim are original.

### If you are a software engineer or technical reviewer

1. **[RESEARCH.md](docs/RESEARCH.md)** — focus on the engineering hygiene: test coverage, build systems, CI behavior, repository structure, documentation, reproducibility claims.
2. Identify which repositories are implemented (GRANITE-NR, VORTEX, SDSS pipeline) versus specification-stage (LOITER-SIM).
3. **[COLLABORATE.md](docs/COLLABORATE.md)** — for concrete contribution targets across all projects. You do not need to engage with theoretical material to evaluate engineering quality.

### If you are a philosopher, theorist, or thoughtful generalist

1. **[VISION.md](docs/VISION.md)** — this is the only document that addresses the broader picture: why this work exists, what I think is at stake, the Kardashev transition, the Great Filter, the structure of truth and self-deception.
2. **[THEORIES.md](docs/THEORIES.md)** — for the formal frameworks that try to put structure on some of what `VISION.md` discusses informally.
3. **[RESEARCH.md](docs/RESEARCH.md)** — if you want to see what the philosophical motivation translates into in terms of concrete artifacts.

### If you are a potential collaborator

1. **[RESEARCH.md](docs/RESEARCH.md)** — to understand the actual scope and current state of the portfolio.
2. **[COLLABORATE.md](docs/COLLABORATE.md)** — to identify where your expertise would matter. The per-project lists are specific.
3. Reach out with one concrete target rather than a general offer of help. Specific asks get specific responses; general ones get general ones.

### If you are a general reader without a specific technical background

1. **[VISION.md](docs/VISION.md)** — the human context behind everything.
2. **[RESEARCH.md](docs/RESEARCH.md)** — for an honest picture of what is actually built.
3. **[THEORIES.md](docs/THEORIES.md)** — only if you are comfortable with material that is explicitly labeled as speculative. The status markers (🔴 Speculative, 🟡 Tested-Unresolved, 🟢 Grounded) tell you exactly how to read each framework.

---

## The epistemic scale used throughout the portfolio

`THEORIES.md` uses a consistent three-level status marker on every theoretical framework. The same scale is implicitly used in `RESEARCH.md` for projects with unresolved results:

| Status | Meaning |
|---|---|
| 🔴 **Speculative** | Internally consistent framework; no empirical validation; predictions not yet testable by me |
| 🟡 **Tested — Unresolved** | Empirical test attempted; result does not confirm the theory; open question |
| 🟢 **Grounded** | Built on peer-reviewed literature; the critique is about the synthesis, not the components |

Nothing in `THEORIES.md` is marked as "established science." Nothing in `RESEARCH.md` claims peer-review status it does not have.

---

## The boundary between engineering and speculation

The engineering projects (GRANITE-NR, VORTEX, SDSS pipeline, OADF) can be evaluated by their own standards — test coverage, convergence benchmarks, code quality, reproducibility — without reference to the theoretical frameworks. A C++17 numerical relativity engine with 107 unit tests is not made more or less valid by the existence of a speculative consciousness theory in the same portfolio.

The reverse also holds. The theoretical frameworks should be evaluated by standards appropriate to theory: mathematical consistency, literature placement, falsifiability, empirical strategy.

> **Evaluate each artifact by the correct standard for its category.**

---

## Minimal reading order

For readers who want one clean path:

1. **This guide.** You are reading it.
2. **[RESEARCH.md](docs/RESEARCH.md)** — what exists, what is implemented, what is incomplete, what the limitations are.
3. **[COLLABORATE.md](docs/COLLABORATE.md)** — what needs review, correction, testing, or contribution.
4. **[THEORIES.md](docs/THEORIES.md)** — speculative frameworks, status-labeled and limitation-disclosed.
5. **[VISION.md](docs/VISION.md)** — personal motivation and the broader picture.

This order is deliberate. It puts concrete artifacts before speculative interpretation, and operational specifics before motivational context.

If you only have time for one document after this guide, make it `RESEARCH.md`. Everything else can be deferred or skipped.

---

This portfolio is intentionally open before it is perfect. Some parts are mature, some are incomplete, some are speculative, and some are probably wrong in ways I cannot yet see. The goal is not to look finished — the goal is to make the work inspectable, correctable, and useful.

---

*Liran M. Schwartz*  
[`scliran9@gmail.com`](mailto:scliran9@gmail.com) · [ORCID 0009-0008-8035-1308](https://orcid.org/0009-0008-8035-1308) · [@LiranOG](https://github.com/LiranOG) · May 2026
