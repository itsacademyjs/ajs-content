# Exercise 1

Assume a table with the following data.

name            continent	  area	    population	gdp
Afghanistan	    Asia	      652230	    25500100	20343000000
Albania	        Europe	    28748	    2831741	    12960000000
Algeria	        Africa	    2381741	    37100000	188681000000
Andorra	        Europe	    468	        78115	    3712000000
Angola	        Africa	    1246700	    20609294	100990000000
...

1. The example uses a WHERE clause to show the population of 'France'. Note that strings (pieces of text that are data) should be in 'single quotes';


Modify it to show the population of Germany

SELECT population FROM world
  WHERE name = 'France'

2. Checking a list The word IN allows us to check if an item is in a list. The example shows the name and population for the countries 'Brazil', 'Russia', 'India' and 'China'.

Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.

SELECT name, population FROM world
  WHERE name IN ('Brazil', 'Russia', 'India', 'China');

3. Which countries are not too small and not too big? BETWEEN allows range checking (range specified is inclusive of boundary values). The example below shows countries with an area of 250,000-300,000 sq. km. Modify it to show the country and the area for countries with an area between 200,000 and 250,000.

SELECT name, area FROM world
  WHERE area BETWEEN 250000 AND 300000

# Exercise 2

Assume a table with the following data.

name	        continent
Afghanistan	    Asia
Albania	        Europe
Algeria	        Africa
Andorra	        Europe
Angola	        Africa
....

1. You can use WHERE name LIKE 'B%' to find the countries that start with "B".

The % is a wild-card it can match any characters
Find the country that start with Y

SELECT name FROM world
  WHERE name LIKE 'F%'

2. Find the countries that end with y

SELECT name FROM world
  WHERE name LIKE 'T%'

3. Luxembourg has an x - so does one other country. List them both.

Find the countries that contain the letter x

SELECT name FROM world
  WHERE name LIKE 'T%'

4. Iceland, Switzerland end with land - but are there others?

Find the countries that end with land

SELECT name FROM world
  WHERE name LIKE 'T%'

5. Columbia starts with a C and ends with ia - there are two more like this.

Find the countries that start with C and end with ia

SELECT name FROM world
  WHERE name LIKE 'T%'

6. Greece has a double e - who has a double o?

Find the country that has oo in the name

SELECT name FROM world
  WHERE name LIKE '%ee%'

7. Bahamas has three a - who else?

Find the countries that have three or more a in the name

SELECT name FROM world
  WHERE name LIKE 'T%'

8. India and Angola have an n as the second character. You can use the underscore as a single character wildcard.

SELECT name FROM world
 WHERE name LIKE '_n%'
ORDER BY name
Find the countries that have "t" as the second character.

SELECT name FROM world
 WHERE name LIKE '_n%'
ORDER BY name

9. Lesotho and Moldova both have two o characters separated by two other characters.

Find the countries that have two "o" characters separated by two others.

SELECT name FROM world
 WHERE name LIKE '_n%'

10. The capital of Luxembourg is Luxembourg. Show all the countries where the capital is the same as the name of the country

Find the country where the name is the capital city.

SELECT name, capital, continent
  FROM world
 WHERE name LIKE '%x%'

11. The capital of Mexico is Mexico City. Show all the countries where the capital has the country together with the word "City".

Find the country where the capital is the country plus "City".

The concat function

SELECT name, concat(name, 'town')
  FROM world
 WHERE name LIKE '%ina%'


# Exercise 3

Assume a table with the following data.

name            continent	area	    population	gdp
Afghanistan	    Asia	    652230	    25500100	20343000000
Albania	        Europe	    28748	    2831741	    12960000000
Algeria	        Africa	    2381741	    37100000	188681000000
Andorra	        Europe	    468	        78115	    3712000000
Angola	        Africa	    1246700	    20609294	100990000000
...

1. List each country name where the population is larger than that of 'Russia'.

2. Show the countries in Europe with a per capita GDP greater than 'United Kingdom'.

3. List the name and continent of countries in the continents containing either Argentina or Australia. Order by name of the country.

4. Which country has a population that is more than Canada but less than Poland? Show the name and the population.

5. Germany (population 80 million) has the largest population of the countries in Europe. Austria (population 8.5 million) has 11% of the population of Germany.

Show the name and the population of each country in Europe. Show the population as a percentage of the population of Germany.

The format should be Name, Percentage for example:

name	percentage
Albania	3%
Andorra	0%
Austria	11%
...	...

6. Which countries have a GDP greater than every country in Europe? [Give the name only.] (Some countries may have NULL gdp values)

7. Find the largest country (by area) in each continent, show the continent, the name and the area:

8. List each continent and the name of the country that comes first alphabetically.

9. Find the continents where all countries have a population <= 25000000. Then find the names of the countries associated with these continents. Show name, continent and population.

10. Some countries have populations more than three times that of any of their neighbours (in the same continent). Give the countries and continents.

# Exercise 4

Assume the following tables

game
id	mdate	stadium	team1	team2
1001	8 June 2012	National Stadium, Warsaw	POL	GRE
1002	8 June 2012	Stadion Miejski (Wroclaw)	RUS	CZE
1003	12 June 2012	Stadion Miejski (Wroclaw)	GRE	CZE
1004	12 June 2012	National Stadium, Warsaw	POL	RUS
...

goal
matchid	teamid	player	gtime
1001	POL	Robert Lewandowski	17
1001	GRE	Dimitris Salpingidis	51
1002	RUS	Alan Dzagoev	15
1002	RUS	Roman Pavlyuchenko	82
...

eteam
id	teamname	coach
POL	Poland	Franciszek Smuda
RUS	Russia	Dick Advocaat
CZE	Czech Republic	Michal Bilek
GRE	Greece	Fernando Santos
...

1. The first example shows the goal scored by a player with the last name 'Bender'. The * says to list all the columns in the table - a shorter way of saying matchid, teamid, player, gtime

Modify it to show the matchid and player name for all goals scored by Germany. To identify German players, check for: teamid = 'GER'

SELECT * FROM goal 
  WHERE player LIKE '%Bender'

2. From the previous query you can see that Lars Bender's scored a goal in game 1012. Now we want to know what teams were playing in that match.

Notice in the that the column matchid in the goal table corresponds to the id column in the game table. We can look up information about game 1012 by finding that row in the game table.

Show id, stadium, team1, team2 for just game 1012

SELECT id,stadium,team1,team2
  FROM game

3. You can combine the two steps into a single query with a JOIN.

SELECT *
  FROM game JOIN goal ON (id=matchid)
The FROM clause says to merge data from the goal table with that from the game table. The ON says how to figure out which rows in game go with which rows in goal - the matchid from goal must match id from game. (If we wanted to be more clear/specific we could say
ON (game.id=goal.matchid)

The code below shows the player (from the goal) and stadium name (from the game table) for every goal scored.

Modify it to show the player, teamid, stadium and mdate for every German goal.

SELECT player,stadium
  FROM game JOIN goal ON (id=matchid)

4. Use the same JOIN as in the previous question.

Show the team1, team2 and player for every goal scored by a player called Mario player LIKE 'Mario%'

5. The table eteam gives details of every national team including the coach. You can JOIN goal to eteam using the phrase goal JOIN eteam on teamid=id

Show player, teamid, coach, gtime for all goals scored in the first 10 minutes gtime<=10

SELECT player, teamid, gtime
  FROM goal 
 WHERE gtime<=10

 6. To JOIN game with eteam you could use either
game JOIN eteam ON (team1=eteam.id) or game JOIN eteam ON (team2=eteam.id)

Notice that because id is a column name in both game and eteam you must specify eteam.id instead of just id

List the dates of the matches and the name of the team in which 'Fernando Santos' was the team1 coach.

7. List the player for every goal scored in a game where the stadium was 'National Stadium, Warsaw'

8. The example query shows all goals scored in the Germany-Greece quarterfinal.
Instead show the name of all players who scored a goal against Germany.

SELECT player, gtime
  FROM game JOIN goal ON matchid = id 
    WHERE (team1='GER' AND team2='GRE')

9. Show teamname and the total number of goals scored.

SELECT teamname, player
  FROM eteam JOIN goal ON id=teamid
 ORDER BY teamname

10. Show the stadium and the number of goals scored in each stadium.

11. For every match involving 'POL', show the matchid, date and the number of goals scored.

SELECT matchid,mdate, team1, team2,teamid
  FROM game JOIN goal ON matchid = id 
 WHERE (team1 = 'POL' OR team2 = 'POL')

12. For every match where 'GER' scored, show matchid, match date and the number of goals scored by 'GER'

13. List every match with the goals scored by each team as shown. This will use "CASE WHEN" which has not been explained in any previous exercises.

mdate	team1	score1	team2	score2
1 July 2012	ESP	4	ITA	0
10 June 2012	ESP	1	ITA	1
10 June 2012	IRL	1	CRO	3
...
Notice in the query given every goal is listed. If it was a team1 goal then a 1 appears in score1, otherwise there is a 0. You could SUM this column to get a count of the goals scored by team1. Sort your result by mdate, matchid, team1 and team2.

SELECT mdate,
  team1,
  CASE WHEN teamid=team1 THEN 1 ELSE 0 END score1
  FROM game JOIN goal ON matchid = id