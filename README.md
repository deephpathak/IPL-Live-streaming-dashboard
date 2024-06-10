# Live IPL Score 2024 Dashboard

Welcome to the Live IPL Score 2024 Dashboard! This Power BI dashboard provides real-time updates on the IPL 2024 matches, including live scores, player statistics, and points table data. 

The dashboard connects to the Cricbuzz API to fetch live data and uses Power Query for data cleaning and DAX for calculations.

## Features

- **Live Score**: Real-time updates of the current match score.
- **Live Overs**: Display of the current over and ball count.
- **Live Batsman Score**: Statistics for batsmen currently on the field.
- **Live Bowler Stats**: Statistics for the bowler currently bowling.
- **Number of Fours and Sixes**: Count of boundaries hit in the match.
- **Player and Captain Images**: Visual representation of players and captains.
- **Points Table**: Current standings of the teams in the IPL 2024.

## Getting Started

To set up and run this project locally, follow the steps below.

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
- Cricbuzz API access (You will need to obtain an API key from Cricbuzz)



Data is cleaned and transformed using Power Query Editor.
Steps include removing unwanted columns, filtering rows, and renaming columns for better readability.
DAX Calculations:

Live Score: LIVE_SCORE = SUM(MatchData[Score])
Live Overs: LIVE_OVERS = CONCATENATE(MAX(MatchData[Overs]), ".", MAX(MatchData[Balls]))
Live Batsman Score: Batsman_Score = CALCULATE(SUM(PlayerStats[Runs]), FILTER(PlayerStats, PlayerStats[Status] = "Batting"))
Live Bowler Stats: Bowler_Stats = CALCULATE(SUM(PlayerStats[Wickets]), FILTER(PlayerStats, PlayerStats[Status] = "Bowling"))
Number of Fours and Sixes:
Fours = COUNTROWS(FILTER(BallData, BallData[Runs] = 4))
Sixes = COUNTROWS(FILTER(BallData, BallData[Runs] = 6))
Fetching Images: URL links to player and captain images are integrated within the dataset.
Points Table: Aggregated data from all matches to display team standings.


Use the visual filters to view specific match data, player statistics, and team standings.

The dashboard will automatically refresh with live data from the Cricbuzz API.


Acknowledgements
Cricbuzz API for providing the live data.
Power BI for the powerful data visualization tools.

Contact
For any questions or feedback, please contact your deephpathak@gmail.com
