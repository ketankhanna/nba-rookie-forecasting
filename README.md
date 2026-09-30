# NBA Rookie Forecasting

Can a player's first three NBA seasons predict the peak of their career? This project forecasts a player's **career-high PER** (Player Efficiency Rating) from their rookie-contract years.

👥 **Team project** completed by a U of T student team, including Ketan Khanna · Foundations of Data Science (SCS 3250), University of Toronto · Winter 2020

## The Question
Front offices spend millions on draft picks and second contracts. If early-career stats can forecast peak performance, teams can spot future stars (and busts) sooner.

## Approach
1. **Data:** 1950-2017 season stats from Kaggle plus 2018 and 2019 seasons from basketball-reference.com
2. **Preparation:** removed empty placeholder columns, merged the sources, derived each player's draft year and season number, and filtered out seasons under 9 games
3. **Training set:** players from 1984-2006, averaging their first three seasons, with their career-max PER as the target
4. **Exploration:** correlation of every stat with peak PER (single-season PER, Win Shares, points, true shooting and minutes lead the way)
5. **Models:** a baseline linear regression, then improved variants tested on a separate 2007-2012 cohort

## Results
- The baseline predicts career-high PER within about **±2 points** for most players, with a strong R²
- It holds up on the unseen 2007-2012 players, slightly less accurately
- Fun outlier: Darrell Armstrong posts the top peak PER in the data, a one-season spike that shows why a single "max" can mislead

## Limitations
PER rewards offence far more than defence and can't measure intangibles like leadership, so it is one lens on value, not the full picture.

## Data
[NBA Players stats since 1950](https://www.kaggle.com/drgilermo/nba-players-stats) (Kaggle) and [basketball-reference.com](https://www.basketball-reference.com). Place the CSVs in `data/` to re-run.

## Tools
Python · pandas · scikit-learn · statsmodels · seaborn
