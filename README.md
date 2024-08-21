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
### traceroute
