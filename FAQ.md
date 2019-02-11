# FAQ

**Q:** The DDNSS dashboard shows old IP address(es) but won't get updated by new one(s).

**A:** Delete the `vXupdate.txt` file(s) from working directory. This will force the script to update the IP address(es) during its next run.

```
$ (sudo) rm /path/to/ddnss/v*
```

Example:
```
$ (sudo) rm /usr/local/bin/ddnss/v*
```
