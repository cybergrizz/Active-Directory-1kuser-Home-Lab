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
Lets first rename our PC to match the new domain 
 
 <br/>
<img src="https://i.imgur.com/r6caVxS.png" height="80%" width="80%"/>
<br />
 
 
 
Now we are going to change the IP address to one that was used during the test environment.
-Change Adapter Options->Click Properties->Select Internet Protocol Version 4-> Use the following IP address(check video link for IP address) -> Change DNS Server to 127.0.0.1 to route DNS back to domain controller  
 
 <br/>
<img src="https://i.imgur.com/YQ2LnnG.png" height="80%" width="80%"/>
<br />
 

 
 Now we need to add role and services to our domain
 
 <br/>
<img src="https://i.imgur.com/80rOMY6.png" height="80%" width="80%"/>
<br />
 
 

We will select Domain Service to add create our domain and to be able to add out organizational units that will hold out users and admins
 
<img src="https://i.imgur.com/a9R3PGt.png" height="80%" width="80%"/>
<br />

 
 
 After we promote our Domain, after adding the domain services, we will now add the Routing Access to give create servers on our domain to allow our client to login 
 
 <br/>
<img src="https://i.imgur.com/3FRhPyE.png" height="80%" width="80%"/>
<br />
 
 

 We will now configure the Routing services and Remote access using NAT.  This step is after we right-click on our Domain server and choose to configure Routing and Remote access  <br/>
<img src="https://i.imgur.com/0woVLG9.png" height="80%" width="80%"/>
<br />
 <img src="https://i.imgur.com/uCTyo7r.png" height="80%" width="80%"/>
<br />

 
 
 Our Ethernet adapters did not load, but no worries, closing out and opening it back up had both adapters populate.  We selected the adapter we configured with the above IP address 
 
 <br/>
<img src="https://i.imgur.com/RoWcJGS.png" height="80%" width="80%"/>
<br />

 Now that we have that configured, we will now add the DHCP service to our domain 
 
 <br/>
<img src="https://i.imgur.com/CE9t7pF.png" height="80%" width="80%"/>
<br />
 
 
REMEMBER! You must be on an admin account for this process becuase we need to authorize the DHCP server once we have completed setting it up 
 
 <br/>
<img src="https://i.imgur.com/Ms8VMvY.png" height="80%" width="80%"/>
<br />
 

Now that we have logged into an admin account after creating a new admin user, we will create a new scope for our first lease to allow our Client PC access to the domain 
 
 <br/>
<img src="https://i.imgur.com/Fvqmtvw.png" height="80%" width="80%"/>
<br />
 
 
Now we set our IP range
 
 <br/>
<img src="https://i.imgur.com/zj3XFch.jpg" height="80%" width="80%"/>
<br />
 
 
Here is our lease for our Client PC.  The lease time does not matter as this virtual machine was de-provisioned as fast as it was spun up, but here is an example of how to set one 
 
 <br/>
<img src="https://i.imgur.com/LOLplxF.png" height="80%" width="80%"/>
<br />
 
We will now set our Default Gateway to that of the Domain Controller, while also be setting the DNS to the same IP shortly after.  This will allow our Client PC to connect to the Domain
 
 <br/>
<img src="https://i.imgur.com/LaQaJIM.jpg" height="80%" width="80%"/>
<br />
 
 
After those parameters are set, we now, with our ADMIN account, authorize the DHCP srver 
 
 <br/>
<img src="https://i.imgur.com/7KfwDe4.png" height="80%" width="80%"/>
<br />
 
 
The tutorial we followed has a custom PowerShell code that can be installed on the DC to allow us to run the code
 
 <br/>
<img src="https://i.imgur.com/CbcfTRK.png" height="80%" width="80%"/>
<br />
 
 
!!AS AN ADMIN OF COURSE!!!
 
 
Now we are the Admin after we demanded the PowerShell ISE to run as an administrator
 
 <br/>
<img src="https://i.imgur.com/2Y4pITL.png" height="80%" width="80%"/>
<br />
 
 
So lets run this code.  We will use a .txt document in the file that has over a thousand users randomly generated.  But we must remember, because at first I did not, that we must be in the directory of said file to actually run said code... 
 
 <br/>
<img src="https://i.imgur.com/hNCyOt4.png" height="80%" width="80%"/>
<br />
 
 
Script runs, but don't chase it! That's...that's what it is supposed to do 
 
 <br/>
<img src="https://i.imgur.com/pJP6Idr.png" height="80%" width="80%"/>
<br />
 
 
Now we can see our newly created users in Active Directory 
 
 <br/>
<img src="https://i.imgur.com/eaHSR1J.png" height="80%" width="80%"/>
<br />
 
 
Now we go back to Virtual Box and let's provison our Client PC.  But first we will change the Network Adapter setting to Internal 
 
 <br/>
<img src="https://i.imgur.com/Iafp83S.png" height="80%" width="80%"/>
<br />
 
 
 We changed the Ethernet settings on the CLient PC. We only changed the DNS address to the IP address of our Domain Controller, we need to add it to our Domain controller. 
 
 
 (Right-click on the start menu-> Select system -> Select "Change PC Name(advanced).  We do not change it in the field at the top, but we select "Change" instead and change it there)
 
 <br/>
<img src="https://i.imgur.com/smusvgT.png" height="80%" width="80%"/>
<br />
 
 
 
 YOU CAN SEE IN THE BACK THAT WE RAN THE PING COMMAND TO MAKE SURE THE CLIENT PC CAN TALK TO THE DOMAIN CONTROLLER AFTER RUNNING IPCONFIG TO CONFIRM THAT THE CLIENT PC HAS A DEFAULT GATEWAY, WHICH IS THE SAME AS THE IP ADDRES OF THE DOMAIN CONTROLLER.  SO INCEPTION BASICALLY...
 
 
 
 Now we use our admin account of our Domain Controller and log into the DC to connect Client-SAMA 
 
 <br/>
<img src="https://i.imgur.com/1Swfrg8.jpg" height="80%" width="80%"/>
<br />
 
 

 
 Success!! Also do you care that I chose not to redact all of the IP addressess even though I thought I should because Cybersecurity but realized that all of those same addresses are generated in the video I linked above? COOL, me neither 
 
 <br/>
<img src="https://i.imgur.com/PYv3tLV.png" height="80%" width="80%"/>
<br />
 
 
 Now that we have connected our Domain Controller to our Client PC, I mean vice versa, we will logon with one of those randomly generated employees...ahem...users. 
 
 <br/>
<img src="https://i.imgur.com/YluZE8S.png" height="80%" width="80%"/>
<br />
 
 
 
 But seriously, WHOAMI?. I'm a new computer that can be in the repsective OU. 
 
 <br/>
<img src="https://i.imgur.com/kpFJMXy.png" height="80%" width="80%"/>
<br />

 
 Also, shout out to TECH IS THE NEW BLACK for giving me some good podcast style content about tech while I was running this lab. 
