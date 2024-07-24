
# Binary Search

AUTHOR: JEFFERY JOHN
#### Description
____
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/18/challenge.zip)

#### Soln
___
run the guessing game file within the path home/ctf-player/drop-in/:
```
./guessing_game.sh
```

Since this is random number, starting guessing at the middle. It'll easily give you the idea on what range the random number belongs to. Sample:

```
Welcome to the Binary Search Game!

I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
// your range is now 500-1000, get the mid

Enter your guess: 750
Higher! Try again.
// your range is now 750-1000

Enter your guess: 875
Lower! Try again.
//your range is now 750 - 875

Enter your guess: 800
Lower! Try again.
//your range is now 750-800

Enter your guess: 775
Lower! Try again.
//your range is now 750-775

Enter your guess: 760
Higher! Try again.
//your range is now 760-775

Enter your guess: 765
Lower! Try again.
//your range is now 760-765

Enter your guess: 763
Lower! Try again.

Enter your guess: 762
Lower! Try again.

Enter your guess: 761

Congratulations! You guessed the correct number: 761

Here's your flag: picoCTF{g00d_gu355_2e90d29b}
```

