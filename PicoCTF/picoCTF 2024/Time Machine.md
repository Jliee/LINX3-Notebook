# Time Machine

#picoCTF2024 #Easy #GeneralSkills #git #browser_webshell_solvable 

AUTHOR: JEFFERY JOHN
#### Description
___
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)

#### Soln
___
View the file:
```
> cat message.txt

This is what I was working on, but I'd need to look at my commit history to know why...%
```

The hint is looking at commit history:
```
> ls -a
.           ..          .git        message.txt

> cd .git
> ls
COMMIT_EDITMSG 
HEAD           
branches       
config         
description    
hooks          
index          
info           
logs           
objects        
refs
```

Inspect the commi_editmsg file:
```
> cat COMMIT_EDITMSG
picoCTF{t1m3m@ch1n3_186cd7d7}
```
