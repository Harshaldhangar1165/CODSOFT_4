# MovieMate — Recommendation System (CodSoft AI Internship Task 4)

MovieMate recommends movies based on a movie you like or a free-text description of your preferences. It uses a content-based filtering approach with TF-IDF-style text vectors and cosine similarity.

## Features

- Recommend movies similar to a selected title
- Recommend based on text preferences, e.g. `space adventure`, `funny family`, or `mystery detective`
- Movie titles, genres, and descriptions included in a sample CSV dataset
- Fuzzy matching for small title typos
- Similarity scores for recommendations
- Interactive command-line menu
- Unit tests; no third-party dependencies

## Requirements

Python 3.9 or newer. The project uses only Python's standard library and works offline.

## Run

```bash
python recommender.py
```

Choose:
1. Recommend movies similar to a movie title.
2. Recommend movies based on your preferences.
3. Exit.

To customize the catalog, edit `movies.csv` and add rows with `title`, `genres`, and `description`.

## Example

For a title-based recommendation, enter `The Martian`. Movies with similar science-fiction and adventure content should rank highly.

For preference-based recommendations, enter `space adventure` or `comedy family`.

## Run tests

```bash
python -m unittest -v
```

## How it works

1. Combines each movie's genre and description into a text document.
2. Tokenizes text into lowercase words.
3. Builds TF-IDF-style weighted vectors. Repeated genre terms give genre information additional influence.
4. Uses cosine similarity to compare two vectors.
5. Ranks movies by similarity and excludes the input movie from title-based recommendations.

This is content-based filtering: recommendations are based on item descriptions, not other users' ratings. The sample catalog is intentionally small for a beginner-friendly internship project, so recommendations depend on the quality and variety of its descriptions.

## Project structure

```text
CODSOFT_TASK4/
├── recommender.py
├── movies.csv
├── test_recommender.py
├── README.md
└── .gitignore
```

