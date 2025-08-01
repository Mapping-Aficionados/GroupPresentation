# Methodology for Semantic Clustering of Visual Pattern Annotations

This project analyzes a dataset of subjective text annotations for patterns found in images. The goal is to move beyond simple keyword counting and use Natural Language Processing (NLP) to uncover the underlying semantic themes in the descriptions. The analysis pipeline groups the annotations into meaningful categories and visualizes the results in an interactive 3D space.

## Methodology

The workflow was conducted in a series of distinct steps to transform raw text into an insightful, categorized dataset.

### 1. Semantic Vectorization (From Text to Meaning)

To understand the meaning of the annotations, each phrase was converted into a 384-dimensional numerical vector using a **Sentence-BERT** model (`all-MiniLM-L6-v2`). This transformer-based model captures the contextual meaning of an entire phrase, allowing us to group annotations by their actual intent, not just shared words.

### 2. Unsupervised Clustering (Finding the Groups)

With all annotations represented as points in a high-dimensional space, we used the **K-Means clustering algorithm** to identify natural groupings. After an iterative process, we found that partitioning the data into **8 clusters** yielded the most coherent and meaningful results.

### 3. Interpreting and Naming the Clusters

The K-Means algorithm produces numerical labels (1-8), which require human interpretation. We used a three-pronged, evidence-based approach to assign a descriptive name to each cluster:

*   **Centroid Analysis:** We found the single, real annotation closest to the mathematical center of each cluster. This "Most Representative Annotation" (e.g., `"whale"` for the aquatic group) served as a strong indicator of the cluster's core theme.
*   **Keyword Extraction:** The TF-IDF algorithm was used to automatically identify the most statistically significant keywords for each group.
*   **Manual Review:** Finally, we reviewed a diverse sample of annotations from each cluster to confirm its thematic consistency.

### 4. Summarizing Themes per Image

To understand the primary themes for each image, we grouped all of its annotations by their assigned category. This allowed us to calculate the **Dominant Category** for each image—the theme that was most frequently identified by the annotators. A ranked list of the top three categories was also generated to capture any thematic ambiguity.

## Visualization

It is impossible to visualize data in 384 dimensions. To create a meaningful plot, we used **t-SNE (t-Distributed Stochastic Neighbor Embedding)** to reduce the data to a 3-dimensional "map." t-SNE is an algorithm that excels at preserving the local neighborhood structure, meaning annotations that are semantically similar in the high-dimensional space remain close together in the 3D plot.

The final coordinates were plotted using **Plotly** to create a fully interactive 3D visualization.

## Final Categories

The analysis successfully identified 8 distinct semantic categories:

1.  **Objects & Symbols**
2.  **Reptiles & Monsters**
3.  **Abstract Patterns & Forms**
4.  **Landscapes & Geography**
5.  **Human Faces & Profiles**
6.  **Cats & Dogs**
7.  **Avian & Aerial**
8.  **Aquatic & Marine**

---

### **View the Interactive 3D Visualization**

You can explore the final categorized data in the interactive 3D plot here:

**[Link to your 3D_cluster_visualization_interactive.html file on GitHub Pages]**
