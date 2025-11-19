# GEO-microarray-disease-classification


This repository contains a complete bioinformatics workflow for **microarray-based cancer classification** using GEO datasets. The pipeline performs dataset loading, quality control, normalization, probe-to-gene mapping, batch correction, feature selection, and machine-learning model training.


## **📌 Features**

* Automated **GEO dataset download** using `GEOparse`
* **Quality control**:

  * Sample counts
  * Missing labels
  * Probe matrix inspection
  * Class balance checks
* **Platform compatibility analysis**
* **Probe intersection** across datasets
* **Gene-level aggregation** (if needed)
* **Normalization & scaling**
* **Batch correction (ComBat)**
* Dimensionality reduction (**PCA**) for visual QC
* Train/test split & ML training:

  * Random Forest
  * MLP classifier
* Performance metrics & confusion matrix

---

## **📁 Workflow Overview**

1. **Load GEO datasets**
2. **Filter samples** with valid labels
3. **Check platform compatibility**
4. **Intersect common probes**
5. **Normalize + Log transform**
6. **Batch-correct merged matrix**
7. **Run PCA / visualize structure**
8. **Train ML models** to classify cancer vs normal



## **🧪 Supported Datasets**

The pipeline is built for GEO microarray datasets (GPL96/GPL571/GPL1352 etc.) and automatically extracts:

* GSM sample metadata
* Expression matrices
* Phenotype labels (`cancer`, `normal`)



## **⚙ Requirements**

```
Python 3.10+
pandas
numpy
scikit-learn
matplotlib
seaborn
GEOparse
pycombat / combat.py implementation
```



## **📦 Output**

* Cleaned dataset summaries
* PCA plots
* Batch-corrected merged expression matrix
* Gene-level table (optional)
* Trained ML model metrics


