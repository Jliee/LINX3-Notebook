# Commitment Issues
#picoCTF2024 #Easy #GeneralSkills #git #browser_webshell_solvable 

AUTHOR: JEFFERY JOHN
#### Description
___
I accidentally wrote the flag down. Good thing I deleted it! 

You download the challenge files here:

```
https://artifacts.picoctf.net/c_titan/75/challenge.zip
```

#### SOLN
_____

Current master has a message.txt file 
```
> > cat message.txt

TOP SECRET
```

Check the logs for commits
```
git log
```

You should see:
```
commit 3899edb7f3110d613c72ad40083fd8feeef703d0 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    remove sensitive info

commit 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    create flag
```

Copy the commit ID where the flag is created and check it out
```
git checkout 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
```

You should see
```
Note: switching to '6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 6603cb4 create flag
```

HEAD is now at 6603cb4 create flag, so cat the file again
```
> > cat message.txt
picoCTF{s@n1t1z3_9539be6b}
```

