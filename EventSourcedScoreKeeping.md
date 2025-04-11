# Event Sourced Score Keeping Kata

Event sourcing is a technique where we store all the events that happen rather than only keeping the current state.


## Objective

Use an append-only event log to write code to track the score for a team-based game, adding new reporting features as you go.

> **What Game?**
>
> For the purposes of this exercise, the specific game is not particularly important, so long as individual members of the team can score points, and the points can come in varying amounts (e.g. 1, 2, or 3 points at a time).
> 
> It could be a board game, a sport, or something else.


## Problem Description

### Part 1: Logging Scores

Create methods for scoring points and retrieving the current score for a team, for example:

```
scorePoints(team, points)
getCurrentScore(team)
```

Each time points are scored, your implementation should store the event data (which team & how many points) into some kind of in-memory data structure (such as a list or array).

The current score should be calculated by iterating the data structure rather than storing a single integer value.


### Part 2: Which Team is Leading?

Add a method which returns the name of the team that has the most points (and thus is currently ahead and closest to winning).
For example:

```
getLeadingTeam()
```

If both teams have the same total score, this method should return the string `"Tie"`.


### Part 3: Highest Scoring Player Per Team

Modify your implementation so that when points are scored, you also track which player scored those points.
Then add a method which returns the player who scored the most points for their team, such as:

```
getHighestScoringPlayer(team)
```

### Part 4: Top 5 Scoring Players

Add a method which returns data about the five players who have scored the most points during the game, ordered from high to low total points.

```
getTop5Players()
```


For each player, the returned data should include:
* Which player
* Which team they are on
* How many total points they've scored
* How many times they scored points


### Part 5: The 3-Point Scorers

Add a method to return all players who have achieved 3-point scores during the game. For example:

```
get3PointScorers()
```

For each player, the returned data should include:
* Which player
* Which team they are on
* How many times they got a 3-point score

The data should be ordered by the number of times they scored a 3-point score, from high to low.


### Part 6: Top Scorers in a Window

Add a method to return data about points scored by players
in a specific window of scoring events, such as the first 10 points scored.

```
getScoresInWindow(start, size)
```

Where `start` is the Nth time points were scored, and `size` is how many score events to consider (the size of the window).
Thus `getScoresInWindow(1, 10)` would yield the first 10 points scored in the game.

For each player, the returned data should include:
* Which player
* Which team
* The total points scored during the window
* The number of times they scored during the window


### Part 7: Reflect On Your Work

Think about the following questions:
* How did the constraint of event sourcing affect your code?
* How would your implementation be different if you didn't use event sourcing?
* Would some of the features have been more difficult with a naive implementation?
* Does event sourcing make it easier to add new or unexpected features over time?
* What domains could be a good fit for event sourcing?


## Testing Data

To verify your implementation, here is some test data provided in 2 formats:
* [JSON](./data/event-log.json)
* [CSV](./data/event-log.csv)

From this data you should find:
* Team `Space Fantasy` is leading 100 to 85.
* The top 5 scoring players data:
    * Kira scored 10 times for a total of 20 points
    * Leia scored 12 times for a total of 18 points
    * Worf scored 8 times for a total of 16 points
    * Vader scored 8 times for a total of 16 points
    * R2 scored 9 times for a total of 16 points
* The 3-point scorers and their shot counts are:
    * Kira 4
    * Worf 2
    * Vader 2
    * Obi-Wan 2
    * R2 1
    * Finn 1
    * Picard 1
    * McCoy 1
    * Dax 1
* The top scorers for the first 10 events (window start: 1, size: 10) are:
    * Vader scored 5 times for 10 points
    * Kira scored 1 time for 3 points
    * Worf scored 1 time for 3 points
    * Finn scored 1 time for 2 points
    * LaForge scored 1 time for 2 points
    * Dax scored 1 time for 1 point
* The top scorers for the 13 scoring events starting at the 55th (window start: 55, size: 13) are:
    * Obi-Wan scored 2 times for 5 points
    * Leia scored 3 times for 4 points
    * Fett scored 2 times for 3 points
    * Finn scored 1 time for 3 points
    * Picard scored 1 time for 3 points
    * McCoy scored 1 time for 3 points
    * R2 scored 1 time for 2 points
    * Worf scored 1 time for 2 points
    * Kira scored 1 time for 1 point

## Challenges

* Try building an implementation that does not use event sourcing.
    * Compare side-by-side with your event sourced version.
* Add a caching layer to speed up queries.
* Add other types of events in addition to points scored, such as:
    * time periods (e.g. `quarter-ended` or `half-time-reached`)
    * fouls
    * time-outs
* Try adding timestamp data so you can answer questions like, "Who had the best 5-minute hot streak?"
