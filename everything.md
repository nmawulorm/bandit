Bandit 1
---------------------------
bandit1 password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
Bandit host: bandit.labs.overthewire.org

Bandit 2
---------------------------
bandit2 password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
### I had to specify the full path to the dash directory. So in this case , I specified ./- to be able to open the - file. 

Bandit 3
---------------------------
# Spaces in this file name 
This file had spaces in it's and so I had to put backward slash before each space in the file name. An easier way to do this was to press the tab key for suggestion for the file names. This made it easier.
The password is MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Bandit 4
---------------------------
# Bandit 4
There was a hidden file called ...Hiding-From-You in the inhere directory.
I used the 'ls -al' command to list all items in the directory includeincluding hidden ones vertically.
The password is 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
Actually, what displayed the hidden file was the -a in the ls -al

Bandit 5
---------------------------
# Bandit 5
Finding the password in bandit 5 was quiet interesting. Apperently, there were files preceeding with -file0 which actually means that I had to access them with the full path name and that is ./ There was another interesting thing and that is I was to go through about 10 files to get the password. This made me learn how to write loops in bash. I saw a number of them, but i prefered the 
```bash
for i in {0..9}; do
cat ./-file0$i
echo ""
done
```
The found password was 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Bandit 6
---------------------------
# Bandit 6
I went through multiple challenges to be able to read all files in each directory
I used a loop from 1-9. In the loop I made headings using echo and I used ls -al to list items in the each directory but filtered them with | grep using the file size
The password is HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Bandit 7
---------------------------
# Bandit 7
I had to study how to find a file based on the user owners and the group. I also learn about the size, but didn't put it to use. 
The password is morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
The command is used was 
```bash
find / -user bandit7 -group bandit6 2>/dev/null
```

I could have also added -size 33c to specify it is in bytes. The 2>/dev/null means that it should ignore permission errors

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
Bandit 8
---------------------------
# Bandit 8
I used grep to find the whole lined
The password is dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Bandit 9
---------------------------
# Bandit 9

I run [ls -al] to be able to view all files in the directory. I then run a sort on the lines of text. I finally filtered with [uniq -u]. This is what the final code looked like:
```bash
sort data.txt | uniq -u
```
The password is 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM


Bandit 10
---------------------------
# Bandit 10

This was a little challenging since I couldn't find a straight command to find other characters like the = sign.

So I used the cat command to display the content of data.txt, then I used the find command to search for strings with multiple = signs.

The password is FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Bandit 11
---------------------------
# Bandit 11

I used cat to display the content of data.txt. This is actually my first time seeing a base64 text. After a lttle research, I found that using `--decode` with the `base64` will be my solution

This is the password dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

Bandit 12
---------------------------
# Bandit 12

I rotated the Alphabets 13 times after viewing the with cat. I used `tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt`

The password was 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

Bandit 13
---------------------------
# Bandit 13

This was really a tough one. I had to get assistance from https://mayadevbe.me/posts/overthewire/bandit/level13/

The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

Bandit 14
---------------------------
# Bandit 14

I used ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220 to be able to log into the network.

To get the sshkey.private file, i used `scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .` to save the file to my PC

I had to also use `chmod 700 sshkey.private` to reduce the permissions



Bandit 15
---------------------------
# Bandit 15
First, I have to extract the password for bandit 14 from `/etc/bandit_pass/bandit14`. So I used the cat command for that. 
So the password is MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

Secondly, I had to submit password to the localhost on port 30000. I did this using the nc command. 
So the password for bandit15 is 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo


Bandit 16
---------------------------
# Bandit 16

This is particular activity requried me to read about openssl

It is used for many cryptrographic activities. I connected to the server using `openssl s_client -connect localhost:30001`


The password for bandit16 is kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Bandit 17
---------------------------
# Bandit 17

I had to discover all open ports and the services running on the server from 31000 to 32000.

I discovered five open ports with nmap, two of which were ssl and port 31790/tcp was ssl and running an unkown service

I then used `ncat --ssl localhost 31790` and the current user password to view the private key.

The ssh was:

--Add start here
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
--and end here

Bandit 18
---------------------------
# Bandit 18

I created a private key called sshkey17.private and I used it to access the bandit 17 using `ssh -i ~/Source/bandit/sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220`.
But first, I changed the privillege using `chmod 700 sshkey17.private`

This logged me in to bandit 18.

Then I used `diff` to find the only difference between the two files

The password is x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO


Bandit 19
---------------------------
# Bandit 19

Anytime I logged into bandit18, I got logged out. But like the hint suggested, I can access the password to bandit 19 in the home directory. 

This made me learn how to execute a command through SSH wihtout actually staying logged in. 

I finally used `ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat ~/readme"`

The password was cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8


Bandit 20
---------------------------
# Bandit 20

At this level, I was a little overwhealed. I got to learn that since I had permission to execute bandit20-do as a bandit19 user, it means, I could use it to access the files in the /etc/bandit_pass directory.

I used `./bandit20-do ls /etc/bandit_pass/` to list the items and `/bandit20-do cat /etc/bandit_pass/bandit20` to display the password's content.

The password for bandit 20 is 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO


