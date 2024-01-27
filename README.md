<h1>Kerberoast Attack</h1>

 <h2>Description</h2>
Project consists of performing a Kerberoasting attack, used to obtain password hashes of a service account, on a vulnerable Windows home lab.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Impacket</b> 
- <b>Hashcat</b>

<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Project walk-through:</h2>

<p align="center">
Kerberoasting 
<br />
<br />
First we will utilize impacket to run GetUserSPNs.py in order to grab any Service Principal Name (SPN) that are associated with an account. If an SPN is set on a user account it is possible to request a Service Ticket for this account and attempt to crack it in order to retrieve the user password. <br />
<img src="https://i.imgur.com/d1iJwJx.png" height="60%" width="60%" alt="Kerberoast"/>
<br />
<br />
Next we can take the krb5 hash save it in a text file, then we can attempt to use hashcat to crack it to find the password.  <br/>
<img src="https://i.imgur.com/Exjzr6N.png" height="60%" width="60%" alt="Kerberoast"/>
<br />
<br />
Hashcat will run and begin the cracking process. If the password is cracked it will display the password in clear text at the end of the hash we provided.  <br/>
<img src="https://i.imgur.com/ky9TnIt.png" height="60%" width="60%" alt="Kerberoast"/>
<br />
<br />
Hashcat successfully cracked the hash.  <br/>
<br />
<br />
</p>
<p align="left">
Mitigation/Remediation Strategies <br />
1. Have strong password complexity policies <br />
2. Use least privilege principles - no accounts running as admin/domain admin that dont need it. <br />
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
