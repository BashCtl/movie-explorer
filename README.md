# Movie Explorer

Movie Explorer is a Jupyter notebook project for exploring the TMDB 5,000 movie dataset. It combines movie information with cast and crew data, cleans and enriches the records, and uses pandas and matplotlib to examine ratings, genres, budgets, revenue, directors, actors, and release dates.

## Project contents

- [`movies.ipynb`](movies.ipynb) — the main project workflow, from loading and cleaning data through analysis and charts.
- `data/tmdb_5000_movies.csv` — movie details such as release date, budget, revenue, genres, runtime, and ratings.
- `data/tmdb_5000_credits.csv` — cast and crew details, including actors and directors.

The notebook expects both CSV files to remain in the `data/` directory relative to the project root.

## Set up

The project requires Python 3.13 or newer. With [uv](https://docs.astral.sh/uv/) installed, create the project environment and install its dependencies:

```bash
uv sync
```

This installs pandas, NumPy, Matplotlib, and the notebook kernel dependency. Open `movies.ipynb` in Jupyter or another notebook editor and select the project's Python environment as its kernel.

## What the notebook does

1. Loads and inspects the movie and credit tables.
2. Selects useful movie fields, handles missing or zero values, parses release dates and genre lists, and removes duplicate movie IDs.
3. Adds derived fields such as release decade, runtime category, profit, return on investment, and weighted rating.
4. Compares ratings and financial outcomes across genres, decades, runtime groups, and budget groups; it also identifies unusually long or short runtimes.
5. Joins director information and summarizes ratings for directors and lead actors with enough credited films.
6. Draws charts for rating distributions, genre ratings, ratings over time, and budget versus revenue.

The rating analyses generally use movies with at least 100 votes to reduce the influence of films with very few ratings. Financial comparisons require recorded budget and revenue values.
