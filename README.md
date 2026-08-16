# Dynasty Fantasy Football - All-Time League Profiles

A data pipeline and visualization project for analyzing the history of a dynasty fantasy football league using the [Sleeper API](https://docs.sleeper.com/).

The project pulls historical matchup, roster, user, and player data across multiple seasons, aggregates the points scored by players when they were started, and builds an **all-time starting lineup for each manager**. Those results are then combined with other league-history metrics to create manager profile infographics.

## What It Does

The Jupyter notebook:

* Pulls historical matchup and roster data from Sleeper
* Maps league users to manager names across seasons
* Tracks player points and games started when a player was in a starting lineup
* Identifies each manager's top all-time players by position
* Builds an all-time lineup consisting of:

  * QB
  * 2 RB
  * 2 WR
  * TE
  * FLEX
* Exports detailed player history and manager lineups to CSV

The resulting data can be used to create league-history profiles such as the example infographic included in this repository.

## Repository Contents

* `rosemount_dynasty_alltimerosters.ipynb` — Sleeper API data collection, aggregation, and all-time lineup generation
* `Rosemount Dynasty Team Profiles #4 - Zach.png` — Example manager profile infographic

## Current Approach

The notebook is intentionally straightforward and serves as an initial proof of concept. Season-specific league IDs, season lengths, and manager-name mappings are currently maintained as configuration within the notebook.

The analysis currently focuses on **production from starting lineups**, rather than simply looking at total roster ownership or player production while on a team's bench.

## Next Steps

Potential improvements include:

1. **Harden the data pipeline**

   * Remove season-specific hardcoding where possible
   * Improve API error handling and request reliability
   * Automate discovery of historical league IDs
   * Add validation and logging for missing or inconsistent data

2. **Automate the workflow**

   * Move API extraction and transformation logic into reusable Python scripts
   * Establish a repeatable data pipeline that can refresh league data automatically
   * Store standardized outputs for downstream analysis

3. **Expand analytics**

   * Add deeper roster, draft, playoff, and championship analysis
   * Track player tenure and manager roster-building trends
   * Develop additional measures of team strength and historical performance
   * Identify trends, anomalies, and notable league milestones

4. **Build a BI layer**

   * Connect the processed data to Power BI or another visualization platform
   * Create interactive manager profiles and league-history dashboards
   * Eventually automate the generation and distribution of manager reports

The long-term goal is to evolve this from a one-off historical analysis into a **reusable fantasy football analytics pipeline** capable of continuously collecting league data and producing increasingly comprehensive insights.

