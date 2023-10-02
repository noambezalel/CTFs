Some basic nmap scan

sudo nmap -sS -p- 10.10.15.238

```
Starting Nmap 7.94 ( https://nmap.org ) at 2023-10-02 18:57 IDT
Stats: 0:01:02 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 28.40% done; ETC: 19:00 (0:02:29 remaining)
Nmap scan report for 10.10.15.238
Host is up (0.11s latency).
Not shown: 65527 filtered tcp ports (no-response)
PORT      STATE SERVICE
80/tcp    open  http
135/tcp   open  msrpc
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
3389/tcp  open  ms-wbt-server
49663/tcp open  unknown
49667/tcp open  unknown
49669/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 259.80 seconds
```

Waiting for the more serious scan

sudo nmap -sC -O -p- 10.10.15.238

```
┌──(kali㉿NoamPC)-[~]
└─$ sudo nmap -sC -O -p- 10.10.15.238
Starting Nmap 7.94 ( https://nmap.org ) at 2023-10-02 19:30 IDT
Nmap scan report for 10.10.15.238
Host is up (0.12s latency).
Not shown: 65527 filtered tcp ports (no-response)
PORT      STATE SERVICE
80/tcp    open  http
|_http-title: IIS Windows Server
135/tcp   open  msrpc
139/tcp   open  netbios-ssn
445/tcp   open  HEAD,
3389/tcp  open  ms-wbt-server
| rdp-ntlm-info:
|   Target_Name: RELEVANT
|   NetBIOS_Domain_Name: RELEVANT
|   NetBIOS_Computer_Name: RELEVANT
|   DNS_Domain_Name: Relevant
|   DNS_Computer_Name: Relevant
|   Product_Version: 10.0.14393
|_  System_Time: 2023-10-02T16:33:40+00:00
| ssl-cert: Subject: commonName=Relevant
| Not valid before: 2023-10-01T15:37:34
|_Not valid after:  2024-04-01T15:37:34
49663/tcp open  unknown
49667/tcp open  unknown
49669/tcp open  unknown
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running (JUST GUESSING): Microsoft Windows 2016 (89%)
OS CPE: cpe:/o:microsoft:windows_server_2016
Aggressive OS guesses: Microsoft Windows Server 2016 (89%)
No exact OS matches for host (test conditions non-ideal).

Host script results:
| smb2-security-mode:
|   3:1:1:
|_    Message signing enabled but not required
|_clock-skew: mean: 1h45m02s, deviation: 3h30m02s, median: 0s
| smb-security-mode:
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-time:
|   date: 2023-10-02T16:33:38
|_  start_date: 2023-10-02T15:38:10
| smb-os-discovery:
|   OS: Windows Server 2016 Standard Evaluation 14393 (Windows Server 2016 Standard Evaluation 6.3)
|   Computer name: Relevant
|   NetBIOS computer name: RELEVANT\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2023-10-02T09:33:38-07:00

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 255.77 seconds
```