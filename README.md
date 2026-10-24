# Reproducing Isolation Forest (Liu, Ting & Zhou, ICDM 2008)

Reproduction of the paper's main experiment (Table 3: iForest AUC and runtime on 12 datasets, with LOF as baseline), plus the sub-sampling sweep (Figure 6) and the Mulcross swamping/masking example, using scikit-learn.
Claude Opus 5.5 was used for this implementation.
## How to run

```bash
pip install -r requirements.txt
jupyter notebook iforest_reproduction.ipynb
```

Then run all cells (Kernel → Restart & Run All). The datasets are downloaded automatically into `data/` on the first run; Mulcross is generated in the notebook.

## Parameters

iForest: `n_estimators` = 100, `max_samples` (ψ) = 256, `max_features` = 1.0, sampling without replacement, 10 runs with seeds 0–9.
LOF: `n_neighbors` = 10. All runs single-threaded (`n_jobs=1`).
Full list in Section 6 of the notebook.

## Notes

- Runtimes depend on hardware and will differ from the reported ones.
- Mulcross is generated randomly; different numpy/scipy versions can produce a slightly different dataset even with the same seed, so use the versions in `requirements.txt` to reproduce the exact numbers.
