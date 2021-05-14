# Bandit Level 13 to 14 Writeup

Author: [Samarth Arora](https://github.com/Samadeol)

Problem Page: [bandit13](https://overthewire.org/wargame/bandit/bandit13)

## List of Commands Used
```
ankur used everything pls ask him
ssh -i
cat
ls - list files in a directory
cd
```

## Walkthrough
I read the man pages. In that -i(identity file) selects a file from which the identity (private key) for RSA or DSA authentication is read which seemed perfect for this level.

## Password
`4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

## Bash/Python script to automate the process
```
#!/usr/bin/expect 
spawn ssh -p 2220 bandit13@bandit.labs.overthewire.org
expect "password:"
send -- "8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL\r"
expect "$ "
send -- "ssh -i sshkey.private bandit14@localhost \r"
expect "? "
send -- "yes\r"
send -- "cd ../../etc/bandit_pass/ \r"
send -- "cat bandit14 \r"
send -- "exit\r"
expect -- "$ "
send -- "exit\r"
interact
```

## Suggested modifications [Optional]
thx