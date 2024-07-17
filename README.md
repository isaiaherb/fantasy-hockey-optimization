# Fantasy Hockey Lineup Optimization
## Description
This project, completed for my optimization modeling course, uses Pyomo's GLPK Solver Engine to determine the best fantasy hockey lineup given the data provided from the 2022-23 season.
## Requirements
We'd like to determine the Draft Kings fantasy hockey lineup that optimizes the statistics, specifically the total points, of each player while keeping within the following boundaries: the team must have 9 players, a maximum salary of $50,000, and include players from at least 3 different teams. There must also be two centers, two defenders, three wings, one utility (center, defender, or wing), and one goalie. In accordance with these constraints, we're incorperating two sets of data, one that describes player statistics for the entire season, and one that has the same statistics for the most recent game. Our first problem is to create the optimal lineup using the season data, and our second is to create the optimal lineup using the actual game data.
## Data
- DKSalaries.csv – Data from Draftkings website including player names, teams, salary, position, and average points per game. 
- Actual game data from Feb 11, 2023
  - skaters-actual.csv – Data from each of the seven games on Feb 11 related to the skaters (i.e., non-goalies).
  - goalies-actual.csv – Data from each of the seven games on Feb 11 related to the goalies.
- Season Statistics
  - skaters.csv – Data from the NHL season (October 7, 2022 through Feb 10, 2023) related to skaters.
  - goalies.csv - Data from the NHL season (October 7, 2022 through Feb 10, 2023) related to goalies.
