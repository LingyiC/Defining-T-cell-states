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
### 3.1 immune cells 
**Method:** 'Unsupervised clustering of immune cells' parts

**Data:** gene expression matrix

**Truth:** Table S1, S2, S4

**Results:**

### 3.2 T cells

