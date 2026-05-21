# Collaboration

**How to contribute. What I need. What you can expect from me.**

---

## Who this document is for

This document is for people who have seen the work and want to engage with it. If you are still exploring, [PORTFOLIO_READING_GUIDE.md](./PORTFOLIO_READING_GUIDE.md) is a better starting point.


---

## What I actually need

I am looking for people who can do something specific, where the specifics depend on what you know.

### Engineering contributions

**GRANITE-NR**

- Run the existing benchmarks (single puncture, BBH inspiral) on hardware I do not have access to — cluster, HPC, multi-GPU. The constraint norms, the wall times, and the convergence behavior at higher resolutions are data I genuinely cannot produce alone.
- Review the CCZ4 or GRMHD implementation against the literature and tell me what is wrong. The implementation is mine alone; a trained NR specialist will catch things I cannot.
- Find any of the 107 unit tests that pass but should not — cases where the test is correct but the physics it is testing is subtly wrong. Solo-developer test suites have systematic blind spots.
- Implement or review the AMR reflux correction (the known stub in `src/amr/`). This is the highest-impact accuracy improvement available right now.
- Suggest or implement initial data configurations corresponding to specific entries in the SXS BBH catalog, so that GRANITE-NR's eventual merger outputs can be directly compared.
- Investigate the lapse stabilization at ~0.93 instead of the expected trumpet value ~0.3. This is a real open issue and a fresh perspective on the gauge condition setup would be useful.
- Investigate the anomalous resolution convergence ordering observed in some scans. Either I have set up the convergence test incorrectly, or there is a subtle issue in the AMR refinement criteria — and I cannot easily distinguish between these alone.

**VORTEX**

- Implement the missing 2PN conservative correction term. This is documented as the single most important gap in the post-Newtonian expansion.
- Implement higher-order PN terms (3PN, 3.5PN, 4PN, 4.5PN) for near-merger accuracy.
- Implement EOB resummation for extending PN into the strong-field regime.
- Add tidal deformability for NS-NS and NS-BH scenarios.
- Add QNM ringdown after merger.
- Validate against established N-body codes (rebound, NBODY7) on canonical test problems. VORTEX's Hermite integrator is verified against the analytical references I used, but external cross-validation is missing.
- Add an automated regression test suite that asserts specific physical observables (e.g., GW150914 chirp frequency within X% of observed) rather than relying on visual inspection.

**SDSS Cosmic IB Analysis**

- Review the Information Bottleneck estimator methodology. The 93× gap between measured and predicted η_IB is most likely partly methodological, and I cannot identify the methodological issue alone.
- Suggest a better proxy for "cosmic compression" in the IB framework. The current proxy was chosen heuristically.
- Run the pipeline on other survey data — DES, DESI, Euclid. A measurement that depends on the survey is not yet a robust measurement.
- Replace the photometric inputs with spectroscopic where possible, to get cleaner T-Web classification.
- Test the TDA persistent homology stage for stability under noise and sampling perturbations.

**LOITER-SIM**

- Review the architecture specification for correctness and completeness before implementation begins. This is the highest-value contribution right now — once code starts being written, design errors compound rapidly.
- Point me to existing C-UAS simulation frameworks I should be aware of and possibly build on.
- Critique the sensor modeling assumptions. The current spec assumes idealized noise models that may not match real-world EO/IR/RF sensor performance.
- Comment on the civilian-vs-operational boundary. The project is explicitly simulation-only, but the line requires thoughtful articulation that has not yet been formally addressed.

**OADF**

- Read the working paper and tell me what is wrong with the derivation.
- Suggest where actual experimental measurements could be made to test the closed-form supersaturation prediction.
- Identify any of the 30 cited sources where my citation overstates what the source actually says.

### Theoretical contributions

**FCT / UIBIC**

- Point me to existing literature on Information Bottleneck at macroscopic (non-neural) scales. If serious work has been done on this and I have not found it, the prediction methodology should be revised.
- Identify which of my 13 formal equations are already established results vs. genuinely novel claims. I have tried to map this myself; an external check would be more reliable.
- Critique the leap from "this system performs IB compression" to "this system has consciousness." Even if the math is right, the interpretation may not follow.
- Tell me whether the ~93× empirical discrepancy is more likely methodological or theoretical. This is the central unresolved question.

**CFD**

- Point to existing complex systems or computational social science literature that formalizes similar mechanisms (Tainter, Diamond, Holland, Kauffman, network resilience theory, etc.). I have not done this mapping rigorously and the framework may be largely a restatement of existing work.
- Identify specific historical case studies where CFD's qualitative predictions hold or fail.
- Tell me whether the framework, as published, says anything specific enough to be useful, or whether it is "language without claims."

**CAT**

- Point me to literature on the "Asynchronous Bottleneck" mechanism. I have not found it formalized elsewhere but I may have missed relevant work.
- Critique the broadcasting-window timescale, which the framework asserts rather than derives.
- Identify the anthropic assumptions baked into CAT that may not generalize to civilizations evolving along non-human trajectories.

**COE-F (Three-Layer Fermi Model)**

- Critique the formal coupling between the three layers — the model claims they compound but does not derive the compounding.
- Tell me whether Layer 3's symmetric formulation (the Eusocial Paradox applied to us, not just to them) is genuinely original. If it is in Freitas, Stephenson, Webb, or others I have not seen, please point to the reference.
- Critique the use of "eusocial" — a term with specific biological meaning — for civilizational integration. The choice may be misleading.

---

## What you can expect from me

**Response time during active development:** I read everything. Issues, emails, PRs typically receive a response within 24 hours.

**Response time during the May–August 2026 hiatus:** Slower. Things still get read. Things still get answered. The delay may be days to weeks rather than hours. Active development resumes on return.

**Engagement quality:** I will engage with specific technical or theoretical critique at the same level of depth it is offered. If you write me a paragraph explaining a specific flaw, I will write back a paragraph engaging with that specific flaw — not a generic thank-you-for-your-feedback. If you write me a multi-page review, I will read it carefully and respond in proportion.

**Credit:** Any contribution that affects the work will be acknowledged explicitly — in the relevant repository's CONTRIBUTORS section, in commit messages, in any future publication that builds on the contributed work. This is not negotiable. I do not take credit for work I did not do, and I will not let credit-stripping happen to anyone who helps me.

**Honesty about my limits:** If I do not know something, I will say so. If I think you are wrong, I will say that too. I value directness over comfort — I would rather have a frank exchange that ends with both of us understanding more than a polite one that ends with neither of us moving.

**No NDAs, no contracts, no surrender of intellectual property rights:** Most of the work in the repositories is open-source — typically GPL-3.0 for source code, CC BY-SA 4.0 for academic content where applicable. Contributions are made under those licenses. I do not require contributors to sign agreements or surrender intellectual property rights. The only thing I ask is that contributions be made in good faith and that you stand behind them with your name.

---

## What contribution looks like in practice

There is no minimum. There is no gatekeeping. There is no "small enough not to matter."

- You run `B2_eq` on your cluster and send me the constraint norms. That is a contribution.
- You read the GRMHD implementation and find one line where the sign is wrong. That is a contribution — possibly the most valuable kind.
- You open an issue saying "your IB estimator is using the wrong mutual information bound for this data structure, because of X." That is a contribution.
- You share any of this with a colleague who knows more than you do about the relevant area. That is a contribution.
- You tell me "the Layer 3 argument in COE-F is already in Freitas (1983), here is the reference." That is a major contribution — it would let me retire a novelty claim that should not have been made.
- You file a typo correction in the documentation. That is a contribution.

The modules are deliberately decoupled. You do not need to understand GRANITE-NR to critique FCT. You do not need to care about the Fermi Paradox to contribute to VORTEX. You do not need to know my entire portfolio to contribute to any one piece of it. Engage with what you know.

---

## How to reach me

**For technical contributions on a specific project:** Open an issue in the relevant repository. Use the issue templates if they exist. If they do not, just write what is wrong and how you found it. Even if you are not sure it is the right place, open the issue — I will find it.

**For broader theoretical questions, framework critique, or open-ended discussion:** GitHub Discussions on any of the repositories. All of them have Discussions enabled.

**For private matters — unpublished work, partnership discussions, things that do not fit a public forum:** `scliran9@gmail.com`.

**For formal citation:** [ORCID 0009-0008-8035-1308](https://orcid.org/0009-0008-8035-1308). The GRANITE-NR has a Zenodo DOI: [10.5281/zenodo.19502264](https://doi.org/10.5281/zenodo.19502264). Other projects can be cited by repository URL.

---

## A note on scale

This is a solo project. There is no team, no institution, no filter between you and me. If you write, I am the one who reads it and responds — typically within 24 hours during active development. Response times are slower during May–August 2026 as development is paused.

The work has real flaws — many documented, some certainly not. The modules are decoupled: you do not need to understand the full portfolio to contribute to any one piece of it. If you see something worth engaging with, the issue tracker is open. So is the email.

---

*Liran M. Schwartz*  
May 2026
