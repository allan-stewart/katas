# Yahtzee Kata

(Adapted from http://codingdojo.org/cgi-bin/index.pl?KataYahtzee)

## Objective:

Create code that given five six-sided dice and a Yahtzee category will return the score.

Example: `int Score(string category, string[] dice)`

## Problem Description:

In Yahtzee the following categories exist:

* `Ones`, `Twos`, `Threes`, `Fours`, `Fives`, and `Sixes`: In these categories, the player scores the sum of the dice that match the category.
    * For example, 1, 4, 2, 4, 1 scored on "fours" scores 8 points.
* `Three of a kind`: If there are three dice with the same number, the player scores the sum of all the dice. Otherwise the player scores 0.
    * For example, 3, 4, 3, 3, 5 scored on "three of a kind" gives 18 points.
* `Four of a kind`: If there are four dice with the same number, the player scores the sum of all the dice. Otherwise the player scores 0.
    * For example, 2, 5, 2, 2, 2 scored on "four of a kind" gives 13 points.
* `Full house`: If the dice are a pair and a three of a kind, the player scores 25 points, otherwise 0.
    * For example, 1, 1, 2, 2, 2 placed on "full house" gives 8 points.
    * Note that 4, 4, 4, 4, 4 is not "full house" because the pair and three of a kind must be difference die values.
* `Small straight`: If four of the dice are in sequence (e.g. 1, 2, 3, 4), the player scores 30 points, otherwise 0.
    * For example: 1, 3, 4, 5, 6 scored on "small straight" gives 30 points, but 1, 2, 4, 5, 6 gives 0 points.
* `Large straight`: If all five dice are in sequence (e.g. 2, 3, 4, 5, 6), the player scores 40 points, otherwise 0.
* `Yahtzee`: If all dice are the have the same number, the player scores 50 points, otherwise 0.
* `Chance`: The player gets the sum of all dice, no matter what they read.

## Testing Considerations

Explore boundary cases such as: invalid categories, wrong number of dice, invalid dice values (e.g. 7)

## Challenges

* Add a second algorithm that returns the category which will yield the highest score for a given roll.
* Add additional categories, for example: "pair" or "two pair".
* Change how categories with fixed scores are calculated so they incorporate the values of the matching dice.
