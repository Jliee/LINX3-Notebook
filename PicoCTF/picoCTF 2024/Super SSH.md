# Super SSH

#picoCTF2024 #Easy #GeneralSkills #shell #browser_webshell_solvable #ssh

AUTHOR: JEFFERY JOHN
#### Description
___

Using a Secure Shell (SSH) is going to be pretty important.

Additional details will be available after [launching your challenge instance](https://play.picoctf.org/practice/challenge/424?category=5&originalEvent=73&page=1)

Using a Secure Shell (SSH) is going to be pretty important.

Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `63973` to get the flag?You'll also need the password `6dd28e9b`. If asked, accept the fingerprint with `yes`.

If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell) 

#### Soln
___

```
ssh -l ctf-player -K titan.picoctf.net -p 63973
```

prompt:
```
The authenticity of host '[titan.picoctf.net]:51651 ([3.139.174.234]:51651)' can't be established.

ED25519 key fingerprint is SHA256:4S9EbTSS32I+cdM5TyzthpQryv5kudR7XQ.

This key is not known by any other names.

Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes

Warning: Permanently added '[titan.picoctf.net]:51651' (ED25519) to the list of known hosts.

ctf-player@titan.picoctf.net's password:

Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}

Connection to titan.picoctf.net closed.
```