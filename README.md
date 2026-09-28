# IPL 2022 — Exploratory Data Analysis

Exploratory data analysis of match-level data from the IPL 2022 season, built with pandas, seaborn, and matplotlib. The notebook cleans the data, visualizes key patterns across the season, and writes up an observation after every chart, ending with an overall conclusion.

## Overview

The dataset covers all 74 matches of IPL 2022, from the first group-stage game (March 26, 2022) through the final (May 29, 2022). The analysis looks at:

- Which teams won the most matches
- How teams used the toss and how strongly they favored one decision
- Scoring patterns: top individual scores, first vs. second innings totals, and margins of victory
- Which players and venues stood out across the season
- Whether scoring changed as the season progressed

## Dataset

`IPL.csv` contains 74 rows (one per match) and 20 columns:

| Column | Description |
|---|---|
| `match_id` | Match number in the season |
| `date` | Match date |
| `venue` | Stadium where the match was played |
| `team1`, `team2` | The two teams playing |
| `stage` | Group, Playoff, or Final |
| `toss_winner`, `toss_decision` | Team that won the toss and whether it chose to bat or field |
| `first_ings_score`, `first_ings_wkts` | First innings runs and wickets lost |
| `second_ings_score`, `second_ings_wkts` | Second innings runs and wickets lost |
| `match_winner` | Winning team |
| `won_by`, `margin` | Whether the win was by runs or wickets, and by how much |
| `player_of_the_match` | Player of the match |
| `top_scorer`, `highscore` | Top batter of the match and their score |
| `best_bowling`, `best_bowling_figure` | Best bowler of the match and their figures |

## Data preparation

- Fixed a malformed date entry (`April11,2022`) and converted the `date` column to datetime
- Checked for missing values (none found)
- Created a `run_diff` column (first innings score minus second innings score) for the innings comparison

## Visualizations

- Bar chart: matches won per team
- Count plot: toss decision (bat vs. field)
- Histogram: distribution of the highest individual score per match
- Count plot: matches won by runs vs. wickets
- Bar chart: top 10 player-of-the-match winners
- Bar chart: matches played per venue
- Scatter plot: first vs. second innings score
- Line chart: innings scores over the season

## Key findings

- **Gujarat had the standout season**, leading with 12 wins and winning the final against Rajasthan. Mumbai and Chennai finished with the fewest wins (4 each).
- **Fielding first was the dominant strategy**, chosen in 59 of 74 matches (about 80%).
- **Batting first produced higher average scores** (171 vs. 159 runs), but the team with the higher first innings score won only 37 of 74 matches.
- **Wins were split evenly** between runs (37) and wickets (37), but run-wins averaged a 28-run margin while wicket-wins averaged 6 wickets.
- **No single player dominated**: Kuldeep Yadav led the player-of-the-match count with just 4 awards.
- **Matches were concentrated at four Mumbai/Pune venues** (70 of 74 matches), reflecting the season's bio-bubble format.
- **Scoring showed no meaningful trend** over the season (correlation with date near zero for both innings).

## Tools

- Python
- pandas
- numpy
- matplotlib
- seaborn

## How to run

1. Clone the repo and keep `IPL.csv` in the same folder as the notebook.
2. Install dependencies:
```
   pip install pandas numpy matplotlib seaborn
```
3. Open and run `IPL_analysis.ipynb` in Jupyter.

## Repo structure

```
├── IPL.csv               # match-level dataset
├── IPL_annotated.ipynb   # analysis notebook with observations and conclusion
└── README.md
```
