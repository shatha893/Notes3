

* Nmap results

```
PORT      STATE SERVICE
135/tcp   open  msrpc
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
3389/tcp  open  ms-wbt-server
5985/tcp  open  wsman
47001/tcp open  winrm
49664/tcp open  unknown
49665/tcp open  unknown
49666/tcp open  unknown
49667/tcp open  unknown
49668/tcp open  unknown
49669/tcp open  unknown
49670/tcp open  unknown
49671/tcp open  unknown
```

* Banner Grab  

```
PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
3389/tcp open  ms-wbt-server Microsoft Terminal Services
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

```

* So the problem was with the certificate. When I use `xfreerdp /v:[IP ADDRESS] /cert:ignore /u:Administrator`. 
* First off, we use Administrator instead of root in Windows machines.
* Second, I should've looked more into the flags or switches or whatever they call them. Anyway, it wouldn't have occured to me that I have to ignore the cert or that this was an option or that if I put it it will be functional.

```
[03:25:50:543] [2009:2010] [INFO][com.freerdp.client.common.cmdline] - loading channelEx rdpsnd
[03:25:50:543] [2009:2010] [INFO][com.freerdp.client.common.cmdline] - loading channelEx cliprdr
[03:25:50:883] [2009:2010] [INFO][com.freerdp.primitives] - primitives autodetect, using optimized
[03:25:50:918] [2009:2010] [INFO][com.freerdp.core] - freerdp_tcp_is_hostname_resolvable:freerdp_set_last_error_ex resetting error state
[03:25:50:918] [2009:2010] [INFO][com.freerdp.core] - freerdp_tcp_connect:freerdp_set_last_error_ex resetting error state
[03:25:50:214] [2009:2010] [WARN][com.freerdp.crypto] - Certificate verification failure 'self signed certificate (18)' at stack position 0
[03:25:50:214] [2009:2010] [WARN][com.freerdp.crypto] - CN = Explosion

```