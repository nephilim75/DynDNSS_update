# DynDNSS_update
Script is posting current IP addresses of a server or client to [DynDNSService](https://ddnss.de).

## Purpose
This setup is intendent to be used with (private) hardware behind an ISP account with changing IP addresses. This helps to make the server or client available from internet. [DynDNS Service](https://ddnss.de) (DDNSS) provides constant domain name even though your IP addresses are changing.

The simple but robust scripts are logging all events with meaningful and understandable comments and are doing checks against the DDNSS server to ensure the update success.

Our scripts support [IPv4](https://github.com/nephilim75/DynDNSS_update/blob/master/scripts/IPv4%20only) only, [IPv6](https://github.com/nephilim75/DynDNSS_update/blob/master/scripts/IPv6%20only) only and both [IPv4&IPv6](https://github.com/nephilim75/DynDNSS_update/blob/master/scripts/Dualstack%20(IPv4%20%26%20IPv6)) (DualStack).

## Requirements
1. An account at [DynDNS Service](https://ddnss.de).
2. Created host and its **host name**.
3. Valid **update key**. You'll find it on DDNSS's dashboard on the left bottom corner.

## HowTo
**1.** Copy the script to a directory of your choice. E.g. `/usr/local/bin/ddnss`.</br>
**2.** Give the script you've choosen the name `ddnss.sh` and paste the copied content into it.
```
$ (sudo) nano /path/to/ddnss/ddnss.sh
```

Example:
```
$ (sudo) nano /usr/local/bin/ddnss/ddnss.sh
```

**3.** Make `ddnss.sh` executable for `root`.
```
$ (sudo) chown root:root /path/to/ddnss/ddnss.sh
$ (sudo) chmod u+x /path/to/ddnss/ddnss.sh
```

Example:
```
$ (sudo) chown root:root /usr/local/bin/ddnss/ddnss.sh
$ (sudo) chmod u+x /usr/local/bin/ddnss/ddnss.sh
```

**4.** Update the scripts according to your needs.

```
# Define variables DDNSS (user input)
KEYAUTH="UpdateKey provided by DDNSS"
HOST="host.name.tld"
WDIR="/path/to/ddnss"
```

Example:
```
# Define variables DDNSS (user input)
KEYAUTH="ljaeirio3v536ijuagfiu"
HOST="myserver.ddnss.org"
WDIR="/usr/local/bin/ddnss"
```


**5.** Add a cron job to `root`'s crontab to trigger the script.

```
*/10 * * * * /path/to/ddnss.sh > /dev/null 2>&1
```

Example:
```
*/10 * * * * /usr/local/bin/ddnss/ddnss.sh > /dev/null 2>&1
```

**That's it**.
