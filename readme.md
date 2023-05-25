# Clothing Similarity Search

Clothes similarity search provides ranked recommendations based on the description of the clothing provided from the database. This repository contains the source code for:

- Data Scraper
- Sentence Encoder
- Similarity Function

### Data Scraper

**Data scraper** makes use of the data available on [H&M website](https://www2.hm.com/en_in/index.html).

The scraped data is further feature-engineered and preprocessed to generate a wordSoup for representational encoding and is stored in the column _cleaned_text_

### Encoder

**Encoder** uses Tfidf-Vectorizer to generate sentence embeddings for every product description of size _1 x MAX_FEATURES_ _(default = 1000)_.

### Similarity Function

**Similarity Function** utilizes cosine similarity by _scikit-learn_ to generate a similarity measure between the **product description** and the **database** and provide n-ranked results to the user.

## Function Description

The **similarity function** can be accessed through cloud functions from [here](https://us-central1-clothes-similarity.cloudfunctions.net/clothes-similarity)

url: https://us-central1-clothes-similarity.cloudfunctions.net/clothes-similarity

The function takes 2 arguments as parameters:

- description(required): _description of the clothing article_
- limit(optional): _no. of clothing articles to return, default = 10_.
