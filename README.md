## Differential-Gene-Expression-and-Pseudotime-Analysis-of-T-Cell-States: Naive-like, Memory-Precursor-like, and Effector-like Cells 

## **Aim**

- To identify differentially expressed genes and reconstruct pseudotime trajectories to explore the progression and differentiation of T-cell states, including naive-like, memory-precursor-like, and effector-like subtypes.
---

## **Data Source**
- **Publication**: [PMC6336113](https://pmc.ncbi.nlm.nih.gov/articles/PMC6336113/#S2)  
- **Dataset**: RNA-seq count data from mouse samples, with metadata describing cell type classifications and gene annotations.
---

## **Analysis Workflow**

### **1. Data Preprocessing**

- Raw RNA-seq count data and metadata.
- Filter lowly expressed genes and low-quality cells.
- Normalize gene expression to a fixed total.
- Apply log transformation for variance stabilization.
- Add metadata for cell annotations.

### **2. Dimensionality Reduction and Visualization**
 **1. PCA Visualization**: 
 
 - Principal Component Analysis (PCA) was performed to reduce dimensionality and visualize variance in the dataset.
 - Cells were colored by their simplified cell type (naive-like, memory-precursor-like, and effector-like).

<img width="724" alt="image" src="https://github.com/user-attachments/assets/ede11677-b7ab-4769-a312-c19aeb5e8c6b" />


 **2. UMAP Visualization**: 

- A neighborhood graph was computed, followed by UMAP to visualize clusters in a 2D space.
- UMAP shows well-separated clusters, indicating distinct gene expression profiles for the cell types.

<img width="733" alt="image" src="https://github.com/user-attachments/assets/67ba436b-9d1a-4efa-878b-28586cd23d12" />

**Insights**: 

- The cells are well-separated into three clusters, indicating that the cell types have distinct gene expression profiles.
- Effector-like cells (blue) and Naive-like cells (green) form compact clusters, distinct from other groups.
- Memory precursor-like cells (orange) form a separate cluster but are closer to native-like cells, possibly reflecting a transitional state (between the naive and effector stages)

### **3. Differential Expression Analysis**:


**Naive-like vs. Memory Precursor-like Cells in Simplified T-cell Types**: 

- Total differential Expressed genes: 2369
- Upregulated genes: 430
- Downregulated genes: 1939

**Visualizations**: 

- **Volcano Plot**:
- The volcano plot visualizes the relationship between the log fold change (logFC) and the statistical significance (-log10 of p-value) of genes in the dataset.
- Red dots represent genes that are significant based on the thresholds (pval < 0.05 and |logFC| > 1) and Gray dots represent non-significant genes.
- The distribution suggests a substantial number of genes are either upregulated or downregulated with statistical significance.
- Some genes exhibit extremely large fold changes, suggesting potential biological importance.
  
  <img width="646" alt="image" src="https://github.com/user-attachments/assets/a0258fa4-e7b0-451a-9df4-f8ece5276b50" />

- **P-Value Distribution**:
- Displays the frequency of raw p-values
- A large peak near 1: This indicates many genes have high p-values, meaning they are not significantly differentially expressed.
- A smaller peak or tail near 0: These represent genes with lower p-values, indicating significance. These are the genes driving the differential expression analysis results.

  <img width="646" alt="image" src="https://github.com/user-attachments/assets/c37babd7-d6ec-41f8-a3cd-98a01c4e4b31" />

- **MA Plot**:
- Highlights fold changes against mean expression levels

  <img width="646" alt="image" src="https://github.com/user-attachments/assets/e40fcdea-621d-4f90-90b5-0f4c9699db68" />

- **Heatmap**:
- the expression of top upregulated and downregulated genes.

  <img width="646" alt="image" src="https://github.com/user-attachments/assets/8bdb8273-7b69-4c7a-a921-3588f3d41278" />
  
### **4. Trajectory inference**:

<img width="629" alt="image" src="https://github.com/user-attachments/assets/c69fb5a0-5c57-453c-a96d-8a04c097171c" />


- There is strong connectivity between naive_like and memory_precursor_like clusters (thick edge). Similarly, there is a strong connection between memory_precursor_like and effector_like clusters. The connection between naive_like and effector_like is weak.
- This graph suggests a likely trajectory: Naive-like → Memory-precursor-like → Effector-like.

- The core trajectory is similar in case whole dataset and significant genes.

### **4. Pseudotime Analysis**:

<img width="646" alt="image" src="https://github.com/user-attachments/assets/f86dd13a-9759-4a8b-af55-3421920347d9" />


- Dark purple cells have low pseudotime values (closer to the root and earlier stages of differentiation). Yellow cells have high pseudotime values (later stages of differentiation).

- Pseudotime reflects the gradual differentiation from naive-like cells (root) to memory-precursor and effector-like cells.

- **Pseudotime Results**

| **Run**        | **Pseudotime** |
|----------------|----------------|
| SRR8245064     | 0.274654       |
| SRR8245065     | 0.343095       |
| SRR8245066     | 0.241242       |
| SRR8245067     | 0.287529       |
| SRR8245068     | 0.221455       |
| SRR8245069     | 0.011546       |
| SRR8245070     | 0.000000       |
| SRR8245071     | 0.075624       |
| SRR8245072     | 0.910634       |
| SRR8245073     | 1.000000       |
| SRR8245074     | 0.958594       |
| SRR8245075     | 0.950762       |
| SRR8245076     | 0.908047       |
| SRR8245077     | 0.638296       |

- Runs **SRR8245073** and **SRR8245072** are at the furthest end of the trajectory (`pseudotime ≈ 1`).

- Runs **SRR8245070** and **SRR8245069** are at the beginning of the trajectory (`pseudotime ≈ 0`).





  






