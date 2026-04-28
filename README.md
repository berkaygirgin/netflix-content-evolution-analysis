# Netflix Content Evolution Analysis
![Netflix Content Evolution Analysis](https://img.shields.io/badge/Netflix-Content%20Analysis-E50914?style=for-the-badge&logo=netflix&logoColor=E50914&labelColor=221F1F)

A focused data analysis project examining Netflix’s catalog structure, content trends, movie durations, and rating patterns using exploratory analysis and hypothesis testing.

## Project Overview

This project analyzes the structure and evolution of Netflix’s content catalog. The main focus is on content type, movie duration, rating groups, and how titles were added over time.

The project combines exploratory data analysis with chi-square hypothesis testing. The goal is not only to visualize patterns, but also to check whether the main observed differences are statistically significant.

This is a focused catalog analysis, not a general Netflix dashboard.

## Dataset

The dataset used in this project is the [Netflix Movies and TV Shows dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows) from Kaggle.

It contains 8,807 Netflix titles and 12 columns, including Movies and TV Shows. The main columns used in this analysis are content type, title, date added, release year, rating, duration, country, and listed genres.

## Research Questions

This project focuses on the following questions:

- How is Netflix content distributed between Movies and TV Shows?
- How did Netflix title additions change over time?
- Are movie duration patterns different across release eras?
- Does rating group distribution differ between Movies and TV Shows?
- Did the Movie/TV Show mix change across years added?

## Methods

The analysis follows a simple workflow:

- Data cleaning and basic type fixes
- Feature engineering for `year_added`, `month_added`, `rating_group`, `duration_category`, and `era`
- Exploratory data analysis with focused visualizations
- Chi-square hypothesis testing for categorical relationships
- Cramér’s V to check the strength of the tested associations
- Additional visual analysis for genre duration, seasonality, and TV show season counts

## Key Findings

- The Netflix catalog is clearly movie-heavy. Movies make up 69.7% of all titles, while TV Shows make up 30.3%.

- Netflix added much more content after 2015. The busiest period was 2018–2020.

- Most movies are in the 1.5–2 hour range. Older movies have a higher share of 2+ hour titles, while newer movies are more concentrated in shorter duration categories.

- All three chi-square tests were statistically significant. However, the Cramér’s V values were small, so the patterns exist in the data but they are not very strong in practice.

- The additional analysis gives extra context. Movie duration also changes by genre. Most TV Shows have only 1–2 seasons, and Netflix title additions were not evenly spread across years or seasons.

## Statistical Tests

Three chi-square tests of independence were used to check whether the main categorical patterns were statistically significant.

| Test | p-value | Cramér's V | Interpretation |
| --- | ---: | ---: | --- |
| Movie Duration Category vs Release Era | 3.0128e-63 | 0.1317 | Significant, small association |
| Rating Group vs Content Type | 9.5362e-22 | 0.1072 | Significant, small association |
| Content Type vs Year Added | 5.2149e-11 | 0.0811 | Significant, very small association |

All three tests were statistically significant, but the effect sizes were small. So the patterns should be interpreted carefully and not overstated.

## Tools Used

- Python
- pandas
- matplotlib
- seaborn
- scipy
- Poetry
- Jupyter Notebook

## Repository Structure

```text
netflix-content-evolution-analysis/
├── data/
├── notebooks/
├── pyproject.toml
├── poetry.lock
└── README.md
```

## How to Run

- Clone this repository.
- Install the project dependencies with Poetry.
- Open the notebook with Jupyter.

```bash
git clone https://github.com/berkaygirgin/netflix-content-evolution-analysis.git
cd netflix-content-evolution-analysis
poetry install
poetry run jupyter notebook
```