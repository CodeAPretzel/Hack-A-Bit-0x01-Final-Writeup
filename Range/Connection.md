## Challenge ~
This section is a series of challenges in a semi-isolated cyber range. Your goal is to compromise the boxes and get the flags. Your first challenge is more of a sanity-check/confirmation. We wanted to use private keys for this but logistics of distributing them was challenge so its just password login for now. Check your email, at exactly 5pm PST Friday you received a credential and IP address for this jumpbox. You can also use the connection info listed below.

You will use this jumpbox to attack other machines in the network. We've installed nmap, metasploit and netcat for your convience. If you want other tooling installed later please reach out to staff and will consider those requests as you ask. Remember that you can use techniques like proxychains over SSH to emulate much of this functionality.
<br>

`range.final.hackabit.com`

<br>

<div align="center">
  <b>IMPORTANT -- CHALLENGES IN RANGE WILL BE LESS DESCRIPTIVE SINCE THE MACHINES HOSTING THE CHALLENGES ARE DOWN</b>
</div
    
<br>
<br>
    
## Solution ~
This challenge was pretty simple. All we had to do was connect to the server and look around for the flag. As the challenge says, we get an email with the ip, `**.***.123.214` and we have to `SSH` into this with our username and password:
    
```
--(kali@kali)-[~]
|
-$ ssh [username]@**.***.123.214
    
Add this connection, blah blah blah

- Password ->
    
- We're In
    
-$
```

Next we look for the flag on the server. We could do this in two ways. Search for it or use `find / -name flag`. I used the second option and thank goodness they didn't decide to change the name on us for this one. Read the file and get the 🚩 <b>flag{welcome_to_the_range}</b>
