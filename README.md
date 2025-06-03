# Gene Expression Across Parkinson’s Progression

This project explores how gene expression changes with Parkinson’s disease (PD) progression using microarray data from the NCBI GEO dataset GSE49036. Rather than a case-control comparison, it models transcriptomic shifts across Braak stages (Control, BR12, BR34, BR56) in the substantia nigra.

## Rationale

The original study (Lesnick et al., 2007) identified axon guidance genes as PD risk factors. This work builds on that by examining stage-specific expression patterns to surface genes linked to disease progression. Insights from Dijkstra et al. (2015) — showing early immune activation, axonal dysfunction, and endocytic failure — support the idea that subtle, early transcriptomic changes may underlie worsening pathology.

## Dataset

- **GSE49036** – [View on GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE49036)
- **Tissue:** Substantia nigra
- **Platform:** Affymetrix HG-U133 Plus 2.0
- **Samples:** 28 (8 Control, 5 BR12, 7 BR34, 8 BR56)

## Methods

- **Preprocessing:** Loaded matrix, filtered samples, applied Braak stage labels
- **Annotation:** Mapped probe IDs to gene symbols via GPL570 metadata
- **Differential Expression:** One-way ANOVA across Braak stages, with −log₁₀(p) scoring
- **Visualization:** Boxplots and regression lines for key genes

## Getting Started

1. Place data in `/data/`:
   - `GSE49036_series_matrix.txt`
   - `GPL570-55999.txt`
2. Install requirements:
   ```bash
   pip install pandas numpy scipy matplotlib seaborn statsmodels
   ```
3. Run:
   ```bash
   jupyter notebook notebooks/parkinsons_progression_analysis.ipynb
   ```

## Citation

Lesnick TG et al. *A genomic pathway approach to a complex disease: axon guidance and Parkinson disease.* PLoS Genet. 2007;3(6):e98.

## License

MIT License