# endianness

#picoCTF2024 #Easy #GeneralSkills #browser_webshell_solvable

AUTHOR: NANA AMA ATOMBO-SACKEY

#### Description
___

Know of little and big endian?

[Download Challenge here](https://artifacts.picoctf.net/c_titan/117/flag.c)

#### Soln
___

Running the c file will prompt this:
```
Welcome to the Endian CTF!

You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.

Word: wsvyy
```

[Endian](https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7) refers to the order in which bytes are stored for multi-byte data types, so we [convert](https://www.rapidtables.com/convert/number/ascii-to-hex.html) the word (ASCII) into Hexadecimal notation:

> "wsvyy" to  "77 73 76 79 79"

Little Endian will be written from left to right.
```
Enter the Little Endian representation: 7979767377
Correct Little Endian representation!
```

Big Endian will be written from right to left.

```
Enter the Big Endian representation: 7773767979
Correct Big Endian representation!
```

The flag:
```
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_25c5f083}
```

