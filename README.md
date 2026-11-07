# HiMCM 2026 — Team 18105

Working repository for **Problem B: Air Conditioning the Environment: Modeling Energy Waste in Public Cooling**.

This is the **planning branch**, `codex/model-planning`. The current authorization is to record plans, decisions and research; the `main` branch and manuscript are unchanged, and this branch is not to be merged yet.

## Start here

- [Progress and decisions](progress.md): agreed scope, evaluation categories, current direction and unresolved choices.
- [Model formulation](model-formulation.md): mathematical definitions, teammate's temperature-equation proposal, path integrals and proposed optimization approach.
- [Original problem](2026_HiMCM_Problem_B.pdf): authoritative requirements.
- [Bus-stop research](bus-stop-cooling-research.md): real-world evidence and limits for our first case.
- [File guide](package-info.md): remaining research and project files.
- [Paper](main.tex): teammate's initial Overleaf import; currently a title and empty Introduction.

## Current direction

Start with the **open-sided bus shelter** and compare the required fan, evaporative cooler and large evaporative cooler. Enclosure changes are set aside for now. Then extend to the semi-open rail waiting area and at least two specific venues differing in climate or technology.

The discussed modeling pipeline is:

**Cooler/outlet configuration + weather + geometry → airflow, temperature and humidity → conditions along people's paths → aggregate benefit and resource use → configuration comparison.**

People are points with positions that change over time; stationary occupants are constant-position paths with arrival and departure times. The temperature advection–diffusion equation proposed by Tianyi is a candidate physical component, not an airflow solver by itself. A simplified additive response model is being considered for candidate selection, followed by checking with a model that accounts for interactions. Neither the weak-interaction assumption nor the physical/comfort model has been validated.

The four agreed evaluation categories are **benefit to people, all financial costs, environmental effects, and nonfinancial practicality**. Reliability affects these outcomes rather than receiving a separate score. Heat safety remains distinct from ordinary comfort.

No final cooler, venue, numerical utility function, weights, solver or optimum has been selected. Proposed equations and research estimates must not be reported as measured results.

## Collaboration

The local HiMCM workspace is a working copy of this repository. Record agreed decisions on this planning branch as work proceeds, check teammate changes before editing, and preserve their manuscript contributions. See [project agent guidance](AGENTS.md). A GitHub update alone does not verify synchronization back into Overleaf.

Research and formulation notes include AI assistance; retain that provenance for the eventual disclosure.
