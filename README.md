# wiki-recommender

A content-based recommender system for Wikipedia articles, created as a project for the Information Retrieval course.

**Authors:** Julia Korzekwa, Alicja Jakowczuk

## About

Given a list of Wikipedia articles a user has visited (as titles or links), the system recommends other articles from our database, each with a similarity score.

The pipeline consists of three steps:

1. **Crawling and scraping** – a randomised depth-first crawler collects ~2000 Wikipedia articles.
2. **Preprocessing** – the texts are tokenized, stop words are removed and words are stemmed with the Porter stemmer.
3. **Recommendation** – articles are represented as TF-IDF vectors and scored by their cosine similarity to the average profile of the visited articles.

The report also includes statistics about the database and charts explaining why each article was recommended.

## Files

- `wiki-recommender-report.ipynb` – the full report with source code, statistics and examples
- `raw_articles.parquet` – downloaded articles (raw text)
- `articles.parquet` – preprocessed articles (stemmed and lemmatized tokens)
- `requirements.txt` – required Python packages

## How to run

```bash
python -m venv .venv
.venv\Scripts\activate        # on Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook wiki-recommender-report.ipynb
```

The data files are included, so crawling does not have to be repeated – the notebook loads them directly.
