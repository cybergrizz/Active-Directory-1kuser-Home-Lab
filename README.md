# 

<h1>Active Directory Bulk User creation</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
In this lab this lab I created a Domain Controller in Active Directory.  I used Oracle Virtual Box to create the virtual environment to set up the Domain Controller and a Client PC to connect to our local domain.  Following a video, posted bY Josh Madakor on youtube (linked above), allowed me to use a custom PowerShell script to bulk add over 1 thousand different users into our domain.  
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Program walk-through:</h2>


<p align="center">
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
 
 
 
Now we are going to change the IP address to one that was used during the test environment.
-Change Adapter Options->Click Properties->Select Internet Protocol Version 4-> Use the following IP address(check video link for IP address) -> Change DNS Server to 127.0.0.1 to route DNS back to domain controller  <br/>
<img src="https://i.imgur.com/YQ2LnnG.png" height="80%" width="80%"/>
<br />
 

 
 Now we need to add role and services to our domain<br/>
<img src="https://i.imgur.com/80rOMY6.png" height="80%" width="80%"/>
<br />
 
 

We will select Domain Service to add create our domain and to be able to add out organizational units that will hold out users and admins
<img src="https://i.imgur.com/a9R3PGt.png" height="80%" width="80%"/>
<br />

 
 
 After we promote our Domain, after adding the domain services, we will now add the Routing Access to give create servers on our domain to allow our clinet to login <br/>
<img src="https://i.imgur.com/3FRhPyE.png" height="80%" width="80%"/>
<br />
 
 

 We will now configure the Routing services and Remote access using NAT.  This step is after we right-click on our Domain server and choose to configure Routing and Remote access  <br/>
<img src="https://i.imgur.com/0woVLG9.png" height="80%" width="80%"/>
<br />
 <img src="https://i.imgur.com/uCTyo7r.png" height="80%" width="80%"/>
<br />

 
 
 At first our Ethernet adapters did not load, but no woriies, closing out and opening it back up had both adapters populate.  We selected the adapter we configured with the above IP address <br/>
<img src="https://i.imgur.com/RoWcJGS.png" height="80%" width="80%"/>
<br />

 Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />

 Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
Lets First rename our PC to match the new domain <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
