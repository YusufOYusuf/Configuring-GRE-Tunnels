<h1>Configuring GRE Tunnels</h1>


<h2>Description</h2>
In this lab, I learned to configure GRE (generic routing encapsulation) tunnels. It is a tunneling protocol that provides connectivity to a wide variety of network-layer protocols by encapsulating and forwarding packets over an IP-based network.
<br />



<h2>Environments Used </h2>

- <b>Ubuntu 20.04.2 LTS</b> 
- <b>PuTTY SSH Client</b>

<h2>Program walk-through:</h2>

<p align="center">
From the left sidebar click PuTTY SSH Client and proceed to put in the IP address, port number, click Telnet and then click open: <br/>
<img src="https://i.postimg.cc/KjxYRsyM/Screen-Shot-2022-08-13-at-5-28-21-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
<br />
In the R1 terminal window type the commands to create a tunnel<br/>
1. conf t <br/>
2. interface tunnel 1 <br/>
3. ip address 40.0.0.1 255.0.0.0 <br/>
4. tunnel source e0/0 <br/>
5. tunnel destination 192.168.1.2 <br/>
6. end <br/>
<img src="https://i.postimg.cc/6pXNwGt8/Screen-Shot-2022-08-13-at-5-34-37-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
<br />
 In the R1 terminal type the following commands to configure the routing <br/>
 1.conf t <br/>
 2. ip route 0.0.0.0 0.0.0.0 192.168.0.2 <br/>
 3. end <br/>
 <img src="https://i.postimg.cc/50ZR3ZtX/Screen-Shot-2022-08-13-at-5-38-27-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
 
 
 

  
  
<br />
In the R3 terminal type the following commands to create another tunnel <br/>
1. conf t <br/>
2.interface tunnel 1 <br/>
3. ip address 40.0.0.2 255.0.0.0 <br/>
4. tunnel source e0/0 <br/>
5. tunnel destination 192.168.0.1 <br/>
6. end <br/>
<img src="https://i.postimg.cc/L8gKzBDQ/Screen-Shot-2022-08-13-at-5-48-15-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
  
  

  

<br />
In the R3 terminal type the following commands to observe the tunnel configuration<br/>
1. show int tunnel 1 <br/>
2. ping 40.0.0.1 <br/>                      
<img src="https://i.postimg.cc/WzsqZ4PS/Screen-Shot-2022-08-13-at-5-51-18-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>

  
  
 

  
  
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
