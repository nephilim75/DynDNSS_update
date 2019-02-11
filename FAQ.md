# FAQ

**Q:** The DDNSS dashboard shows old IP address(es) but won't get updated by new one(s).

**A:** Delete the `vXupdate.txt` files from working directory. This will force the script to update the IP address(es) during its next run.

Example:
```
$ (sudo) rm /usr/local/bin/ddnss/v*
```
