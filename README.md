# Conditioning of Periapsis-Shift Extraction from Orbit Integrations

### An Accumulated-Phase Estimator and Its Error Scaling

**Author:** Uppala Sri Sai Vithesh  
**Affiliation:** Independent Student Researcher, Andhra Pradesh, India  
**Contact:** uppalasrisaivithesh99@gmail.com  
**Research area:** General Relativity · Computational Physics · Numerical Methods  
**Manuscript date:** 22 November 2026

---

## 1. Project Overview

This project investigates the numerical extraction of relativistic periapsis shift from integrated orbital trajectories.

In numerical orbit calculations, periapsis advance is commonly estimated by identifying successive periapsis events and measuring the angular separation between them. This project studies an alternative approach based on tracking an accumulated orbital phase.

The central objective is to investigate how the accumulated-phase estimator behaves relative to event-based periapsis extraction under different orbital regimes, numerical tolerances, and computational protocols.

The study focuses on the Schwarzschild orbital equation and also examines a cubic extension as a mathematical test family.

**The work is a numerical-method study. It does not propose a new theory of gravity or claim new gravitational physics.**

## 2. Research Objectives

The project investigates:

- The construction of an accumulated-phase estimator for periapsis-shift extraction.
- The relationship between phase evolution and the underlying orbital differential equation.
- Numerical error and conditioning in event-based and phase-based measurements.
- The influence of orbital parameters on estimator performance.
- The effect of different numerical comparison protocols.
- The limitations of phase-based estimation in weak-, intermediate-, and strong-field regimes.

## 3. Mathematical Framework

The Schwarzschild orbital equation considered in this study is

\[
w''+w=1-\epsilon(3+e^2)+3\epsilon w^2.
\]

The variables are defined as follows:

- \(w=p/r\): dimensionless inverse-radius variable.
- \(p\): semi-latus rectum.
- \(r\): Schwarzschild radial coordinate.
- \(e\): orbital eccentricity.
- \(\phi\): azimuthal angle.
- \(\epsilon=M/p\): dimensionless relativistic parameter in geometrized units, \(G=c=1\).
- A prime denotes differentiation with respect to \(\phi\).

The phase variables are defined by

\[
X=\frac{w-1}{e},
\qquad
Y=-\frac{w'}{e}.
\]

The orbital phase is

\[
\theta=\operatorname{atan2}(Y,X),
\]

and the accumulated phase deviation is

\[
\psi=\theta-\phi.
\]

The resulting instantaneous phase-rate expression is

\[
\boxed{
\psi'=
-\epsilon
\frac{(w-1)(3w^2-3-e^2)}
{(w-1)^2+(w')^2}
}
\]

within the stated Schwarzschild orbital model and phase definitions.

The phase-based periapsis-shift estimator is constructed from the accumulated phase deviation, while the event-based estimator uses successive periapsis locations.

**Important mathematical restriction:** The phase-variable construction above assumes nonzero eccentricity and requires the phase angle to remain well-defined. The circular-orbit limit requires separate treatment.

## 4. Main Findings

The numerical experiments compare event-based and phase-based estimators under several computational protocols.

The reported results show that:

- The phase estimator performs particularly well in the weak-field regime.
- Its relative advantage depends on how computational cost and numerical error control are defined.
- Results become more mixed in the intermediate- and strong-field regimes.
- The estimator's performance should not be interpreted as universally superior to event-based extraction.
- A cancellation-free quadrature approach provides an important benchmark and outperforms the tested ODE-based approaches in the Schwarzschild problem.

The cubic test family provides an additional mathematical investigation of phase-based estimation beyond the Schwarzschild equation.

These findings are limited to the tested equations, numerical configurations, and computational setup. They do not establish universal performance across all orbital systems.

## 5. Repository Contents

The repository currently contains the manuscript, its LaTeX source files, and the figures and tables used in the paper.

```text
periapsis-phase-estimator/
│
├── README.md
├── CONTRIBUTING.md
├── REPRODUCIBILITY_STATUS.md
│
└── manuscript/
    │
    ├── Periapsis_Phase_Estimator_Manuscript.pdf
    │
    └── latex-source/
        ├── main.tex
        ├── numbers.tex
        ├── tab_baselines.tex
        ├── tab_cubic.tex
        ├── tab_fits.tex
        ├── tab_hp.tex
        ├── tab_interp.tex
        ├── tab_mercury.tex
        ├── tab_protocol.tex
        ├── tab_smalle.tex
        ├── tab_solvers.tex
        ├── tab_strong.tex
        ├── tab_winrate.tex
        │
        └── figures/
            ├── fig01_mercury_tolerance.pdf
            ├── fig02_same_trajectory.pdf
            ├── fig03_baselines.pdf
            ├── fig04_cubic_family.pdf
            ├── fig05_interpolation_convergence.pdf
            └── fig06_error_scaling.pdf
```

## 6. Building the Manuscript

The manuscript is written in LaTeX.

To compile it, use a LaTeX environment with `latexmk` and the required LaTeX packages installed.

From the repository directory, run:

```bash
cd manuscript/latex-source
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The resulting PDF will be generated in the LaTeX source directory.

The precompiled manuscript PDF is also included in the repository.

## 7. Reproducibility Status

**Current status: Manuscript and LaTeX-source archive.**

This repository is not yet a complete computational reproducibility package.

The current archive does not include:

- The original Python or other computational source code.
- The complete raw numerical datasets in CSV or JSON format.
- Automated numerical test suites.
- Complete figure-generation scripts.
- A dependency lockfile or complete computational environment specification.
- End-to-end instructions for regenerating every numerical result from the original data and code.

These materials should be added when available and verified.

The absence of these files is stated explicitly so that readers can distinguish the manuscript archive from a fully reproducible computational release.

## 8. Scope and Limitations

The current investigation has a defined scope.

It does not establish that the phase estimator is universally more accurate or computationally efficient than event-based methods.

The study is limited by the following considerations:

1. The primary orbital model is the planar Schwarzschild problem.
2. The numerical comparisons cover a finite set of tested configurations.
3. The cubic extension is a mathematical test family, not a demonstrated model of a particular physical spacetime.
4. The study does not establish performance for Kerr spacetime, dissipative systems, nonplanar orbits, or general time-dependent systems.
5. The quadrature benchmark is an important limitation on claims of numerical superiority.
6. Further independent implementations and testing with different numerical software ecosystems would strengthen the results.

These limitations define possible directions for future work.

## 9. Future Work

Potential extensions include:

- Testing the estimator in perturbed and non-integrable orbital systems.
- Investigating non-autonomous orbital equations.
- Extending the analysis to nonplanar orbital motion.
- Testing different numerical solvers and software ecosystems.
- Studying the estimator under additional numerical error-control strategies.
- Comparing phase-based extraction with analytical and quadrature-based benchmarks.
- Releasing the original computational code and datasets for independent verification.

These are proposed research directions, not completed results.

## 10. Research and Publication Status

This repository contains a research manuscript prepared for scientific dissemination.

**Publication status:** Manuscript preparation / preprint stage.

- No journal acceptance is claimed.
- No peer-review certification is claimed.
- No arXiv identifier is claimed.
- The numerical findings should be interpreted within the stated scope and limitations.

The project is intended to support transparent scientific discussion, independent examination, and further numerical investigation.

## 11. Author Contributions and Acknowledgment

**Author:** Uppala Sri Sai Vithesh

The author reports contributions to the research idea and design, mathematical derivations, numerical experiments, analysis and interpretation, and manuscript writing and revision.

AI tools were used during parts of the research and writing process. The author is responsible for checking the mathematical derivations, numerical results, interpretation, and final manuscript. Further independent verification and reproducibility work remain important.

## 12. Licensing and Reuse

No blanket licence is assigned to the entire repository at this stage.

The manuscript and software should be treated separately when considering licensing.

Please contact the author before assuming that the manuscript, figures, or other research materials are available for unrestricted reuse.

## 13. Contact

For scientific questions, technical feedback, suggestions, or discussion:

**Uppala Sri Sai Vithesh**  
Independent Student Researcher  
Andhra Pradesh, India

**Email:** uppalasrisaivitheshu99@gmail.com

---

*This repository is intended to document the research, make its mathematical framework accessible, and provide a foundation for further independent investigation.*
