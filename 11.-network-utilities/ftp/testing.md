# Testing

Anonymous FTP is still used to distribute open-source software, we refer to these locations as mirror sites. Look at ftp.heanet.ie using a web browser. I want to get the latest security keys from&#x20;

```
/mirrors/ubuntu-cdimage/releases/22.04/release 
```

The file is called SHA256SUMS and you should be able to find it via a web browser. I wrote the following simple script using the original Python _ftplib_ and saved it as **ftpget1.py**.

```
import ftplib

# Set the path
path = '/mirrors/ubuntu-cdimage/releases/22.04/release'
# What file to download
filename = 'SHA256SUMS'
# Make the connection
ftp = ftplib.FTP("ftp.heanet.ie")
# Anonymous login
ftp.login() 
# Change to the correct directory
ftp.cwd(path)
# Retrieve the file
ftp.retrbinary("RETR " + filename, open(filename, 'wb').write)
# Cleanly exit
ftp.quit()

```

This is the simplest possible usable and useful script! Having fixed paths, URLs, and file names does seem very unprofessional. To make this a little more usable, I could put all my settings in a dictionary (we covered these in Section 3). This is ftpget2.py

```
import ftplib

FTP = {
    "PATH": '/mirrors/ubuntu-cdimage/releases/22.04/release',
    "FILENAME": 'SHA256SUMS',
    "URL": 'ftp.heanet.ie'
}

# Make the connection
ftp = ftplib.FTP(FTP['URL'])
# Anonymous login
ftp.login() 
# Change to the correct directory
ftp.cwd(FTP["PATH"])
# Retrieve the file
ftp.retrbinary("RETR " + FTP["FILENAME"], open(FTP["FILENAME"], 'wb').write)
ftp.quit()

```

This is shorter, cleaner code. But there is a better way. I create a directory called **Exercises\_11\settings** and create a new file, **ftp.py** in it.

```
FTP = {
    "PATH": '/mirrors/ubuntu-cdimage/releases/22.04/release',
    "FILENAME": 'SHA256SUMS',
    "URL": 'ftp.heanet.ie'
}
```

My final code is economical, and it is clear what the settings are and where they come from. To download another file, I just need a different settings file. This is **ftp\_downloader.py**

```
""""
FTP file downloader
Tested with Python >=3.6
By: JOR
    v0.1    20AUG20 
"""
import ftplib
import settings.ftp as settings

# Make the connection
ftp = ftplib.FTP(settings.FTP['URL'])
# Anonymous login
ftp.login() 
# Change to the correct directory
ftp.cwd(settings.FTP["PATH"])
# Retrieve the file
ftp.retrbinary("RETR " + settings.FTP["FILENAME"], open(settings.FTP["FILENAME"], 'wb').write)
ftp.quit()

```

Finally, a modular and useful script that I use for downloading configuration files etc.
