# Rock-Paper-Scissors-Lizard-Spock Kata

What? [See the video on YouTube](https://www.youtube.com/watch?v=Kov2G0GouBw)


## Objective

Create a method that takes two inputs (e.g. scissors and Spock) and returns the proper result as per the rules below.

Example: `string getResult(string input1, string input2)`

The result should be in the format of `<winner> <verb> <loser>` ("Spock smashes scissors"), or in the case of a tie: `tie`.


## Problem Description

The rules of Rock-paper-scissors-lizard-Spock are:

* scissors cuts paper
* paper covers rock
* rock crushes lizard
* lizard poisons Spock
* Spock smashes scissors
* scissors decapitate lizard
* lizard eats paper
* paper disproves Spock
* Spock vaporizes rock
* rock crushes scissors


## Testing Considerations

After getting the basic algorithm working, try exploring boundary cases like:

* Invalid input


## Challenges

* Make the algorithm extensible so you can easily add yet another type
* Allow for more than two players
