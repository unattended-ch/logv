<div align="center">

# logv

[![Release version](https://img.shields.io/github/v/release/unattended-ch/logv?color=blue&label=&style=for-the-badge)](https://github.com/unattended-ch/logv/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/unattended-ch/logv/total?style=for-the-badge&color=blue)](https://github.com/unattended-ch/logv/releases/latest)

[![my way](https://img.shields.io/badge/-actio_et_reactio-navy.svg?style=for-the-badge&color=blue)](https://translate.google.com/?sl=auto&tl=de&text=actio%20et%20reactio&op=translate)<br>

Webserver logfile analysis for IIS, Nginx and Apache

Logfile analysis for Mikrotik routers

</div>

<!-- TABLE OF CONTENTS -->
<a name="toc"></a>
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">TABLE OF CONTENTS</h2></summary>
  <ol>
    <ul>
      <a href="#main">Main window</a><br>
      <ul>
          <a href="#description">Description</a><br>
          <a href="#folders">Folders</a><br>
          <a href="#files">Files</a><br>
          <a href="#first">First steps</a><br>
      </ul>
      <a href="#add-files">Add files</a><br>
      <a href="#updown">Upload Download</a><br>
      <a href="#analyze">Analyze logfile</a><br>
      <a href="#blocklist">Blocklist</a><br>
      <a href="#database">Database</a><br>
      <a href="#license">Get a license</a><br>
      <a href="#change">Changelog</a>
    </ul>
  </ol>
</details>



<a name="main"></a>
## :computer: MAINPAGE

![Main Page][main]

<a name="description"></a>
## :scroll: DESCRIPTION

       Webserver logfile analysis software for IIS, Nginx and Apache
       Logfile analysis for Mikrotik routers
       Written with Lazarus using mysql 8.0 database
       Compiled for Ubuntu

       - Download logfiles from your Webserver
       - Analyze logfiles IP, Range, Country...
       - Create blocklist entry for adress ranges
       - Create .htaccess files for webserver (only Licensed)
       - Send .htaccess file to your server (only Licensed)

##### Uploading files is only in Licensed version available

<a name="folders"></a>
### :file_folder: FOLDERS

OS|Folder|Description
----|----|----
Ubuntu|/usr/local/bin/|Executable
Ubuntu|~/logv/|Logfiles, Pages and Archiv folder
Ubuntu|~/.logv/|Work folder for internal files

<a name="files"></a>
### :clipboard: FILES

OS|File|Description
----|----|----
Ubuntu|/usr/local/bin/logv|Executable
Ubuntu|~/.logv/logv.conf|Configuration file

   [goto TOC](#toc)

<a name="first"></a>
## :runner: FIRST STEPS

       - Start logv
       - A script will assist you if mysql-server is not installed
       - Then the database connection dialog is displayed

![Connection][dbconnection]

       - Enter your data a press "Connect"
       - If the server is connected, you get a messsage "missing database"
       - Press "Create database"
       - The basic tables for logv are created
       - On success you will be forwarded to main page
       - The basic data will be imported from dump

       - Press "Upload/Download" button

![UploadDownload][updown]

       - Press "Add" to create a new IIS, Nginx, Apache or Mikrotik logfile
       - Press "Add" to create a new .htaccess file

![Addfile][add]

       - Enter informations and Press "Save"
   For more information [(see Add Files)](#addfiles)

       - Press "Download" to get the original .htaccess file from provider to ~/.logv/files/SERVERNAME.htaccess
       - Add two lines for Blocklist "#BEGIN Blacklist" and "#END Blocklist
       - Add two lines for Webspiders "#BEGIN Spiders" and "#END Spiders"
[.htaccess](/.htaccess)

       - Between #BEGIN and #END data will be automatically replaced

   [goto TOC](#toc)

<a name="updown"></a>
### :globe_with_meridians: Upload Download

![Main Page][updown]

Function|Description
---|---
Add|Add a new file to database
Delete|Delete selected file from database
Download|Download selected file
Download Log|Download all IIS, Nginx and Apache logfiles
*Upload|Upload selected file
*Update Blacklist|Update and upload all blocklist files
Exit|Exit from window

###### Function marked with * are only in Licensed-Version available

   [goto TOC](#toc)

<a name="addfiles"></a>
### :pencil2: ADD FILES

	- Press "Upload/Download"
	- Press "Add"

![Main Page][add]

Format|Description
---|---
.htaccess|.htaccess file for Apache, Nginx or IIS
IIS logfile|Microsoft IIS logfile format
Apache logfile|Apache or Nginx lofile format
Mikrotik|Mikrotik logfile format
PHP file|PHP file (example : wp-config.php)
HTML file|HTML file
Config file|Config file
Flags|Flags
Webalizer Config file|Webalizer config file

	- For FTP download use "Server", "Username" and "Password"
	- Without these fields a normal file copy will be made

	- For Mikrotik you can specify a VPN-connection use "Filename" (myvpn)
	- For Mikrotik specify "Username" with connection data (username@10.1.1.1)
	- Mikrotik data will be send with "rsh username@10.1.1.1 scriptname"

Fields|Description
---|---
Server|FTP FQDN or IP
Username|FTP username or Mikrotik rsh connection data
Password|FTP password
Filename|Remote filename, replace date in filename with "{DATE}"
Local filename|Local filename, replace date in filename with "{DATE}"
Comment|Comment for this file entry
Logpre|Logfile short code for local files (example: "aa" or "ab")
Conf filename|Webalizer configuration file (example: files/SERVERNAME.conf)
Webalizer index|Webalizer (example: pages/SERVERNAME/index.html)
Hours to add|If your server is not running in your timezone -1 or +1
Blacklist error|HTML error to send in Blocklist (example: 410)

   [goto TOC](#toc)

<a name="analyze"></a>
### :mag_right: ANALYZE LOGFILE

![Main Page][main]

	- Click on a file on left window
	- File will be loaded into import table on center window
	- Country and Range loading will be started automatically
	- To block IP address select log line and Right-Click "Add to blocklist"
	- To block Webspiders select a log line and Right-Click "Add to spiders"
![Blocklist][block]
![Webspider][spider]

	- Verify data and Press "Save"
	- Leave the window Press "Exit"

   [goto TOC](#toc)

<a name="blocklist"></a>
### :name_badge: BLOCKLIST

![Main Page][block]

Function|Description
---|---
Save|Save selected record
Delete|Delete selected record
Refresh|Refresh list
Reload|Reload list
Reset|Reset default list display
Update Filter|Update filter
Validate Filter|Validate filter
Test Filter|Test all filter in the blocklist
Test Owner|Test all owners in the blocklist
Overlap|Check for overlapping ranges in the blocklist
Whois|Run WHOIS for selected IP Adress
Exit|Close window

   [goto TOC](#toc)

<a name="database"></a>
### :cd: DATABASE

###### Windows marked with * are only in Licensed-Version available

#### * Archiv
![Database archiv][dbarchiv]

   [goto TOC](#toc)

#### * Blocklist
![Database blocklist][dbblock]

   [goto TOC](#toc)

#### * Spiders
![Database spiders][dbspiders]

   [goto TOC](#toc)

#### * Errors
![Database errors][dberrors]

   [goto TOC](#toc)

#### * Keywords
![Database keywords][dbkeywords]

   [goto TOC](#toc)

#### * Files
![Database files][dbfiles]

   [goto TOC](#toc)

#### Connection
![Database connection][dbconnection]

   [goto TOC](#toc)

<a name="license"></a>
## :warning: License

[Get license, pay with payment slip](https://unattended.ch/?page_id=1983)<br>

<a name="change"></a>
## :recycle: CHANGELOG
[Changelog](/CHANGELOG)

   [goto TOC](#toc)


[main]: docs/main-window.png

[add]: docs/add-window.png

[updown]: docs/updown-window.png

[block]: docs/block-window.png

[spider]: docs/spiders-window.png

[dbarchiv]: docs/db-archiv.png

[dbblock]: docs/db-block.png

[dbspiders]: docs/db-spiders.png

[dberrors]: docs/db-errors.png

[dbkeywords]: docs/db-keywords.png

[dbfiles]: docs/db-files.png

[dbconnection]: docs/db-connection.png

[.haccesst]: .htaccess

[releases]: https://github.com/unattended-ch/logv/releases/

[discuss]: https://github.com/unattended-ch/logv/discussions/


