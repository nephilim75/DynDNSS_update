# DynDNSS_update
Script is posting current IP addresses of a server or client to DynDNSService.

## Purpose
This setup is intendent to use with (private) hardware behind an account with changing IP addresses. To make the server or client available from internet. [DynDNS Service](https://ddnss.de) provides constant domain name even though your IP addresses are changing.

## Requirements
1. An account at [DynDNS Service](https://ddnss.de)
2. Created host and its host name.
3. Valid update key. You'll find it on DDNSS's dashboard on the left bottom corner.

## HowTo
1. Copy the script to a directory of your choice. E.g. `/usr/local/bin/ddnss`.
2. Add a cron job to `root`'s crontab to trigger the script.

```
*/10 * * * * /path/to/ddnss.sh > /dev/null 2>&1
```

**Example:**
```
*/10 * * * * /usr/local/bin/ddnss/ddnss.sh > /dev/null 2>&1
```

**That's it**
