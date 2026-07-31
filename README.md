# Fractional Tail-Event Timing Diagnostics

Replication materials for the manuscript **“Fractional Tail-Event Timing Diagnostics: EVT Severity, Mittag-Leffler Recurrence, and Stress Episodes”**, submitted to *Mathematics*.

Repository: <https://github.com/rolando-rubilar/Extremes>

## Authors

Rolando Rubilar-Torrealba, Karime Chahuán-Jiménez, Hanns de la Fuente-Mella, Martín Galaz, and Joaquín Astorga.

## Repository structure

- `code/analysis_fractional_tail_v16.py`: regenerates all numerical tables.
- `code/make_figures_v16.py`: regenerates the five manuscript figures.
- `data/`: six daily price series and the derived wide and long panels.
- `outputs/`: generated CSV tables and `manifest_v16.json`.
- `environment.yml`: pinned Conda environment.
- `requirements.txt`: pip-compatible dependency list.
- `SHA256SUMS.txt`: integrity hashes for the repository files.

## Reproduction

Using Conda:

```bash
conda env create -f environment.yml
conda activate fractional-tail-v16
python code/analysis_fractional_tail_v16.py --input-dir data --out-dir outputs_check
python code/make_figures_v16.py --input-dir data --table-dir outputs_check --out-dir figs_check
```

A faster diagnostic run is available:

```bash
python code/analysis_fractional_tail_v16.py --input-dir data --out-dir outputs_check --quick
```

The full analysis uses fixed random seeds recorded in `outputs/manifest_v16.json`. The manifest also contains SHA256 hashes of the six input series, the common sample window, and the threshold grid. All numerical tables are generated through a single analysis script; all figures are generated through a separate figure script.

## Compiling the manuscript

From `manuscript/`, run:

```bash
pdflatex fractional_tail_risk_regimes_mdpi_v16.tex
pdflatex fractional_tail_risk_regimes_mdpi_v16.tex
pdflatex fractional_tail_risk_regimes_mdpi_v16.tex
```

The bibliography is embedded in the LaTeX source, so no BibTeX step is required.

## Data provenance

The primary series were assembled from Yahoo Finance's chart API. Stooq and FRED identifiers are retained as fallback references in the manifests. The six files are `Coffee.csv`, `DAX.csv`, `NasdaqDiario.csv`, `Nikkei.csv`, `Platino.csv`, and `SP500.csv`.

## License and data terms

Original code and documentation are released under the MIT License. Third-party market data remain subject to their providers' terms; see `DATA_NOTICE.md`.

## Citation

Citation metadata are provided in `CITATION.cff`. After publication, update the preferred citation with the final DOI, volume, issue, and article number.
