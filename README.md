# Opening Efficiency in Balanced Elite Chess Encounters

This project explores a dataset of chess games to analyze the efficiency and draw rates of different chess openings when played by evenly matched elite players (where the absolute Elo rating difference is $\le$ 25). 

## Research Question
**Which chess openings yield the highest and lowest draw rates in balanced elite encounters, and is the difference statistically significant?**

## Dataset
* **Source:** You will need a dataset named `games_chesstempo.csv` containing chess match records (with columns for `result`, `white_elo`, `black_elo`, and `opening`).
* **Preparation:** Place the `games_chesstempo.csv` file directly in the root directory of this project. The script automatically handles data cleaning by standardizing draw notations ("1/2-1/2"), filtering for valid game results, and extracting the primary opening family. 

## What the Script Does
* **Cleans and Prepares Data:** Filters out missing values and restricts the dataset to balanced games ($\vert{}\Delta \text{Elo}\vert{} \le 25$).
* **Statistical Analysis:** Calculates baseline draw and white win rates, aggregates data by opening family (minimum 80 games), and computes standard errors for binomial proportions.
* **Hypothesis Testing:** Performs a Z-test comparing the openings with the lowest and highest draw rates.
* **Outputs Generation:** Automatically creates a `figures/` directory and populates it with visualizations and summary metrics.

## Output Files
Running the script generates the following files in the `figures/` directory:
* `draw_rates_with_uncertainties.png`: A plot showing draw rates and standard errors for each valid opening.
* `elo_diff_distribution.png`: A histogram showing the distribution of absolute rating differences.
* `summary_metrics.txt`: A summary table of the calculated metrics for each opening.

## How to Run
### Dependencies
This script is written in base **R**. No external packages (like `ggplot2` or `dplyr`) are required.

### Execution
1. Ensure R is installed on your machine and `games_chesstempo.csv` is in the same directory as the script.
2. Run the script from your terminal or command prompt:
```bash
Rscript analysis.R