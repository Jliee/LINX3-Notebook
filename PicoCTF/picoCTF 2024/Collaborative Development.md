# Collaborative Development

AUTHOR: JEFFERY JOHN

#### Description
___
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)

#### Soln
___

Unzip the file:
```
> unzip challenge.zip

Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample
  inflating: drop-in/.git/hooks/commit-msg.sample
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample
  inflating: drop-in/.git/hooks/post-update.sample
  inflating: drop-in/.git/hooks/pre-applypatch.sample
  inflating: drop-in/.git/hooks/pre-commit.sample
  inflating: drop-in/.git/hooks/pre-merge-commit.sample
  inflating: drop-in/.git/hooks/pre-push.sample
  inflating: drop-in/.git/hooks/pre-rebase.sample
  inflating: drop-in/.git/hooks/pre-receive.sample
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample
  inflating: drop-in/.git/hooks/update.sample
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
  inflating: drop-in/.git/refs/heads/main
   creating: drop-in/.git/refs/heads/feature/
 extracting: drop-in/.git/refs/heads/feature/part-1
 extracting: drop-in/.git/refs/heads/feature/part-2
 extracting: drop-in/.git/refs/heads/feature/part-3
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD
  inflating: drop-in/.git/config
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a
   creating: drop-in/.git/objects/eb/
 extracting: drop-in/.git/objects/eb/4de2a9826332633c62e44a1a130d9b1a88171a
   creating: drop-in/.git/objects/6e/
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c
   creating: drop-in/.git/objects/ad/
 extracting: drop-in/.git/objects/ad/37f59bfdcb1e8052bf7e12e1d89a2adb315cf9
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258
   creating: drop-in/.git/objects/97/
 extracting: drop-in/.git/objects/97/92a89fa347abc711f84b7208db18d164d45aca
   creating: drop-in/.git/objects/78/
 extracting: drop-in/.git/objects/78/ac69cf187e7a72fcd8750f3d7435e807f4a61a
   creating: drop-in/.git/objects/50/
 extracting: drop-in/.git/objects/50/d2c5d928a5b377e0d75093b113707e21ca36d9
   creating: drop-in/.git/objects/13/
 extracting: drop-in/.git/objects/13/08521d0d0b66df1a73e91d5d9e2d74610002e3
  inflating: drop-in/.git/index
 extracting: drop-in/.git/COMMIT_EDITMSG
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1
  inflating: drop-in/.git/logs/refs/heads/feature/part-2
  inflating: drop-in/.git/logs/refs/heads/feature/part-3
  inflating: drop-in/flag.py
```

Check the file:
```
cat drop-in/flag.py
print("Printing the flag...")```
```

Check the other heads to get the commit id:
```
> cat drop-in/.git/refs/heads/feature/part-3
1308521d0d0b66df1a73e91d5d9e2d74610002e3

> cat drop-in/.git/refs/heads/feature/part-2
9792a89fa347abc711f84b7208db18d164d45aca

> cat drop-in/.git/refs/heads/feature/part-1
ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9
```

Get the different commits content:
```
> git checkout ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9 && cat flag.py

Previous HEAD position was 9792a89 add part 2
HEAD is now at ad37f59 add part 1
print("Printing the flag...")

print("picoCTF{t3@mw0rk_", end='')%


> git checkout 9792a89fa347abc711f84b7208db18d164d45aca && cat flag.py

HEAD is now at 9792a89 add part 2
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')%


> git checkout 1308521d0d0b66df1a73e91d5d9e2d74610002e3 && cat flag.py

HEAD is now at 1308521 add part 3
print("Printing the flag...")

print("w0rk_e4b79efb}")
```

I just copy pasted the parts of the flag hehe:
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_e4b79efb}
```

