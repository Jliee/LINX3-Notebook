# binhexa

AUTHOR: NANA AMA ATOMBO-SACKEY

#### Description
___
How well can you perfom basic binary operations?

Start searching for the flag by starting an [instance here](https://play.picoctf.org/practice/challenge/404?category=5&originalEvent=73&page=1)

`nc titan.picoctf.net 59418`

#### Soln
___

```
Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01011100
Binary Number 2: 10110010


Question 1/6:
Operation 1: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 10111000
Correct!

Question 2/6:
Operation 2: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01011001
Correct!

Question 3/6:
Operation 3: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0100001110
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111110
Correct!

Question 5/6:
Operation 5: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 011111111111000
Correct!

Question 6/6:
Operation 6: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00010000
Correct!

Enter the results of the last operation in hexadecimal: 10

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_1367e2c6}
```