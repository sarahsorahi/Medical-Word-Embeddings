# 🧬 Medical Word Embeddings: Semantic Modeling of Medical English Vocabulary

This project trains and analyzes word embeddings on medical English corpora. It aims to capture semantic relationships between medical terms and provide resources for applications in Medical English education, vocabulary analysis, and domain-specific NLP.

## 🚀 Project Goals

- Train custom word embeddings on medical texts (e.g. PubMed abstracts)
- Visualize and evaluate semantic relationships between medical terms
- Provide tools for term similarity search, synonym identification, and vocabulary support

## 📂 Project Structure

medical-word-embeddings/
│
├── data/ # Raw and cleaned medical text corpora
├── notebooks/ # Jupyter notebooks for training and visualization
├── models/ # Saved embedding models (e.g., Word2Vec)
├── results/ # Output CSVs and plots
├── README.md # Project overview
└── requirements.txt # Dependencies



## 📚 Dataset

We use medical abstracts from PubMed and/or clinical notes from public datasets:

- [PubMed Central Open Access Subset](https://www.ncbi.nlm.nih.gov/pmc/tools/openftlist/)
- [BioASQ dataset](http://bioasq.org/)
- [Kaggle Clinical Notes Sample](https://www.kaggle.com/datasets/cdc/clinical-notes)

To keep the project lightweight, I include a sample PubMed abstracts file in `data/pubmed_sample.txt`.

## 🧠 Word Embedding Models

I use `gensim`'s Word2Vec for training:

```python
from gensim.models import Word2Vec
model = Word2Vec(sentences, vector_size=100, window=5, min_count=5, workers=4)
model.save("models/med_word2vec.model")
