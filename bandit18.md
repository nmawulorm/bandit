# Bandit 18

I created a private key called sshkey17.private and I used it to access the bandit 17 using `ssh -i ~/Source/bandit/sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220`.
But first, I changed the privillege using `chmod 700 sshkey17.private`

This logged me in to bandit 18.

Then I used `diff` to find the only difference between the two files

The password is x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

