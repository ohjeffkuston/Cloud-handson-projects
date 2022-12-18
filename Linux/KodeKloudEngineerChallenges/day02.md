<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Create a Linux User with non-interactive shell
Create a new Linux user with a non-interactive shell. As in the Linux user cannot interact with the shell. Ok—seems pretty straight forward. Here's my thought process to get this completed.

## The Dig 

-  ♾️ Dig 1 > [First Off What's Interactive vs. Non-interactive?](https://www.baeldung.com/linux/interactive-non-interactive-login-non-login-shells)
-  ♾️ Dig 2 > [Let's login to the server in question](https://www.servermania.com/kb/articles/ssh-linux/)
-  ♾️ Dig 3 > [How to Switch Users on Linux](https://devconnected.com/how-to-change-user-on-linux/)
-  ♾️ Dig 4 > [A Good Thread on Creating A Non-interactive Linux User](https://kodekloud.com/community/t/create-a-linux-user-with-non-interactive-shell-guide/10369/5)
-  ♾️ Dig 5 > [Helpful StackExchange Thread on the Matter](https://unix.stackexchange.com/questions/4676/creating-a-user-who-cannot-get-an-interactive-shell)

## What I Ultimately Did

```bash
#log into the applicable server
ssh username@ip_address
```
```bash
#create the new Linux user w/interactive shell
sudo useradd username -s /sbin/nologin
```
```bash
#verify the new Linux user has an non-interactive shell
su <user>
```

[< prev Day 1](day01.md)  |  [Home](../../..)  |  [Day 3 next >](day03.md)
