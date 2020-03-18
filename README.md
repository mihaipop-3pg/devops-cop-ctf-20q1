
## Abstract

This is meant as a fun exercise into the importance of securing your stuff. Your agility is important, but your stuff is [importanter](https://www.urbandictionary.com/define.php?term=Importanter).
Knowing about Linux systems and how to run inside them is essential, as [most systems have some kind of Linux distribution under their hood](https://unix.stackexchange.com/questions/85308/whats-the-approximate-percentage-of-linux-servers-in-the-world) and operational excellence is not an ops problem, but [the goal of the entire team](https://twitter.com/mipsytipsy/status/992878988828721152).

This game is aimed at absolute beginners. Like any other [Jeopardy-style Capture The Flag game](https://www.reddit.com/r/securityCTF/comments/5nboxz/what_are_jeopardy_ctfs/), it’s organized in levels. You start at level 0 and at each level have to find the credentials for the next.


## CTF Readiness

Throughout our DevOps CoP sessions this quarter of 2020:
- We’ve talked about hardening servers and containers,
- Navigating the Linux terminal and filesystem,
- Using shell scripts to ease up our work,
- Understand basic networking concepts like DNS and SSH,
- And use them in our Linux systems
- And, finally, securing our containers and servers and showing what happens when we don’t (ಥ⌣ಥ)

## What do you need?

Make sure to bring your wits with you. If you get stuck, it’s perfectly fine. There are 7 days (no need to show this tape to someone else, fyi) and tons of resources available, like the help pages shipped with each Linux distro, the [DevOps CoP slide deck](https://github.com/3PillarGlobal/devops-cop), and, well, the entirety of the internet!
Remember, if you don’t know or remember something, [man](http://www.linfo.org/man.html) is your friend and --help is your trusted side-kick.

### Connection details
To access the server, create a Pull Request adding your SSH public key in the [public-keys](https://github.com/bogdanbarna/devops-cop-ctf-20q1/blob/master/public-keys/) directory.

After that has been approved and merged, connect to the 3PG VPN, you may access to the server and have fun:
```
ssh -i <your-private-key> fork1@ec2-3-121-184-179.eu-central-1.compute.amazonaws.com
```

To access the next level,
```
su - fork2
```

![alt text](https://media.giphy.com/media/RyXVu4ZW454IM/giphy.gif "hackerman")

## Levels

### [L0 → L1]

Description: Welcome! To connect add your SSH public key to this repository and then use the private key to connect. (Also see Connection details.)

Username: fork1

Useful commands for this level: ssh. 


### [L1 → L2]

Description: No files in the user home directory. This is an entirely different environment.

Username: fork2

Useful commands for this level: printenv 


### [L2 → L3]

Description: No visible files in the user home directory. The password is around here, though.

Username: fork3

Useful commands for this level: ls, find 


### [L3 → L4]

Description: The password is in the badly-named file.

Username: fork4

Useful commands for this level: cat 


### [L4 → L5]

Description: The password is a file inside this directory, but all lowercase j characters have been replaced by ! characters.

Username: fork5

Useful commands for this level: tr 


### [L5 → L6]

Description: No one likes reading logs, but everyone loves understanding logs during outages.

Username: fork6

Useful commands for this level: less, view, cat, grep 


### [L6 → L7]

Description: At this level, the password is inside ~/mail. There are multiple “password: <string>” lines, you have to find the one that’s only mentioned once.

Username: fork7

Useful commands for this level: grep, cut, sort 


### [L7 → L8]

Description: There is a cron job that sets up the password for the next user.

Username: fork8

Useful commands for this level: crontab, ls, cat 


### [L8 → L9]

Description: The SSH password was once part of the git repository in this directory, find it.

Username: fork9

Useful commands for this level: git 


### [L9 → L10]

Description: User rikrok has access to fork12’s password. Impersonate rikrok.

Username: fork10

Useful commands for this level: N/A. 


### [L10 → L11]

Description: The file containing the SSH password has been compressed multiple times. Get to the bottom of this!

Username: fork11

Useful commands for this level: tar, gzip, bzip, zip. 


### [L11 → L12]

Description: It's all coming together... In the current directory is an archived git repository. One of the git commits has the password. Find it.

Username: fork12

Useful commands for this level: zip, tar, gzip, bzip, git. 
