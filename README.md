# Formula 1 2008 — Driver and Constructor Analysis

Python analysis of an educational Formula 1 dataset, developed during the **Python Programming** course of the **ProfessionAI Master in Data Analytics**.

## Project overview

The project uses race results to analyze individual driver performance and generate driver and constructor standings.

It demonstrates data loading, functions, dictionaries, user input validation, aggregation, sorting, and text file export.

## Dataset

The dataset provided for the assignment contains **180 records**, covering **10 drivers** and **6 teams**.

Each record includes:

| Column | Description |
|---|---|
| Driver | Driver surname |
| Team | Constructor name |
| Race | Race location |
| Country | Host country |
| Position | Points-paying finishing position, or 0 |

**Position 0** means that the driver finished outside the points-paying top eight. It does not specify the exact finishing position or whether the driver retired.

Dataset source: [ProfessionAI — Formula 1 CSV](https://proai-datasets.s3.eu-west-3.amazonaws.com/formula1_data.csv)

## Scoring system

| Position | Points |
|---|---:|
| 1 | 10 |
| 2 | 8 |
| 3 | 6 |
| 4 | 5 |
| 5 | 4 |
| 6 | 3 |
| 7 | 2 |
| 8 | 1 |
| 0 | 0 |

The dataset is loaded once, and points are calculated once for reuse across all analyses. Unexpected position values raise an error.

## Features

### Individual driver analysis

The interactive interface lists the available drivers and lets the user select a surname.

The `analyze_driver()` function returns:

- Total points.
- Number of wins.
- Number of podium finishes.

Users can analyze multiple drivers in the same session.

### Driver standings

The `create_driver_standings()` function:

- Calculates total points for every driver.
- Returns a dictionary sorted by descending points.
- Displays the standings.
- Exports them to `Drivers_Standings_2008.txt`.

Google Colab then initiates the download of the text file.

### Constructor standings

The `create_constructor_standings()` function aggregates points by team and returns a dictionary sorted by descending points.

### Consistency checks

Final checks confirm that the driver standings and constructor standings both account for the total points in the dataset.

## Selected results

Results calculated from the supplied dataset:

| Driver | Points |
|---|---:|
| Hamilton | 98 |
| Massa | 97 |
| Raikkonen | 75 |
| Kubica | 75 |

| Constructor | Points |
|---|---:|
| Ferrari | 172 |
| McLaren | 151 |
| BMW | 135 |

Both standings account for **610 total points**.

## How to run

1. Download `formula1_data_portfolio.ipynb` from this repository.
2. Open [Google Colab](https://colab.research.google.com/) and upload the notebook.
3. Run the cells in order.
4. Enter a driver surname exactly as shown in the available drivers list.
5. Answer `no` after an analysis, or enter `quit` at the driver prompt, to finish the interactive session.
6. Run the remaining cells to generate the standings, download the text file, and perform the consistency checks.

An internet connection is required to load the dataset.

The notebook is designed for Google Colab and uses `google.colab.files` for downloading the exported standings.

## Scope and limitations

- The supplied dataset covers a subset of participants. Results do **not** represent the complete official championship standings.
- Equal point totals retain the order of first appearance in the dataset. Official championship tie-breaking rules are not implemented.
- The consistency checks verify point reconciliation; they do not independently establish the historical accuracy or completeness of the source data.

## Tools

- Python
- Pandas
- Google Colab

## Author

**Claudio Lombardi**

[GitHub profile](https://github.com/PsyClaudio)
