<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Linux User Without Home
- [x] Install `cronie` on all 3 app servers
- [x] Ensure the `crond` service is started on all 3 app servers
- [x] Add a cron for the `root` user on all 3 app servers

## The Dig 

-  ♾️ Dig 1 > [How do I add a user in Linux without a home directory?](https://linuxhint.com/add-user-linux/)
-  ♾️ Dig 2 > [The Complete Guide to “useradd” Command in Linux – 15 Practical Examples](https://www.tecmint.com/add-users-in-linux/)
-  ♾️ Dig 3 > [How To: Create a New User Without a /home Directory](https://linux-tips.us/how-to-create-a-new-user-without-a-home-directory/)
-  ♾️ Dig 4 > [Useradd vs Adduser: What's the Difference?](https://linuxhandbook.com/useradd-vs-adduser/)
-  ♾️ Dig 5 > [adduser vs useradd in Linux](https://linuxconfig.org/add-user-linux-command)

## What I Ultimately Did

```bash
#create a user without a HOME directory
$ useradd -M <username>

#OR
$ useradd --no-create-home <username>
```

```bash
#verify the user was created without a home directory
$ ls -l /home/<username>




# **_OUTPUT_**
ls: cannot access /home/shilpi: No such file or directory
```

[< prev Day 6](day06.md)  |  [Home](../../..)  |  [Day 8 next >](day08.md)
