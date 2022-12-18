<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Linux File Permissions
A bash script on one of the application servers needs executable permissions—that allow any user to execute the script.

## The Dig 

-  ♾️ Dig 1 > [How do I check a file's permission via terminal?](https://www.howtouselinux.com/post/check-file-permissions-in-linux)
-  ♾️ Dig 2 > [Setting up permissions on a script](https://bash.cyberciti.biz/guide/Setting_up_permissions_on_a_script)

## What I Ultimately Did

```bash
#log into the applicable server
ssh username@ip_address
```
```bash
#get my bearings
pwd

#verify the script in question is in fact present on the server
ls -l
```
<img src="../img/day4-1.png?raw=true" alt="Image 1" width="50%" height="50%" />

```bash
#attempt to set the desired permission
chmod 0755 </filepath/filename>

#received a "operation not permitted" response
```
<img src="../img/day4-2.png?raw=true" alt="Image 1" width="50%" height="50%" />

```bash
#tried again with sudo
sudo chmod 0755 </filepath/filename>
```
<img src="../img/day4-3.png?raw=true" alt="Image 1" width="50%" height="50%" />

```bash
#verify the appropriate permissions are set on the script file
ls -l </filepath/filename>
```
<img src="../img/day4-4.png?raw=true" alt="Image 1" width="50%" height="50%" />

## Fun Facts
My favorite way to learn AWS & DevOps is by breaking stuff in my home lab environment. Better there than on the job.

[< prev Day 3](day03.md)  |  [Home](../../..)  |  [Day 5 next >](day05.md)
