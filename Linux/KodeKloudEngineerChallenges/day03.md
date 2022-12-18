<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Linux Time Zones Setting
Set the **Application Servers'** timezone to **Pacific/Chuuk** using _Linux Commands_ and the _terminal_.

## The Dig 

-  ♾️ Dig 1 > [List of UTC Offsets](https://en.wikipedia.org/wiki/List_of_UTC_offsets)
-  ♾️ Dig 2 > [How To Set or Change Time Zone Using Linux](https://www.key2goal.com/article/how-set-or-change-time-zone-linux)

## What I Ultimately Did

```bash
#log into one of the application servers
ssh username@ip_address
```
```bash
#verify the current timezone of the server
timedatectl
```
_Output:_
<p align="left">
 <img src="../img/timezone.png?raw=true" alt="Timezone Check" width="50%" height="50%" />
</p>

```bash
#list the timezones the server supports
timedatectl list-timezones
```
_Output:_
```bash
$ timedatectl list-timezones
Africa/Abidjan
Africa/Accra
Africa/Addis_Ababa
Africa/Algiers
Africa/Asmara
Africa/Bamako
Africa/Bangui
Africa/Banjul
Africa/Bissau
Africa/Blantyre
Africa/Brazzaville
Africa/Bujumbura
Africa/Cairo
Africa/Casablanca
Africa/Ceuta
Africa/Conakry
Africa/Dakar
Africa/Dar_es_Salaam
Africa/Djibouti
Africa/Douala
Africa/El_Aaiun
Africa/Freetown
Africa/Gaborone
Africa/Harare
Africa/Johannesburg
[more]
```
```bash
#set each applicable application server's timezone to Pacific/Chuuk
sudo timedatectl set-timezone Pacific/Chuuk
```
```bash
#verify the server's timezone change
timedatectl
```

## Fun Facts
God Of War: Ragnarok was played heavily in between completing DevOps labs.

[< prev Day 2](day02.md)  |  [Home](../../..)  |  [Day 4 next >](day04.md)
