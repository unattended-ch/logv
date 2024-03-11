
<div align="center">

# logv

[![Release version](https://img.shields.io/github/v/release/unattended-ch/logv?color=blue&label=&style=for-the-badge)](https://github.com/unattended-ch/logv/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/unattended-ch/logv/total?style=for-the-badge&color=blue)](https://github.com/unattended-ch/logv/releases/latest)

Webserver logfile analysis for IIS, Nginx and Apache

Logfile analysis for Mikrotik routers

</div>

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">TABLE OF CONTENTS</h2></summary>
  <ol>
    <li>
      <a href="#description">Description</a>
    </li>
      <a href="#Synopsis">Synopsis</a>
    <li>
      <a href="#first-steps">First steps</a>
      <ul>
        <li><a href="#folders">Folders</a></li>
        <li><a href="#files">Files</a></li>
        <li><a href="#add-files">Add files</a></li>
        <li><a href="#upload-download">Upload Download</a></li>
        <li><a href="#analyze-logfile">Analyze logfile</a></li>
        <li><a href="#blocklist">Blocklist</a></li>
      </ul>
    </li>
    <li><a href="#binarys">Binarys</a></li>
    <li><a href="#configuration">Configuration</a></li>
  </ol>
</details>



## MAINPAGE

![Main Page][main]

## DESCRIPTION

       Webserver logfile analysis software for IIS, Nginx and Apache
       Logfile analysis for Mikrotik routers
       Written with Lazarus and using mysql 8.0 database
       Compiled for Debian, Ubuntu

[Discussion][discuss]

## SYNOPSIS

       - Download logfiles from your Webserver
       - Analyze logfiles IP, Range, Country...
       - Create blocklist entry for adress ranges
       - Create .htaccess files for webserver
       - Send .htaccess file to your server

## FIRST STEPS

       - MySql server must be installed
       - Create a new mysql user weblog
       - Start logv
       - A database connection dialog is displayed
       - Enter your data a press "Connect"
       - If the server is connected, you get a messsage "missing database"
       - Press "Create database"
       - On success you will be forwarded to main page
       - Press "Upload/Download" button
       - Press "Add" to create a new IIS, Nginx, Apache or Mikrotik logfile
       - Press "Add" to create a new .htaccess file
       - Download original .htaccess file from provider to ~/.logv/SERVERNAME.htaccess
       - Add two lines for Blocklist "#BEGIN Blacklist" and "#END Blocklist"
       - Add two lines for Spiders "#BEGIN Spiders" and "#END Spiders"
       - Between this two lines entry's are automatically replaced

### FOLDERS

OS|Folder|Description
----|----|----
Ubuntu|/usr/local/bin/|Executable
Ubuntu|~/logv/|Logfiles, Pages and Archiv folder
Ubuntu|~/.logv/|Work folder for internal files

### FILES

OS|File|Description
----|----|----
Ubuntu|/usr/local/bin/logv|Executable
Ubuntu|~/.logv/logv.conf|Configuration file


### ADD FILES

	- Press "Upload/Download"
	- Press "Add"

![Main Page][add]

Format|Description
---|---
.htaccess|.htaccess file for Apache, Nginx or IIS
IIS logfile|Microsoft IIS logfile format
Apache logfile|Apache or Nginx lofile format
PHP file|PHP file (example : wp-config.php)
HTML file|HTML file
Config file|Config file
Flags|Flags
Webalizer Config file|Webalizer config file

	- For FTP download use "Server", "Username" and "Password"
	- Without these fields a normal file copy will be made

Fields|Description
---|---
Server|FTP FQDN or IP
Username|FTP username
Password|FTP password
Filename|Remote filename, replace date in filename with "{DATE}"
Local filename|Local filename, replace date in filename with "{DATE}"
Comment|Comment for this file entry
Logpre|Logfile short code for local files (example: "aa" or "ab")
Conf filename|Webalizer configuration file (example: files/SERVERNAME.conf)
Webalizer index|Webalizer (example: pages/SERVERNAME/index.html)
Hours to add|If your server is not running in your timezone -1 or +1
Blacklist error|HTML error to send in Blocklist (example: 405)

### Upload Download

![Main Page][updown]

Function|Description
---|---
Add|Add a new file to database
Delete|Delete selected file from database
Download|Download selected file
Upload|Upload selected file
Download Log|Download all IIS, Nginx and Apache logfiles
Update Blacklist|Update and upload all blocklist files
Exit|Exit from window

### ANALYZE LOGFILE

![Main Page][main]

	- Click on a file on left window
	- File will be loaded into import table on center window
	- Country and Range loading automatically started
	- Select a log line and Right-Click "Add to blocklist"
	

### BLOCKLIST

![Main Page][block]

Function|Description
---|---
Save|
Delete|
Refresh|
Reload|
Reset|
Update Filter|
Validate Filter|
Test Filter|
Duplicates|Check for duplicate ranges
Whois|Run WHOIS for IP Adress
Exit|Close window

## BINARYS

  [Download binary][releases]

## CONFIGURATION

OS|File
----|----
Ubuntu|[logv.conf](logv.conf)


[main]: docs/main-window.png

[add]: docs/add-window.png

[updown]: docs/updown-window.png

[block]: docs/block-window.png

[releases]: https://github.com/unattended-ch/logv/releases/

[discuss]: https://github.com/unattended-ch/logv/discussions/


