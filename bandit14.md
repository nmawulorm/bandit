# Bandit 14

I used ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220 to be able to log into the network.

To get the sshkey.private file, i used `scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .` to save the file to my PC

I had to also use `chmod 700 sshkey.private` to reduce the permissions


