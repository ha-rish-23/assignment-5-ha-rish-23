# Assignment-5 DAL (DA5401)

| Field           | Detail                  |
|-----------------|--------------------------|
| Name            | Harish B                |
| Roll Number     | DA24S024              |
| Course          | DA5401 – Data Analytics Lab|
| Assignment      | 5                       |

## Visualizing Data Veracity Challenges in Multi-Label Classification

## 📁 Folder Structure

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

## 📝 Overview

This assignment explores **data veracity challenges in multi-label classification** using the yeast protein dataset. The project focuses on visualizing high-dimensional gene expression data through advanced dimensionality reduction techniques and analyzing the challenges these data characteristics pose for classification algorithms.

### Key Components:

1. **Data Preprocessing & Scaling**: Feature standardization and statistical analysis
2. **t-SNE Analysis**: Exploring different perplexity values (5-50) and their impact on visualization
3. **Veracity Inspection**: Identifying noisy labels, outliers, and hard-to-learn samples
4. **Isomap Implementation**: Global structure preservation and manifold analysis
5. **Comparative Analysis**: t-SNE vs Isomap for revealing data structure and classification challenges

---

## 🧬 Dataset Information

**Yeast Multi-Label Classification Dataset:**
- **Samples**: 2,417 protein instances
- **Features**: 103 gene expression attributes (Att1-Att103)
- **Labels**: 14 functional classes (Class1-Class14)
- **Challenge**: Multi-label classification where proteins can belong to multiple functional categories

---

## � Technical Implementation

### Part A: Data Preprocessing
- **Feature Scaling**: StandardScaler to normalize all 103 features (mean=0, std=1)
- **Label Analysis**: Identification of single-label vs multi-label combinations
- **Visualization Setup**: Color-coded categories for consistent visual analysis

### Part B: t-SNE Analysis & Veracity Inspection
- **Perplexity Exploration**: Systematic testing of 9 different perplexity values (5, 10, 15, 20, 25, 30, 35, 40, 50)
- **3x3 Grid Visualization**: Comprehensive comparison of perplexity effects
- **KL Divergence Analysis**: Quantitative evaluation of embedding quality
- **Veracity Challenges**:
  - **Noisy/Ambiguous Labels**: Samples with similar features but different labels
  - **Outliers**: Isolated points representing rare or unique patterns
  - **Hard-to-Learn Samples**: Overlapping regions with mixed categories

### Part C: Isomap & Manifold Learning
- **Global Structure Preservation**: Geodesic distance-based dimensionality reduction
- **Neighborhood Analysis**: n_neighbors=3 based on logarithmic rule (log(2417) ≈ 3.4)
- **Manifold Curvature Assessment**: Analysis of reconstruction error and complexity
- **Comparative Evaluation**: Direct comparison with t-SNE for structure revelation

---

## 📊 Key Visualizations

### 1. Feature Scaling Comparison
- **Before/After Scaling**: Statistical comparison showing mean centering and variance normalization
- **Purpose**: Demonstrates the importance of scaling for distance-based algorithms

### 2. t-SNE Perplexity Grid (3x3)
- **9 Different Perplexity Values**: Visual comparison of local vs global structure emphasis
- **KL Divergence Rankings**: Quantitative quality assessment
- **Best Performance**: Perplexity=50 achieving optimal balance

### 3. Final t-SNE Visualization
- **Color-Coded Categories**: Clear distinction between single-label, multi-label, and other combinations
- **Veracity Analysis**: Visual identification of problematic regions for classification

### 4. Isomap Visualization
- **Global Structure Focus**: Preservation of overall data topology
- **Manifold Representation**: Continuous distribution revealing data complexity

### 5. Side-by-Side Comparison
- **t-SNE vs Isomap**: Direct comparison highlighting different structure preservation approaches
- **Analysis**: Detailed discussion of clustering behavior and interpretability

---

## 🔍 Key Insights & Findings

### Data Veracity Challenges Identified:

1. **High Label Ambiguity**: 
   - Mixed categories in central regions indicate inherent classification difficulty
   - Similar gene expression patterns leading to different functional annotations

2. **Complex Manifold Structure**:
   - High reconstruction error (0.4-0.6) suggests complex, non-linear data manifold
   - Non-convex structure with multiple "folds" requiring sophisticated classification approaches

3. **Global vs Local Structure Trade-offs**:
   - **t-SNE**: Superior for cluster identification and local pattern discovery
   - **Isomap**: Better for understanding overall data topology and global relationships

### Classification Implications:

- **Ensemble Methods Recommended**: Complex manifold structure suggests need for sophisticated algorithms
- **Feature Engineering Critical**: Non-linear relationships require careful feature transformation
- **Global Structure Awareness**: Understanding manifold geometry important for algorithm selection

---

## 🎯 Technical Achievements

### Dimensionality Reduction Mastery:
- **t-SNE Optimization**: Systematic perplexity tuning with quantitative evaluation
- **Isomap Implementation**: Proper parameter selection based on theoretical principles
- **Comparative Analysis**: Deep understanding of algorithm strengths and limitations

### Data Quality Assessment:
- **Veracity Framework**: Systematic identification of data quality challenges
- **Visual Analytics**: Effective use of color coding and layout for pattern recognition
- **Quantitative Metrics**: KL divergence and reconstruction error analysis

### Biological Insight:
- **Multi-Label Complexity**: Understanding of protein function prediction challenges
- **Gene Expression Analysis**: Interpretation of high-dimensional biological data
- **Functional Annotation**: Insight into computational biology challenges

---

## 🏆 Conclusions

### Best Practices Demonstrated:
1. **Systematic Parameter Exploration**: Comprehensive perplexity analysis for t-SNE
2. **Theoretical Grounding**: n_neighbors selection based on mathematical principles
3. **Multi-Algorithm Comparison**: Understanding complementary strengths of different methods
4. **Domain-Aware Analysis**: Connecting technical findings to biological interpretations

### Recommended Approach for Similar Datasets:
- **Start with Isomap**: For understanding global data structure
- **Use t-SNE**: For detailed cluster analysis and local pattern discovery
- **Consider Ensemble Methods**: For classification on complex, curved manifolds
- **Prioritize Feature Engineering**: For handling non-linear relationships

---

## 🚀 How to Run

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
   - Total runtime: ~10-15 minutes (depending on system specifications)

4. **Output**:
   - Multiple visualizations showing dimensionality reduction results
   - Quantitative analysis of embedding quality
   - Comprehensive veracity assessment report

---

## 📋 Prerequisites

- **Python 3.7+**
- **Required Libraries**: 
  - `pandas` (data manipulation)
  - `scikit-learn` (dimensionality reduction, scaling)
  - `matplotlib` (visualization)
  - `scipy` (ARFF file loading)
  - `numpy` (numerical operations)
- **Environment**: Jupyter Notebook or VS Code with Python extension
- **Memory**: ~4GB RAM recommended for large-scale t-SNE computations

---

## 🎓 Learning Outcomes

This assignment demonstrates proficiency in:

- **Advanced Dimensionality Reduction**: t-SNE and Isomap implementation and optimization
- **Data Quality Assessment**: Systematic veracity analysis and visualization
- **Multi-Label Classification**: Understanding challenges in complex label structures
- **Comparative Analysis**: Strengths and limitations of different visualization techniques
- **Biological Data Analysis**: Application to real-world protein function prediction
- **Technical Communication**: Clear documentation and result interpretation