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
