## Objective
- Build a native, physics-based, end-to-end plasma and etching simulator from scratch in a collaborative, modular and transparent way.
- Each component must be explainable by a human without the help of AI. AI is used primarily to speed up development.

## General Instructions
- Clearly define, step by step, how each physics component is solved, including its inputs, outputs, governing equations and numerical methods.
- Each module must have its own Markdown file describing its workflow and methods. A module is defined only in its Markdown file and its corresponding Python file.
- Components may interact with each other; all valid pairwise interactions must be defined.
- Each component must be modular and separately testable on its own (for example, the gas dynamics module should be independently runnable and testable without knowing anything about plasma electrodynamics).

## Physics/Chemistry components
- Gas fluid dynamics
- Plasma fluid dynamics
- Plasma electrodynamics
- Plasma sheath model
- Plasma chemistry
- Etching chemistry
- Etching topography
- Etching particle dynamics

## Numerical components
- Native numerical methods in Python
- HPC/multicore numerical methods in Rust

## Architectural components
- Solver adapter
- Simulation assembler
- Visualization engine

## Module layout (`./iem`)
| Component | Code | Documentation |
|---|---|---|
| Gas fluid dynamics | `gas_fd.py` | `GAS_FD.md` |
| Plasma fluid dynamics | `plasma_fd.py` | `PLASMA_FD.md` |
| Plasma electrodynamics | `plasma_electrodynamics.py` | `PLASMA_ELECTRODYNAMICS.md` |
| Plasma sheath model | `plasma_sheath.py` | `PLASMA_SHEATH.md` |
| Plasma chemistry | `plasma_chemistry.py` | `PLASMA_CHEMISTRY.md` |
| Etching chemistry | `etching_chemistry.py` | `ETCHING_CHEMISTRY.md` |
| Etching topography | `etching_topography.py` | `ETCHING_TOPOGRAPHY.md` |
| Etching particle dynamics | `etching_particle_dynamics.py` | `ETCHING_PARTICLE_DYNAMICS.md` |
| Native numerical methods (Python) | `numerical_methods.py` | `NUMERICAL_METHODS.md` |
| HPC/multicore numerical methods (Rust) | `numerical_methods_hpc.rs` | `NUMERICAL_METHODS_HPC.md` |
| Solver adapter | `solver_adapter.py` | `SOLVER_ADAPTER.md` |
| Simulation assembler | `simulation_assembler.py` | `SIMULATION_ASSEMBLER.md` |
| Visualization engine | `visualization_engine.py` | `VISUALIZATION_ENGINE.md` |
