<p align="center">
<img src="https://i.imgur.com/HPRl0Uw.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Microsoft Azure)</h1>
Hello! In this tutorial I will install Active Directory within Azure Virtual Machines. Like the previous, this tutorial will assume you have two Virtual Machines on Azure already created. One VM using Windows server 2022(Domain Controller) which I will be installing Active Directory on now and another VM using Windows 10(the Client) that I will join later to the Domain controller. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2> Set the Domain Controller's Private ip to Static</h2>
<b> On the Azure Portal click Domain controller > Click Networking > Click  Network Interface</b>
<img src="https://i.imgur.com/9DlbGza.png">
<b>Click ip Configurations</b>
<img src="https://imgur.com/Xs71iST.png">
<b>Switch Toggle to Static > Click Save</b>
<img src="https://i.imgur.com/Lq6jVwr.png">

<h2> Set the Client DNS settings</h2>
<p> Also in the Azure Portal copy the Domain Controllers private IP
<img src="https://i.imgur.com/UPzntYa.png">

<b>Go to the Client's VM Overview > Click Networking > Click on Network Interface > </b>
<img src="https://imgur.com/Lxk4gSf.png">

<b>Click Ip configurations > Toggle to CUSTOM and Type in the domain's private ip address> Click Save</b>
<img src="https://i.imgur.com/ERVrOgU.png">

<b>Restart the Client VM</b>
<img src="https://imgur.com/sgSfpHN.png">

<h2> Log into Domain Controller </h2>

<P>Using Remote Desktop Connection log into your Domain Controller<P/>
<p>On the Server Manager click Add Roles and Features > Click Next >> Confirm private ip address of the Domain Controller > Check Active Directory Domain Services > Click Add Features > Click Next>> Click Install <p/>
<p> To continue Installation Click Promote as a DC<p/>
<p> Click Set Up a New Forest. Type: Mydomain.com and choose a password. Log off then back on to the DC with new credentials <p/>
