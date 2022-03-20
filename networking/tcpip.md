`ping` - Can be used for a basic health check of the private network, public network / internet connection, and health of a remote server. Primarily this tool returns the time it took to travel round-trip to the remote server and back.

You can potentially find out some information about the destination site - `ping` `cbc.ca` and you can see they use Akamai as a CDN.

References:
[Linux.de](https://linux.die.net/man/8/ping)
[Linuxize](https://linuxize.com/post/linux-ping-command/)

-----

`traceroute` -  Tracking the route packets traverse to arrive at a remote server always leads me down a fun path of the different companies that comprise the internet...

-----

`dig` - Gather information from DNS nameservers, primarily the IP address of the domain and the address of the authoritative nameservers themselves.

```
$ san.cbc.ca.edgekey.net.
e5220.e12.akamaiedge.net.
23.73.183.79

$ dig +short www.cbc.ca NS
san.cbc.ca.edgekey.net.
e5220.e12.akamaiedge.net.
```

References:
[willem.com](https://willem.com/blog/2019-05-24_dig-for-dummies/)

-----

`nslookup` - Another option to gather information in the DNS nameserver world, with the option of an interactive mode. Either mode allows you to specify the nameserver to use.

```
$ nslookup www.cbc.ca
Server:		127.0.0.53
Address:	127.0.0.53#53

Non-authoritative answer:
www.cbc.ca	canonical name = san.cbc.ca.edgekey.net.
san.cbc.ca.edgekey.net	canonical name = e5220.e12.akamaiedge.net.
Name:	e5220.e12.akamaiedge.net
Address: 23.73.183.79
```
