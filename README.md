# Robocopy-samples-I-used


/E => recurse
/XC => exclude existing files with same time stamp (whatever size)
/XN => exclude existing files newer than the source (whatever size)
/XO => exclude existing files older than the source (whatever size)

then since retry times is 1 million by default, we use /R:2 (2 retries) and /W:3 (3 seconds)

Also we excluded *.LOG files as there were a lot that we don't need to copy over

```powershell
Robocopy 'C:\Program Files\Microsoft\Exchange Server\V15' '\\RemoteServer01\c$\Program Files\Microsoft\Exchange Server\V15' /E /XC /XN /XO /R:2 /W:3 /XF *.log
```

