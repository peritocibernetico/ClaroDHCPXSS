# ClaroDHCPXSS

There is a vulnerability in Kaon CG3000 router of Claro provider in Brazil.<br>
The firmware tested was 1.01.43, CG3000 Rev V1.2.<br>
<br>
The operating system of the router does not sanitize the data coming from DHCP protocol.<br>
So, it is possible to exploit a authenticated stored XSS (Cross Site Scripting) in the first page of the system, using this protocol.<br>
This page will be the first, right after authentication process, to be viewed by the router admin.<br>
Using the "dhcpcd" command, the vulnerability can be exploited.<br>
<br>
dhcpcd -k wlan0<br>
dhcpcd -n wlan0 -h "<script>alert('XSS')</script>"<br>
<br>
<br>


![image](https://github.com/user-attachments/assets/555655dd-72d3-43a6-925e-c6e9fc581019)

![image](https://github.com/user-attachments/assets/b562135d-31fe-47a6-b53e-10e19044c97b)


