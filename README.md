WPKG files for automating software installs on windows

See http://wpkg.org

Download and then run commands like this on an admin command prompt:

```
cscript wpkg.js /install:7zip
cscript wpkg.js /install:notepad++
cscript wpkg.js /install:7zip,classicshell,notepad++
```

Software install files can be added to the software directory, and if the download location is specified in the package XML file, will be downloaded as needed.

PS download
-----------

```
$destpath = $pwd.path
$zipfile = join-path $destpath "wpkg.zip"
invoke-webrequest "https://github.com/phhu/wpkg/archive/master.zip" -outfile $zipfile
$shell = new-object -com shell.application
$zip = $shell.NameSpace($zipfile)
$shell.Namespace($destpath).copyhere($zip.items()[0])
cd wpkg-master
cscript wpkg.js /install:classicshell
```
