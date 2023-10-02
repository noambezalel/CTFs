# Port 80 - HTTP
I see that port 80 is open, I will try to go with gobuster and see if I can find any directories.

I ran the command:
`gobuster dir -u http://10.10.15.238:80 -u /usr/share/dirb/wordlists/big.txt`

![[Pasted image 20231002192912.png]]
Nothing interesting... Maybe I'll go back to it later.

# Port 135, 139, 445 - DCE RPC smbd, NetBIOS smbd, SMB over TCP
Used to enable SMB.
Tried to connect to the target through SMB
![[Pasted image 20231002192421.png]]
Found The Folder nt4wrksv.
Inside there's only 1 file, [[passwords.txt]].
![[Pasted image 20231002192516.png]]

When tried through smbclient saw more folders.
![[Pasted image 20231002193934.png]]