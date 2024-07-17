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
## Results
- Lineup: Boone Jenner, Artemi Panarin, Nick Schmaltz, Morgan Rielly, Pheonix Copley, Juuso Valimaki, Anze Kopitar, Clayton Keller, Adrian Kempe
- Total Points: 311.8	
- Salary Cap: $50,000
## Conclusions
### Tactical Information
When it came to determining the optimal lineup using the season data, I found that the total points for the lineup while satisfying each of the constraints was 22,512.4. When analyzing the slack for the constraints, I found that there was no slack for either the player or salary constraints, meaning the entire 50,000 was used. When performing sensitivity analysis, testing a range of 40,000 to 60,000, the total points almost directly linearly correlated with the salary increase, which indicates that the lineup changed each time the salary was incremented.

After checking rubric and seeing that average total points per game was required for the season data problem instead of a total, I found that the lineup above was most optimal, producing 486.58 points. However, when re-calculating the slack for the salary constraint, there was 600 unused dollars in the budget, meaning that the full 50,000 was not optimized. While this solution stays in line with the rubric, I think my first solution, the one that calculates total points instead of total points per game, was the best.

### Strategic Information
Regarding the actual game data that was used in M2, we determined the lineup listed above was the most optimal, yielding 311.8 points and satisfying all of the constraints. When performing sensitivity analysis, the first thing that stuck out to me was that the salary constraint was 10,100 less than the allowed salary cap. However, when I tested a salary cap range from 40,000 to 60,000, the lineup remained the same from 50,000 to 60,000. This means that either the optimal lineup determined earlier in the problem was the best possible and there was simply no need to spend any more money, or there was an issue somewhere else in the problem that I didn't catch.

## Limitations, Improvements, and Challenges
One of the first observations I made was that there may be a better way of predicting the optimal lineup instead of total points. Maybe take into account time played or other statistics that someone with knowledge of the sport would be wary of. This extra information might increase the accuracy of the model or produce a more optimal lineup.

My ideal sensitivity analysis would have had the player positions as the column names, which would better show the changes in lineup as the salary cap went up. However I couldn't find out how to assign the positions to the column names and keep them consistent with the positions of the players in each lineup. I would've also liked to include total points per player, team, and position in the sensitivity analysis dataframe, but I couldn't figure out how to make a dictionary that included multiple values per key without wrecking the entire model. Maybe, given more time, I'd be able to make some of these changes.
