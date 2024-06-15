# NLP Comparison and Clustering

## Overview

This project aims to compare the performance of two Natural Language Processing (NLP) packages, Stanza and SpaCy, with a focus on Named Entity Recognition (NER). The project also incorporates clustering techniques using K-means and visualizes the resulting clusters with Principal Component Analysis (PCA). These methods are applied to provide a comprehensive analysis of NER capabilities and to explore underlying patterns in the data.

## Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
  - [Loading the Notebook](#loading-the-notebook)
  - [Data Preprocessing](#data-preprocessing)
  - [Named Entity Recognition](#named-entity-recognition)
  - [Clustering and Visualization](#clustering-and-visualization)
  - [Metrics and Evaluation](#metrics-and-evaluation)
- [Important Notes](#important-notes)
- [Contributing](#contributing)
- [License](#license)

## Requirements

- Python 3.x
- pandas
- scikit-learn
- matplotlib
- seaborn
- stanza
- spacy
- numpy
- notebook

## Installation

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/Mery-e/datascienceproject/edit/main/README.md
        ```

2. Navigate to the project directory:

    ```bash
    cd stanza_and_spacy_comparison
    ```

3. Create and activate a virtual environment (optional but recommended):

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

4. Install the required dependencies using pip:

    ```bash
    pip install -r requirements.txt
    ```

5. Ensure you have Jupyter Notebook installed:

    ```bash
    pip install notebook
    ```

## Usage

### Loading the Notebook

Start Jupyter Notebook:

```bash
jupyter notebook

Data Preprocessing
The notebook begins by loading and preprocessing the data.

Named Entity Recognition
The notebook contains functions to perform Named Entity Recognition (NER) using both SpaCy and Stanza.

Example Usage:
SpaCy NER:
import spacy

nlp_spacy = spacy.load('en_core_web_sm')

def spacy_model(doc):
    doc_spacy = nlp_spacy(doc)
    spacy_entities = [(ent.text, ent.label_) for ent in doc_spacy.ents]
    return spacy_entities

















## Installation

1. Clone the repository to your local machine.
    ```bash
    git clone https://github.com/Mery-e/datascienceproject/edit/main/README.md
    ```

2. Install the required packages.
    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have Jupyter Notebook installed.
    ```bash
    pip install notebook
    ```

## Usage

### Loading the Notebook

1. Start Jupyter Notebook.
    ```bash
    jupyter notebook
    ```

2. Open the `compare.ipynb` notebook.

### Data Preprocessing

The notebook begins by loading and preprocessing the data. Ensure that all paths provided are absolute paths, as relative paths may not work correctly.

### Named Entity Recognition

The notebook contains functions to perform Named Entity Recognition (NER) using both SpaCy and Stanza. The results are stored in a format suitable for comparison.

#### Example Usage:

- **SpaCy NER**:
    ```python
    nlp_spacy = spacy.load('en_core_web_sm')
    
    def spacy_model(doc):
        doc_spacy = nlp_spacy(doc)
        spacy_entities = [(ent.text, ent.label_) for ent in doc_spacy.ents]
        return spacy_entities
    ```

- **Stanza NER**:
    ```python
    nlp_stanza = stanza.Pipeline(lang='en', processors='tokenize,ner')
    
    def stanza_model(doc):
        doc_stanza = nlp_stanza(doc)
        stanza_entities = [(ent.text, ent.type) for ent in doc_stanza.ents]
        return stanza_entities
    ```

### Clustering and Visualization

The notebook applies K-means clustering on the preprocessed data and visualizes the clusters using PCA.

#### Example Usage:

```python
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_train_vec.toarray())

plt.figure(figsize=(10, 8))
plt.scatter(X_pca[:, 0], X_pca[:, 1], c=predicted_labels, cmap='viridis')
plt.xlabel('PCA Component 1')
plt.ylabel('PCA Component 2')
plt.title('Clusters Visualization after K-means Clustering with PCA')
plt.colorbar(label='Cluster')
plt.savefig('Clusters_K-means_PCA.png')
plt.show()
```

### Metrics and Evaluation

The notebook calculates both supervised and unsupervised metrics to evaluate the clustering results.

#### Example Usage:

```python
from sklearn import metrics

print("Homogeneity: %0.3f" % metrics.homogeneity_score(y_train, predicted_labels))
print("Completeness: %0.3f" % metrics.completeness_score(y_train, predicted_labels))
print("V-measure: %0.3f" % metrics.v_measure_score(y_train, predicted_labels))
print("Adjusted Rand-Index: %.3f" % metrics.adjusted_rand_score(y_train, predicted_labels))
print("Silhouette Coefficient: %0.3f" % metrics.silhouette_score(X_train_vec, predicted_labels))
```

## Important Notes
- **Time-Consuming Operations**: Some operations, particularly those involving large datasets and batch processing, can be time-consuming.





