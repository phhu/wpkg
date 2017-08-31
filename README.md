WPKG files for automating software installs on windows

See http://wpkg.org

Download and then run commands like this on an admin command prompt:

```
cscript wpkg.js /install:7zip
cscript wpkg.js /install:notepad++
cscript wpkg.js /install:7zip,classicshell,notepad++
```

Software install files can be added to the software directory, and if the download location is specified in the package XML file, will be downloaded as needed.
