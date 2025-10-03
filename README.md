# Assignment-5 DAL (DA5401)

| Field           | Detail                  |
|-----------------|--------------------------|
| Name            | Harish B                |
| Roll Number     | DA24S024              |
| Course          | DA5401 – Data Analytics Lab|
| Assignment      | 5                       |

## Visualizing Data Veracity Challenges in Multi-Label Classification

## Folder Structure

```
assignment-5-ha-rish-23/
│
├── dataset/
│   ├── yeast.arff
│   ├── yeast-train.arff
│   └── yeast-test.arff
├── solution.ipynb
├── README.md
```

- `dataset/`: Contains the yeast multi-label classification dataset in ARFF format.
- `solution.ipynb`: Main Jupyter notebook with complete analysis, visualizations, and dimensionality reduction techniques.
- `README.md`: Project overview and documentation.

---

## Overview

This assignment explores **data veracity challenges in multi-label classification** using the yeast protein dataset. The assignment focuses on visualizing high-dimensional gene expression data through advanced dimensionality reduction techniques and analyzing the challenges these data characteristics pose for classification algorithms.

### Key Components:

1. **Data Preprocessing & Scaling**: Feature standardization and statistical analysis
2. **t-SNE Analysis**: Exploring different perplexity values (5-50) and their impact on visualization
3. **Veracity Inspection**: Identifying noisy labels, outliers, and hard-to-learn samples
4. **Isomap Implementation**: Global structure preservation and manifold analysis
5. **Comparative Analysis**: t-SNE vs Isomap for revealing data structure and classification challenges

---

## Dataset Information

**Yeast Multi-Label Classification Dataset:**
- **Samples**: 2,417 instances
- **Features**: 103 gene expression attributes (Att1-Att103)
- **Labels**: 14 functional classes (Class1-Class14)
- **Challenge**: Multi-label classification where proteins can belong to multiple functional categories

---

## Technical Implementation

### Part A: Preprocessing and Initial Setup
- **Data Loading**: Loading yeast dataset from ARFF format (2,417 samples, 103 features, 14 labels)
- **Feature-Label Separation**: Systematic separation of features (Att1-Att103) and labels (Class1-Class14)
- **Label Analysis**: 
  - Identification of single-label vs multi-label combinations
  - Frequency analysis of label combinations
  - Creation of visualization target variable for color-coding
- **Feature Scaling Theory**: Understanding why scaling is crucial for distance-based dimensionality reduction
- **Feature Scaling Implementation**: 
  - StandardScaler application to normalize all 103 features (mean=0, std=1)
  - Statistical comparison showing before/after scaling effects
  - Visual demonstration of scaling importance for distance-based algorithms

### Part B: t-SNE and Veracity Inspection
- **Perplexity Theory**: Mathematical foundation and interpretation of perplexity parameter
- **Systematic t-SNE Analysis**: 
  - Implementation with 9 different perplexity values (5, 10, 15, 20, 25, 30, 35, 40, 50)
  - Optimized computation with duplicate prevention mechanism
  - KL divergence tracking for quality assessment
- **3x3 Grid Visualization**: Comprehensive comparison of perplexity effects on embedding structure
- **Final t-SNE Plot**: Best perplexity selection based on KL divergence minimization
- **Veracity Inspection Analysis**:
  - **Noisy/Ambiguous Labels**: Identification of samples with similar features but different labels
  - **Outliers**: Detection of isolated points representing rare or unique patterns
  - **Hard-to-Learn Samples**: Analysis of overlapping regions with mixed categories

### Part C: Isomap Implementation and Comparative Analysis
- **Isomap Theory**: Understanding global structure preservation vs local structure emphasis
- **Isomap Implementation**:
  - n_neighbors=3 selection based on logarithmic rule (log(2417) ≈ 3.4)
  - Geodesic distance-based dimensionality reduction
  - Reconstruction error analysis for manifold complexity assessment
- **t-SNE vs Isomap Comparison**: Side-by-side visualization and analysis
- **Detailed Theoretical Analysis**:
  - Global structure revelation comparison between methods
  - Manifold curvature assessment and complexity indicators
  - Classification difficulty analysis based on manifold properties
  - Ensemble method recommendations for complex curved manifolds

---

## Key Visualizations

### 1. Feature Scaling Comparison
- **Before/After Scaling**: Scatter plots showing mean centering (0) and variance normalization (1)
- **Purpose**: Demonstrates the importance of scaling for distance-based algorithms

### 2. t-SNE Perplexity Grid (3x3)
- **9 Different Perplexity Values**: Visual comparison of local vs global structure emphasis
- **KL Divergence Rankings**: Quantitative quality assessment for each perplexity
- **Best Performance**: Perplexity=50 achieving lowest KL divergence (≈2.09)

### 3. Final t-SNE Visualization
- **Color-Coded Categories**: Clear distinction between single-label, multi-label, and other combinations
- **Veracity Analysis**: Visual identification of problematic regions for classification
- **Legend**: Red (Other), Blue (Multi-label), Green (Single-label) with sample counts

### 4. Isomap Visualization
- **Global Structure Focus**: Preservation of overall data topology
- **Reconstruction Error**: Quantitative assessment of manifold complexity
- **Continuous Distribution**: Shows underlying data manifold structure

### 5. Side-by-Side Comparison (t-SNE vs Isomap)
- **Clustering Behavior**: t-SNE shows tight clusters, Isomap shows continuous structure
- **Separation Patterns**: Clear boundaries vs gradual transitions
- **Interpretability**: Local pattern discovery vs global topology understanding

---

## Key Insights & Findings

### Data Veracity Challenges Identified:

1. **High Label Ambiguity**: 
   - Mixed categories in central regions indicate inherent classification difficulty
   - Similar gene expression patterns leading to different functional annotations

2. **Complex Manifold Structure**:
   - High reconstruction error (~0.4-0.6) indicates 2D embedding cannot perfectly capture 103D relationships
   - Non-convex structure with multiple "folds" and varying density regions
   - High intrinsic dimensionality requiring sophisticated classification approaches

3. **Global vs Local Structure Trade-offs**:
   - **t-SNE Strengths**: Superior for cluster identification and local pattern discovery
   - **t-SNE Limitations**: May distort global distances and create misleading global arrangements
   - **Isomap Strengths**: Preserves geodesic distances and global topology
   - **Isomap Applications**: Better for understanding overall data manifold structure

4. **Classification Difficulty Indicators**:
   - **High Curvature**: Complex decision boundaries required for non-linear manifolds
   - **Feature Interactions**: Gene expressions interact in complex, non-additive ways
   - **Ensemble Requirements**: Simple linear methods insufficient for curved manifold structures

### Classification Implications:

- **Ensemble Methods Recommended**: Complex manifold structure suggests need for sophisticated algorithms
- **Feature Engineering Critical**: Non-linear relationships require careful feature transformation
- **Global Structure Awareness**: Understanding manifold geometry important for algorithm selection

---

## Conclusions

### Best Practices Demonstrated:
1. **Systematic Parameter Exploration**: Comprehensive perplexity analysis (5-50) with KL divergence evaluation
2. **Theoretical Foundation**: Mathematical understanding of perplexity and logarithmic neighbor selection
3. **Multi-Algorithm Implementation**: Complementary t-SNE and Isomap approaches for different perspectives
4. **Optimization Excellence**: Duplicate computation prevention and efficient parameter sweeping

---

## How to Run

1. **Dataset Setup**: 
   - The yeast dataset files are included in the `dataset/` folder
   - No additional downloads required

2. **Environment Setup**:
   ```bash
   pip install pandas scikit-learn matplotlib scipy
   ```

3. **Execution**:
   - Open `solution.ipynb` in Jupyter Notebook or VS Code
   - Run all cells sequentially to reproduce the complete analysis

4. **Output**:
   - Multiple visualizations showing dimensionality reduction results
   - Quantitative analysis of embedding quality
   - Comprehensive veracity assessment report