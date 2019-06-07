# Replication of results: Defining T Cell States Associated with Response to Checkpoint Immunotherapy in Melanoma
> [Article link](https://www.sciencedirect.com/science/article/pii/S0092867418313941#mmc1)
## 1. Identify individual markers associated with response and lack of response 
**Method:** 'Differential expression analysis' part

**Data:** 'GSE120575_Sade_Feldman_melanoma_single_cells_TPM_GEO.txt', Gene expression values of 6,350 CD8+ T cells (cell ID's found in Table S2)

**Truth:** Table S2

**Results:** 
1. Applied Fisher's Exact test for corresponding table, respose & Non-response (results can be found in '/Results/pvalueSort.csv') 
2. Applied Fisher's Exact test for corresponding table, CD8_B & CD8_G (code can be found in 'Identify_markers.rmd')

head(pvalueSort)

| p_value | mean_exp_in_R | mean_exp_in_NR | per_in_R | per_in_NR | log2_R_NR_ |
| :-------------: |:-------------:| :-----:| :-------------: |:-------------:| :-----:|
| CD38 |	1.968650e-112 |	1.1909712 |	3.4240014 |	0.15226940 |	0.42710997 |	-1.5235448 |
| PRF1 |	7.866785e-96 |	4.4266911 |	7.0580353 |	0.50561249 |	0.76889096 |	-0.6730380 |
| NKG7 |	3.618114e-91 |	7.7752074 |	10.4359219 |	0.70815032 |	0.91141595 |	-0.4246050 |
| IFI6 |	4.182860e-71 |	2.3380918 |	4.3357429 |	0.33723768 |	0.57498256 |	-0.8909476 |
| PSME2 |	2.122274e-70 |	4.2568619 |	6.5887143 |	0.46412884 |	0.69681469 |	-0.6302067 |

## 2. Survival analysis of TCF7+CD8+ in clinical outcome anti-PD-1 therapy
**Method:** 'Survival analysis' part

**Data:** Table S3, including patients' survival data, patients status and immunofluorescence-generated TCF7+CD8+/TCF7−CD8+ ratios.

**Truth:** Figure. 3H  

**Results:** Kaplan-Meier survival curve for 33 patients treated with anti-PD-1 therapy. Patients were divided into two groups based on TCF7+CD8+/TCF7−CD8+ ratio (n = 16 > 1; n = 17 < 1) from IF.
![alt text](https://i.ibb.co/y67Xzxv/image.png)

## 3. Clustering of cells (stopped finding the optimal number of clusters)
### 3.1 Clustering of immune cells 
**Method:** 'Unsupervised clustering of immune cells' parts

**Data:** Using all genes with variance > 6, yielding ∼4000 genes.  /Results/clusterData.csv

**Truth:** Table S1, S2, S4

**Results:**
Determine the optimal number of clusters
- **Step 1** Applied the elbow method

Examined how much of the complexity each cluster captures by applying the elbow method 
Select the solutions that are near plateau (k = 10,..., 15)
![alt text](https://i.ibb.co/nzXN8rB/image.png)

- **Step 2** Performed differentical expression

Performed differentical expression anlysis to search for gene markers that are siginificatly more highly expressed in a specific cluster as compared to all other clusters (excluded solutions with clusters that have too few marker genes (< 20) distinguishing between them and the rest of the cells.)

- **Step 3** Robustness analysis

Finally, we performed a robustness analysis and selected the clustering solution with the highest median robustness score.

### 3.2 Clustering of T cells

**Method:** 'Unsupervised clustering of T cells' parts, same as above 

**Data:**  Gene expression values of 6,350 CD8+ T cells (cell ID's found in Table S2)
