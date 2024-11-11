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