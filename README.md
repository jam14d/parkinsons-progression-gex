# Exploring Gene Expression Dynamics Across Parkinson’s Disease Progression

This project investigates gene expression patterns across stages of Parkinson’s disease (PD) progression using microarray data from the NCBI GEO dataset GSE49036. Rather than treating PD as a binary condition (disease vs. control), this analysis explores which genes show stage-dependent expression changes — a signal of potential involvement in disease progression mechanisms.

## Scientific Rationale

The foundational study for this dataset (Lesnick et al., 2007) identified axon guidance pathway genes as contributors to PD risk and onset using SNP-based pathway modeling. While that work focused on susceptibility, it did not address how gene expression varies across the course of disease progression.

This project takes a complementary approach. By leveraging Braak staging (Control, BR12, BR34, BR56) as a continuous proxy for disease severity, I aim to identify genes whose expression levels correlate with increasing neuropathological burden in the substantia nigra.

This progression-aware perspective may highlight candidate genes or pathways involved not only in the origin of PD but also in its worsening trajectory.

## Data Summary

- **Dataset:** [GSE49036 - NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE49036)
- **Tissue:** Substantia nigra
- **Platform:** Affymetrix HG-U133 Plus 2.0 (GPL570)
- **Samples:** 28 total (8 Control, 5 BR12, 7 BR34, 8 BR56)

## Analysis Workflow

1. **Preprocessing**
   - Loaded gene expression matrix and filtered for sample rows.
   - Manually assigned Braak stage labels to samples.

2. **Gene Annotation**
   - Mapped probe IDs to gene symbols using GPL570 annotation.

3. **Differential Expression**
   - Applied one-way ANOVA across Braak stages for each gene.
   - Computed −log₁₀(p-values) to assess stage-related changes.

4. **Visualization**
   - Boxplots illustrate expression trends for individual genes.
   - Linear regression models capture directional progression signals.


## Running the Analysis

1. Clone this repository and place required files in the `data/` folder:
   - `GSE49036_series_matrix.txt`
   - `GPL570-55999.txt`

2. Install dependencies:
   ```bash
   pip install pandas numpy scipy matplotlib seaborn statsmodels
   ```

3. Run the notebook:
   ```bash
   jupyter notebook notebooks/parkinsons_progression_analysis.ipynb
   ```

## Citation

Lesnick TG, Papapetropoulos S, Mash DC, et al. *A genomic pathway approach to a complex disease: axon guidance and Parkinson disease.* PLoS Genet. 2007;3(6):e98. doi:10.1371/journal.pgen.0030098

## License

This work is provided under the MIT License.