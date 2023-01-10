# EfsTools. Console program for accessing the EFS file system of Qualcomm modems

The program allows:
- Get information about the connected device
- Get information about the parameters of the EFS file system
- Read file from device to computer
- Write file from computer to device
- Delete file from device
- Rename (move) a file on the device
- Create a directory in the device
- Delete directory on device
- Get a list of files and directories
- Download catalog from device to computer
- Download catalog from computer to device.

## System requirements

- Windows 10 1607 or later, Windows Server 2012 R2 or later, Mac OS X 10.13 or later, Red Hat Enterprise Linux 7 or later, CentOS 7 or later, Ubuntu 16.04 or later, Fedora 30 or later, Debian 9 or later, OpenSUSE 15 and up
- [DotNet 5.0](https://dotnet.microsoft.com/download/dotnet/5.0) and above.

## Installation
You need to download the release archive from [developer site](http://johnbel.github.io/). Then unpack it.

## Configuration
The program settings are stored in the EfsTools.exe.config file. Before starting work, you must specify the name of the COM port (parameter ***port***) and its speed (***baudrate***).

## Command line options

EfsTools.exe <command> [command options]

### List of commands
  
***targetInfo***
Get information about the connected device.

Example: EfsTools.exe targetInfo

***efsInfo***
Getting information about the EFS file system on a device

Example: EfsTools.exe efsInfo

***readFile***
Reading a file from a device to a computer

Example: EfsTools.exe readFile -i /safe/test/efs -o c:\temp\efs

***writeFile***
Writing a file from a computer to a device

Example: EfsTools.exe writeFile -i c:\temp\efs -o /safe/test/efs

***renameFile***
Rename file on device

Example: EfsTools.exe renameFile -p /safe/test/efs -n /safe/test/efs2


***deleteFile***
Delete file on device

Example: EfsTools.exe deleteFile -p /safe/test/efs

***createDirectory***
Create directory on device

Example: EfsTools.exe createDirectory -p /safe/test/efs


***deleteDirectory***
Delete a directory on a device

Example: EfsTools.exe deleteDirectory -p /safe/test/efs


***listDirectory***
Get a list of files and directories

Example: EfsTools.exe listDirectory -p /safe/test/efs -r

***downloadDirectory***
Download catalog from device to computer

Example: EfsTools.exe downloadDirectory -i / -o c:\backup\efs


***uploadDirectory***
Upload catalog from computer to device

Example: EfsTools.exe uploadDirectory -i c:\backup\efs -o /


***getModemConfig***
Generate modem configuration using device or directory (option -i) with EFS structure

Example: EfsTools.exe getModemConfig -i .\backup -p .\items_backup.json
EfsTools.exe getModemConfig -p .\items_phone.json


***setModemConfig***
Set modem configuration in device or generate EFS structure in directory (option -o)

Example: EfsTools.exe setModemConfig -p .\items.json -o .\efs
EfsTools.exe setModemConfig -p .\items_for_phone.json


***extractMbn***
Unpack the contents of the MBN (Modem configuration BiNary) file to the specified directory
Example: EfsTools.exe extractMbn -i mcfg_sw.mbn -p mcfg

***getLog***
Start capturing modem logs and messages

Example: EfsTools.exe getLog -l IMS_MESSAGE

***webDavServer***
Starting the WebDAV Server

Example: EfsTools.exe webDavServer -p 8888 -r 1
  
  
***help***
Show command help

Example: EfsTools.exe help createDirectory

***version***
Show program version

Example: EfsTools.exe version

## Licenses
This software is licensed under [MIT](/License.md)

The program uses the [Commandline] library(https://github.com/commandlineparser/commandline) Copyright (c) 2005 - 2015 Giacomo Stelluti Scala & Contributors

The program uses the [NWebDav] library(https://github.com/ramondeklein/nwebdav) Copyright (c) 2018 Ramon de Klein

The program uses the library [Newtonsoft.Json](https://www.newtonsoft.com/json) Copyright (c) 2007 James Newton-King

The program uses the library [ELFSharp] (http://elfsharp.hellsgate.pl) Copyright (c) Konrad Kruczyński, iotr Zierhoffer, Łukasz Kucharski, Bastian Eicher, Cameron, Fox, Frederik Carlier, Everett Maus

The Qualcomm modem protocol was read in the [libopenpst](https://github.com/openpst/libopenpst) project Copyright (c) Gassan Idriss

## Site
[johnbel](http://johnbel.github.io/)
