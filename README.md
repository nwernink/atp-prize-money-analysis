# ATP Prize Money Analysis

### Background
This analysis focuses on the prize money distribution within the ATP by looking at the top 750 singles players and top 250 doubles players from each year starting in 2009* to the present. Although only ATP players are analyzed, similar results very much exist for the WTA Tour (albeit more exacerbated for the worse); however, the ATP website is much more friendly for this type of analysis so it is the one examined.

The following results are meant to show the distribution of prize money within the ATP Tour (which can be extrapolated to the WTA as well), but is not intended to investigate the inequality between the ATP and WTA Tours (which does exist).

### Collection

#### Data Retrieval
An overview list of all players for each year is scraped from the ATP website rankings page from the last week of each year (stored in data/players/overview). This data is then used to go into each player's activity profile in order to get all match data of the tournaments they played for the given year (stored in data/players/activity). 

#### Data Processing
Using the player activity data, a cleaned version is created to standardize prize money earned** and remove Davis Cup matches from players Tour level wins/losses statistics (stored in data/players/clean). Davis Cup matches are removed as wins/losses from player totals because neither prize money nor points are awarded which would create noise*** for later analyses. Additionally, player data is combined for each year so that their singles and doubles prize money is totaled in order to understand the total amount of prize money each player earns as many players play both singles and doubles (stored in data/players/combined)****.

#### Tournament Data Extraction
Unlike player data, tournament data is not readily available, so prize money data at the tournament level is extracted using the player results. This is accomplished by going through every player's match data and associating the prize money and points earned to that particular tournament (organized by singlles/doubles, year, tournament type, and round reached)*****. From there, the data is further synthesized by calculated the average prize money per point at each tournament type (stored in data/tournaments).


### Analyses

#### 1. Percent of Prize Money Won Per Ranking Band
For each year, the total amount of prize money is summed for the top 750 singles players and the top 250 doubles players separately. Then, for each ranking band of 50 players (i.e, 1-50, 51-100, etc.) the sum of their prize money is calculated in order to find the average amount of prize money earned by each particular ranking band of players. The resulting distribution of percent of prize money won shows how spread out prize money is awarded across the rankings.

#### 2. Ranking vs. Prize Money
For each year and for singles and doubles separately, each player's ranking and prize money earned is plotted to create a graph of ranking vs. prize money earned. These charts display how much prize money players earn in comparison to their rankings.

#### 3. Average vs. Median Prize Money Earned
For singles and doubles separately, the average and median prize money is calculated for each year and plotted across all years. The difference between average and media prize money earned reveals the skew of most of the prize money being awarded to a few players while the rest receive much less.

#### 4. Number of Players Earning $X Amount
The number of players earning at least a certain amount of prize money is calculated for each year by using the combined singles and doubles prize money data to count the number of players who earned the given amount.

#### 5. Ranking vs. Prize Money Per Point
For singles and doubles separately and each year individually, each player's ranking and their prize money earned divided number of points won is plotted to create graphs of ranking vs. prize money per point. These charts show the relationship between a player's ranking and how much money they earn per point they win.

#### 6. Correlation Between Ranking/Tour Level Matches Played and Prize Money Earned
The correlation between player rankings and prize money earned as well as tour level matches played and prize money earned is calculated by ranking band (1-50, 50-100, etc.) for each year for singles and doubles separately. The correlations illustrate how related the two variables are to each other.

#### 7. Average Prize Money Per Point at Each Tournament Level
The average prize money per point at each tournament level is calculated by averaging the prize money per point from each player at each tournament level by year. The charts show the trend in how prize money per point has been awarded across the years to players as well as the differences in prize money per point awarded between different tournament levels.

#### 8. Impact of Challenger Prize Money Increases on Number of Players Earning $X Amount
The number of players earning at least a certain amount can be manipulated by changing the amount of prize money players receive at various tournament levels. The following illustrates by what factor does Challenger level prize money need to be increased for a certain number of players to earn at least the given amount of money.

#### 9. Potential Impact of ATP Baseline on Player Earnings
In 2024, the ATP launched Baseline which is a financial security program for players that guarantees them a minimum amount of income based on their ranking as well as injury protection. Below shows the players that would be affected by this program if it were implemented in the previous year and by how much it would impact them.

#### 10. Total Prize Money Awarded at Each Tournament Level
The total prize money awarded at each tournament level is calculated by adding up all prize money earned by players from each respective tournament type. The charts show the trend of the amount of prize money earned each year at the various tournament levels.

#### 11. Average Prize Money Per Point at Each Round of Every Tournament
The average prize money per point at each round of each tournament level is calculated by averaging the prize money per point from each player at each round of each tournament by year.



##### Footnotes
*2009 is used as the starting year because the ATP overhauled its tournament structure to the way it exists now with Masters 1000s, 500s, and 250s.

**Prize money is inflated from January {year} to January 2023 (using https://www.bls.gov/data/inflation_calculator.htm) and is stored in data/inflation.

***For example, a Barbadian player who has never won an ATP point but has played for their national team has ATP tour level wins/losses according to the ATP website but this is not indicative of anything other than the fact they were selected to play for their country.

****Because only the top 750 singles players and top 250 doubles players are analyzed, in theory a top 750 singles player could be the 251st or lower ranked doubles player meaning that their doubles prize money is not included (or vice versa with a top 250 doubles player and 751st or lower ranked singles player). Although not ideal to be missing this data, the prize money at these levels is very minimal and not material for this analysis.

*****As not every single match from all tournaments is encapsulated by analyzing the top 750 singles and top 250 doubles players, there is some lost data, but this is inconsequential due to the shear volume of data collected and by averaging the results.
