# Data Science Project: Text Comparison and Clustering   
    
## Table of Contents

1. [Overview](#overview)
2. [Installation and Usage](#installation and Usage)
3. [Data Collection](#data-collection)
4. [Data Analysis](#data-analysis)
5. [Clustering](#clustering)
6. [Comparing Linguistic Processing Libraries](#comparing-linguistic-processing-libraries)
7. [Named Entity Recognition (NER)](#named-entity-recognition-ner)
8. [Requirements](#requirements)
9. [Contributing](#contributing)


## Overview
This project aims to compare the performance of two Natural Language Processing (NLP) packages, Stanza and SpaCy, with a focus on Named Entity Recognition (NER). The project also incorporates clustering techniques using K-means and visualizes the resulting clusters with Principal Component Analysis (PCA). These methods are applied to provide a comprehensive analysis of NER capabilities and to explore underlying patterns in the data.

## Part 1: Comparing and Clustering Texts

### Data Collection

- *Biographies Extraction*: 
  - Implemented a function to extract biographies for Astronauts and Chefs from Wikipedia.
  - Collected a minimum of 100 biographies per category.
  
- *Knowledge Graph Facts*: 
  - Extracted RDF triples from an open-source knowledge graph (e.g., DBpedia, Wikidata) for each individual.
  - Limited to 100 facts per person due to storage constraints.
  
- *Data Storage*: 
  - Stored biographies and their categories in a Pandas dataframe.
  - Saved each biography in a separate text file named *person_category.txt*.
  - Knowledge graph facts were stored in a JSON file mapped back to each person.

### Data Analysis

#### Text Data Analysis

- *Preprocessing*: 
  - Segmented biographies into sentences.
  - Removed stop words and normalized text to lowercase.

- *Statistics and Visualizations*: 
  - *Vocabulary*: Determined 50 most frequent words and created word clouds for each category.
  - *Sentences*: Calculated min/max/avg number of sentences per category; created histograms and box plots.
  - *Tokens*: Analyzed total bi-gram occurrences per category; min/max/avg occurrences per sentence.

#### Graph Data Analysis

- *RDF Properties*: Identified 50 most frequent properties and generated property clouds for each category.
- *Facts*: Determined min/max/avg number of facts per category; created histograms and box plots.

### Clustering

- *Model Training*: 
  - Utilized KMeans clustering algorithm separately for text and graph data.
  - Split data into train and test sets for evaluation.

- *Comparison*: 
  - Compared clusters predicted using text input vs graph input.
  - Evaluated using supervised and unsupervised metrics.
  - Explored different data sizes, features, and clustering algorithms.

---

## Part 2: Comparing Linguistic Processing Libraries

### Named Entity Recognition (NER)

- *Processing*: 
  - Implemented functions to perform NER using Spacy and Stanza on biographies.
  - Results stored in a Pandas dataframe or JSON file.

### NER Analysis by Entity Type

- *Comparison*: 
  - Conducted detailed comparison of NER results between Spacy and Stanza.
  - Reported statistics on agreement, partial agreement, and disagreement per category and package.
  - Visualized comparison results.

### NER Verification Against Knowledge Graph

- *Verification*: 
  - Developed functions to verify predicted NEs against the knowledge graph for each person.
  - Used regular expressions for matching NEs found in text with RDF entities in associated texts.
  - Calculated the ratio of confidently predicted NEs found in the knowledge graph.
  - Explored co-reference resolution techniques for additional insights.

---

## Installation and Usage

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Mery-e/datascienceproject/tree/main
   cd text-comparison-clustering
   ```

2. Install Dependencies
To install the required dependencies, run the following command:

```bash

pip install -r requirements.txt
```

 ## Requirements
- Python 3.x
- pandas
- scikit-learn
- matplotlib
- seaborn
- keras
- trankit
- stanza
- numpy


### Contributions
Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request on GitHub.
