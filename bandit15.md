# Bandit Level x to y Writeup

Author: [Samarth Arora](https://github.com/namangup)

Problem Page: [bandit15](https://overthewire.org/wargames/bandit/bandit16)

## List of Commands Used
```
exit
ls - list files in a directory
openssl
s_client
```

## Walkthrough
After logging on to the server and suffering i mean searching through the man pages, I used the ssl encryption and connect to da port 30001 and enter this pass to recieve the password for next level.

## Password
`cluFn7wTiGryunymYOu4RcffSxQluehd`

## Bash/Python script to automate the process
```
#!/usr/bin/expect 
spawn ssh -p 2220 bandit15@bandit.labs.overthewire.org
expect "password:"
send -- "BfMYroe26WYalil77FoDi9qh59eK5xNr\r"
expect "$ "
send -- "openssl s_client -connect localhost:30001 \r"
expect " "
send -- "BfMYroe26WYalil77FoDi9qh59eK5xNr \r"
send -- "exit \r"
interact
```