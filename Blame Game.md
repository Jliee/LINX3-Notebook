# Blame Game

AUTHOR: JEFFERY JOHN

#### Description
___
Someone's commits seems to be preventing the program from working. Who is it?

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/157/challenge.zip)

#### Soln
___

Git [whatchanged](https://git-scm.com/docs/git-whatchanged)
```
> git whatchanged

commit 2466febd40004b9ca644ce924181d07e23dcfaeb
Author: picoCTF{@sk_th3_1nt3rn_cfca95b2} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:06 2024 +0000

    optimize file size of prod code

:100644 100644 7df869a 326544a M        message.py

commit 05f26d123cde97b714aaae28ba8f18db3f385af5
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:06 2024 +0000

    create top secret project

:000000 100644 0000000 7df869a A        message.py
```