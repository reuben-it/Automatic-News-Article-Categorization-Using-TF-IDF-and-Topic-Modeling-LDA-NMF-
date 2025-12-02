# Automatic-News-Article-Categorization-Using-TF-IDF-and-Topic-Modeling-LDA-NMF-

🔥 Automatic News Article Categorization Using TF-IDF, LDA & NMF

Unsupervised Topic Modeling + RSS Scraping + NLP Pipeline

📌 Project Overview

This project implements an end-to-end automatic news categorization system using unsupervised machine learning techniques. It collects news articles from RSS feeds, preprocesses the text, extracts TF-IDF features, and applies Latent Dirichlet Allocation (LDA) and Non-Negative Matrix Factorization (NMF) to identify hidden topics.
A custom keyword-based topic labeling mechanism then assigns meaningful category names to each discovered topic.

This system can categorize news into domains such as:

Politics & Policy

Business & Economy

Technology

Sports

Science & Space

Health

Environment

It is fully modular, offline-compatible, and easy to extend.

🧩 Features

✔ RSS feed scraping (NPR/Reuters or any feed)
✔ NLP preprocessing (cleaning, tokenization, stopword removal, lemmatization)
✔ TF-IDF feature extraction
✔ LDA and NMF topic modeling
✔ Extraction of top words per topic
✔ Keyword-based topic labeling system
✔ Modular code structure (scraper, preprocessing, models, main driver)
✔ Offline fallback dataset included
✔ Configurable via command-line interface

📁 Project Structure
news-topic-modeling/
│
├── main.py                # Main driver script
├── scraper.py             # RSS scraping utilities
├── preprocessing.py       # Text cleaning & TF-IDF extraction
├── models.py              # LDA and NMF model implementations
│
├── data/
│   └── news_articles.csv  # Saved scraped articles (optional)
│
├── README.md              # Project documentation
└── requirements.txt       # Dependencies

🛠️ Technologies Used
Programming Language

Python 3.x

Libraries

scikit-learn (TF-IDF, LDA, NMF)

NLTK (stopwords, lemmatization)

feedparser (RSS scraping)

pandas

NumPy

⚙️ How It Works (Pipeline)

Scrape RSS articles (optional)

Preprocess text

remove noise

tokenize

remove stopwords

lemmatize

Transform into TF-IDF vectors

Apply LDA and NMF topic models

Extract top words per topic

Infer topic labels via keyword overlap

Save/display final categorized articles

🖥️ Running the Project
1️⃣ Install dependencies
pip install -r requirements.txt

2️⃣ Scrape RSS articles (optional)
python main.py --scrape --url "https://feeds.npr.org/1004/rss.xml" --num_articles 20


This creates a CSV inside the data/ folder.

3️⃣ Run preprocessing + topic modeling
python main.py --process_and_model --n_topics 5 --n_top_words 10

4️⃣ Output Example

You will see:

Topic #1 – Politics & Policy: government law election minister ...
Topic #2 – Technology: smartphone ai software digital ...
...


and a table:

Title	LDA Label	NMF Label
Govt passes new bill	Politics	Politics
New smartphone launched	Technology	Technology
🧠 Category Keywords (Topic Labeling Logic)

Topics are mapped to categories using curated keyword sets, e.g.:

"Technology": {"software", "ai", "device", "smartphone", "internet", ...}
"Sports":     {"match", "tournament", "team", "player", "football", ...}


The category with highest overlap becomes the topic label.
