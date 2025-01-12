# Differential-Gene-Expression-and-Pseudotime-Analysis-of-T-Cell-States: Naive-like, Memory-Precursor-like, and Effector-like Cells 

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


**Insights**: 

- Total differential Expressed genes: 2369
- Upregulated genes: 430
- Downregulated genes: 1939

**Visualizations**: 

- Volcano Plot
  
  <img width="733" alt="image" src="https://github.com/user-attachments/assets/a0258fa4-e7b0-451a-9df4-f8ece5276b50" />

- P-Value Distribution: Displays the frequency of raw p-values.
- MA Plot: Highlights fold changes against mean expression levels.
- Heatmap: Showcases the expression of top upregulated and downregulated genes.
- Additional Analysis:

Enrichment Analysis: Identifies pathways and biological processes associated with DEGs.


