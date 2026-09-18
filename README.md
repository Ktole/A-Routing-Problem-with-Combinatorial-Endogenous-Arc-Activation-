# A-Routing-Problem-with-Combinatorial-Endogenous-Arc-Activation-
A novel Routing Problem
# CEAA-RP reproducibility package

Repository companion for A Routing Problem with Combinatorial Endogenous Arc Activation.

## Included
- Activation-Aware Dominance Search (AADS)
- deterministic CEAA benchmark generator
- factorial synergy-suite generator
- independent expanded-state exact validator
- experiment/statistics scripts
- emergency-access example
- figure generator
- GitHub/Zenodo instructions

## Install
bash
python -m venv .venv
# Windows: .\.venv\Scripts\Activate.ps1
# Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt
```

## Reproduce
bash
python scripts/generate_ceaa_bench.py --output benchmarks/CEAA-Bench-v1.0
python scripts/validate_ceaa_bench.py benchmarks/CEAA-Bench-v1.0
python code/run_experiments.py --bench benchmarks/CEAA-Bench-v1.0 --output results

python code/generate_synergy_suite.py --output benchmarks/CEAA-Synergy-v2
python code/run_strengthened_experiments.py --suite benchmarks/CEAA-Synergy-v2 --output results
python code/run_milp_validation.py --project . --output results
python code/generate_operational_case.py
python code/make_publication_figures.py


Verification requirement: the supplied code implements the manuscript mechanism, but the generated
outputs must be checked against the exact manuscript tables before the repository is cited as reproducing
the published numerical results. Archive the verified release in Zenodo.
