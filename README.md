# Home-Field Advantage in the NFL

Exploratory analysis of NFL home-field advantage, 2000–2023 — 6,175 games from nflverse. Python, pandas.

## TL;DR

Do NFL teams actually play better at home, and is that edge fading? Across **6,175 regular-season
games (2000–2023)**, home teams won **56.26%** of the time and outscored visitors by an average of
**+2.23 points**. The advantage is real — but it is eroding: home win rate fell **2.19 percentage
points**, from a 57.03% average in 2000–2008 to 54.84% in 2015–2023.

![Home win rate by season, 2000–2023](visuals/home_win_trend.png)

![Home win rate with a five-year rolling average](visuals/rolling_avg.png)

## Full writeup

The analysis is written up in two places — start with the case study:

- **[Case study](https://hamptonabbott.com/projects/home-field-advantage/)** — the story and the findings.
- **[Technical report](https://hamptonabbott.com/projects/home-field-advantage-report/)** — data sourcing, cleaning decisions, sample design, and limitations.

## Repo structure

```
data/         raw and processed CSVs (gitignored — see "Run it" below)
notebooks/    00_setup → 01_home_field_eda → 02_interpretation
visuals/      exported charts
```

## Run it

The dataset is not committed, so download it first.

```bash
git clone https://github.com/hamptonabbott/home-field-advantage.git
cd home-field-advantage
pip install -r requirements.txt

# fetch the source data the notebooks expect
curl -L https://github.com/nflverse/nfldata/raw/master/data/games.csv -o data/raw/games.csv

jupyter notebook
```

Run the notebooks in order: `00_setup.ipynb` filters and cleans the games into
`data/processed/`, then `01_home_field_eda.ipynb` and `02_interpretation.ipynb` produce the charts
in `visuals/`.

## Data

nflverse. *nfldata: games.csv* (GitHub repository dataset file). Retrieved February 18, 2026, from
<https://github.com/nflverse/nfldata/raw/master/data/games.csv>

## License

MIT — see [LICENSE](LICENSE).

## AI transparency

ChatGPT 5.2 was used as a support tool to polish written explanations for clarity and readability,
and as a teaching aid during web development (explaining concepts, troubleshooting, and improving
understanding). It was not used to design, generate, or compose the core analytical, technical, or
conceptual components of this project. All primary ideas, decisions, and project outcomes remain the
author's own.
