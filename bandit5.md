# Bandit 5
Finding the password in bandit 5 was quiet interesting. Apperently, there were files preceeding with -file0 which actually means that I had to access them with the full path name and that is ./ There was another interesting thing and that is I was to go through about 10 files to get the password. This made me learn how to write loops in bash. I saw a number of them, but i prefered the 
```bash
for i in {0..9}; do
cat ./-file0$i
echo ""
done
```
The found password was 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
