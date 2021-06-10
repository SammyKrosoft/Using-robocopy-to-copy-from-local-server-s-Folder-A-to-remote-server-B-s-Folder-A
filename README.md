# Using robocopy to copy missing files from local server's FolderA to a remote server's Folder A

Where Folder A = C:\Program Files\Microsoft\Exchange Server\V15

and we copy on remote server Folder A = \\RemoteServer01\c$\Program Files\Microsoft\Exchange Server\V15

We want the following options:

- /E => recurse

- /XC => exclude existing files with same time stamp (whatever size)

- /XN => exclude existing files newer than the source (whatever size)

- /XO => exclude existing files older than the source (whatever size)


then since retry times is 1 million by default, we use 

- /R:2 (2 retries)

- /W:3 (3 seconds)

Also we excluded *.LOG files as there were a lot that we don't need to copy over using

/XF *.log


The full command line be like :

```powershell
Robocopy 'C:\Program Files\Microsoft\Exchange Server\V15' '\\RemoteServer01\c$\Program Files\Microsoft\Exchange Server\V15' /E /XC /XN /XO /R:2 /W:3 /XF *.log
```

