# 🧬 GEO Microarray Disease Classification

A comprehensive bioinformatics workflow for **cancer classification** using GEO microarray datasets (GSE15852). This pipeline performs end-to-end analysis from raw data download to machine learning model evaluation with automated visualization and reproducible results.

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🌟 **Key Features**

### Data Processing
- **Automated GEO dataset download** using `GEOparse` (GSE15852)
- **Intelligent label extraction** from GSM metadata (cancer vs. normal)
- **Probe-to-gene mapping** via GPL96 annotation
- **Gene-level aggregation** (averaging multiple probes per gene)
- **Log transformation** and **StandardScaler normalization**
- **Class balancing** via random oversampling

### Feature Engineering
- **Variance filtering** to remove low-variance genes
- **ANOVA F-test** feature selection (top 500 genes)
- **Dimensionality reduction** with PCA visualization

### Machine Learning Models
- **Random Forest** (400 estimators, max_depth=12)
- **Multi-Layer Perceptron (MLP)** (3-layer: 256→128→64)
- **Support Vector Machine (SVM)** with RBF kernel
- **XGBoost** with optimized hyperparameters
- **10-fold stratified cross-validation**

### Biological Insights
- **Pathway enrichment analysis** using gseapy (KEGG & GO terms)
- **Feature importance ranking** (top genes driving classification)
- **Gene correlation heatmaps**

### Visualization & Reproducibility
- **Automated plot saving** with timestamps to `plots/` directory
- **ROC curves** comparing all models
- **Confusion matrices** for performance analysis
- **PCA scatter plots** for data structure visualization

---

## 📁 **Project Structure**

```
GEO-microarray-disease-classification/
│
├── notebooks/              # Jupyter notebooks
│   └── final_bioinf.ipynb # Main analysis notebook
│
├── plots/                  # Auto-generated visualizations (gitignored)
│   ├── pca/               # PCA scatter plots
│   ├── roc/               # ROC curves
│   ├── confusion/         # Confusion matrices
│   ├── heatmaps/          # Correlation heatmaps
│   └── feature_importance/ # Top gene rankings
│
├── data/                   # Data directory (gitignored)
│   ├── raw/               # Raw downloads 
│   └── processed/         # Processed datasets
│
├── results/                # Model outputs and metrics (gitignored)
│
├── geo_raw/                # GEO dataset cache (gitignored)
│
├── README.md
├── LICENSE
├── requirements.txt        # Python dependencies
└── .gitignore

```

---

## ⚙️ **Installation**

### 1. Clone the repository
```bash
git clone https://github.com/PratyakshMathur/GEO-microarray-disease-classification.git
cd GEO-microarray-disease-classification
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

---

## 🚀 **Usage**

### Quick Start
1. Open the Jupyter notebook:
```bash
cd notebooks
jupyter notebook final_bioinf.ipynb
```

2. Run all cells sequentially (or use "Run All")

3. Generated plots will be saved automatically to `../plots/` with timestamps

### Expected Runtime
- **Dataset download**: 2-5 minutes (cached after first run)
- **Model training**: 5-10 minutes (depends on CPU cores)
- **Total pipeline**: ~15 minutes

---

## 📊 **Results & Performance**

### Model Comparison (Test Set AUC)
| Model | AUC Score | Key Strength |
|-------|-----------|--------------|
| **Random Forest** | ~0.95+ | Feature importance interpretability |
| **XGBoost** | ~0.94+ | Robust to overfitting |
| **MLP Neural Net** | ~0.92+ | Captures non-linear patterns |
| **SVM (RBF)** | ~0.91+ | Effective in high-dimensional space |

### Key Findings
- **Top discriminative genes** identified via Random Forest feature importance
- **Strong separation** between cancer and normal samples in PCA space
- **Pathway enrichment** reveals cancer-related biological processes (KEGG, GO terms)
- **High classification accuracy** across all models (precision/recall > 0.90)

### Visualizations
All plots are automatically saved with timestamps in the `plots/` directory:
- `pca/` - 2D PCA projections showing sample clustering
- `roc/` - ROC curves comparing model performance
- `confusion/` - Confusion matrices for all classifiers
- `heatmaps/` - Gene correlation heatmaps
- `feature_importance/` - Top 20 genes ranked by Random Forest

---

## 🧪 **Dataset Information**

### GSE15852
- **Platform**: GPL96 (Affymetrix Human Genome U133A Array)
- **Samples**: Cancer and normal tissue samples
- **Probes**: ~22,000 → ~12,000 unique genes after filtering
- **Classes**: Binary (cancer vs. normal)

---

## 🔬 **Methodology Highlights**

1. **Probe-to-Gene Mapping**: Multiple probes per gene are averaged
2. **Feature Selection**: Variance threshold + ANOVA F-test (top 500 genes)
3. **Class Balancing**: Random oversampling to handle imbalanced data
4. **Validation**: 10-fold stratified cross-validation + 75/25 train-test split
5. **Biological Validation**: Pathway enrichment analysis (Enrichr API)

---

## 📦 **Dependencies**

Core libraries (see `requirements.txt` for full list):
- **Data Processing**: `pandas`, `numpy`
- **Bioinformatics**: `GEOparse`, `gseapy`
- **Machine Learning**: `scikit-learn`, `xgboost`
- **Visualization**: `matplotlib`, `seaborn`

---

## 📝 **Citation**

If you use this pipeline in your research, please cite the original GEO dataset:

```
GSE15852: [Dataset Title from GEO]
Platform: GPL96 (Affymetrix HG-U133A)
```

---

## 🤝 **Contributing**

Contributions are welcome! Please feel free to:
- Report bugs or issues
- Suggest new features or models
- Improve documentation
- Add support for additional GEO datasets

---

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 **Acknowledgments**

- **NCBI GEO** for providing public microarray datasets
- **scikit-learn** community for ML tools
- **Enrichr API** for pathway enrichment analysis

---

## 📧 **Contact**

For questions or collaborations:
- GitHub: [@PratyakshMathur](https://github.com/PratyakshMathur)
- Repository: [GEO-microarray-disease-classification](https://github.com/PratyakshMathur/GEO-microarray-disease-classification)


