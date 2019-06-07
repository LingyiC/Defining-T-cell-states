# Defining T Cell States Associated with Response to Checkpoint Immunotherapy in Melanoma
## 1. Identify individual markers associated with response and lack of response. 
**Method:** 'Differential expression analysis' part

**Data:** 'GSE120575_Sade_Feldman_melanoma_single_cells_TPM_GEO.txt', Gene expression values of 6,350 CD8+ T cells (cell ID's found in Table S2)

**Truth:** Table S2

**Results:** /Results/pvalueSort.csv

## 2. Survival analysis of TCF7+CD8+ in clinical outcome anti-PD-1 therapy
**Method:** 'Survival analysis' part

**Data:** Table S3, including patients' survival data, patients status and immunofluorescence-generated TCF7+CD8+/TCF7−CD8+ ratios.

**Truth:** Figure. 3H  

**Results:** Kaplan-Meier survival curve for 33 patients treated with anti-PD-1 therapy. Patients were divided into two groups based on TCF7+CD8+/TCF7−CD8+ ratio (n = 16 > 1; n = 17 < 1) from IF.
![alt text](https://i.ibb.co/y67Xzxv/image.png)

## 3. Clustering of cells
### 3.1 Clustering of immune cells 
**Method:** 'Unsupervised clustering of immune cells' parts

**Data:** Using all genes with variance > 6, yielding ∼4000 genes.

**Truth:** Table S1, S2, S4

**Results:**
Determine the optimal number of clusters
- **Step 1** Applied the elbow method

Examined how much of the complexity each cluster captures by applying the elbow method 
Select the solutions that are near plateau (k = 10,..., 15)
![alt text]()

- **Step 2** Performed differentical expression

Performed differentical expression anlysis to search for gene markers that are siginificatly more highly expressed in a specific cluster as compared to all other clusters (excluded solutions with clusters that have too few marker genes (< 20) distinguishing between them and the rest of the cells.)

- **Step 3** Robustness analysis

Finally, we performed a robustness analysis and selected the clustering solution with the highest median robustness score.

### 3.2 Clustering of T cells

**Method:** 'Unsupervised clustering of T cells' parts

**Data:** Using all genes with variance > 6, yielding ∼4000 genes.

**Truth:** Table S1, S2, S4

**Results:**
