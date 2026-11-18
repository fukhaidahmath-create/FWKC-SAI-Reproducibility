# FWKC–SAI V42 | Reproducibility repository candidate

**Author review first.** Manuscript and supplement are in `Manuscript/`, exact historical archived outputs in `Original_Results/`, and new endpoint data/diagnostics in `Endpoint_Evidence/`. No participant-level clinical workbook is included. Original archived outputs and execution logs must be reviewed for identifiers, sensitive paths and licensing before public release. See `LICENSE_PENDING.md`. This is not an accepted paper or an actual GitHub/Zenodo deposit.

## Run
Use Python 3.13.5 (reference environment) and install the pinned dependencies:

```sh
python -m venv .venv
# Activate the environment as appropriate for your OS.
python -m pip install -r requirements.txt
python Code/run_v42.py --mode endpoints --out New_Endpoints
python Code/run_v42.py --mode audit --out New_Audit
python Code/run_v42.py --mode full-python --out New_Complete_Python
```
The endpoints mode reconstructs all 90 reference curves, derives endpoint support and clinical statistics from the aggregate counts, regenerates 6,000 V39 evaluation score streams, checks the archived full-grid statistic, and compares the seven endpoint CSV exports before generating S10/S11 in three formats. It is not a new independent validation simulation. Audit mode adds the historical summary/workbook checks and existing mathematical tests. Full-python mode additionally reruns the independent and V39 Monte Carlo studies. The individual earlier stages were executed in V41 Revised; the overall integrated V42 full-python orchestration has not been rerun as one command. Optional `--clinical <authorized-local-workbook>` applies only to the prior audit stages. Historical v102 and original EXTENDED R simulations are not rerun by this driver; original matching input and R environment remain required. No historical estimator performance at C=0 or C=1 is inferred. Archived ADEMP defective summaries are retained as provenance, not validated result inputs.

## RStudio figures
Open RStudio and use `source(file.choose(), encoding="UTF-8")`, selecting `Code/FWKC_V42_ALL_25_FIGURES_RSTUDIO.R.txt`. It embeds the original figure data and endpoint additions; it is designed to export 14 main and 11 supporting figures in TIFF (800 dpi), vector PDF and review PNG, with data and provenance. Alternatively use `--r-figures` with the Python driver and Rscript on PATH. R rendering is untested in the present environment, and does not rerun the simulation. No claim of pixel identity with Python exports.

## Evidence and methods
`Evidence/` contains prior execution audits, aligned cells, V39 archives and editorial checks. `Endpoint_Evidence/` contains 495 reconstructed reference P-C cells (90 new endpoint cells), 540 complete-observation iid support benchmarks, 90,000 method-weight records and 90 summaries from the same V39 evaluation streams. Clinical values use six verified aggregate cells per subset, with independent-participant working covariance; source selection provenance remains unresolved. The nonlinear optimizer remains exploratory; no global certificate or universal finite-sample validity. `Math_Source/` contains editable OMML inventory, equation sources and a conversion guide; native MathType was unavailable.

## Release
Review author declarations, repository rights and privacy first. Then create an approved GitHub repository, tag `v42.0.0`, connect it to Zenodo and archive that exact release to obtain a DOI. Use version-specific DOI in the paper. No manuscript submission or public upload has occurred.
