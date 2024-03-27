<h1> Vulnerability Scanning Lab with Nessus</h1>

<h2>Description</h2>
This lab, aimed at exploring the basic functionalities of Nessus, serves as an introductory exercise to understand its capabilities and to see what vulnerabilities can be unearthed for further exploration with Metasploit. Furthermore, Nessus's capability extends to its interoperability with Metasploit, a testament to its utility and adaptability in the cybersecurity realm. Specifically, Metasploit is designed to accept vulnerability scan results from both Nessus and OpenVAS in the nbe file format. This feature facilitates seamless integration between these tools, enhancing the efficiency and comprehensiveness of vulnerability management and penetration testing workflows. The collaboration between these platforms underscores the dynamic nature of cybersecurity defences, highlighting Nessus's pivotal role in identifying vulnerabilities and fortifying network security.
<br />
<br />
Nessus is crucial for companies today, serving as a powerful tool in identifying vulnerabilities within their networks. It helps in uncovering software flaws and misconfigurations, enabling businesses to address potential security risks effectively. Moreover, Nessus supports compliance with industry standards and regulations, offering tailored scans to ensure businesses meet specific security requirements. Its comprehensive reporting facilitates informed decision-making, aiding in the prioritization of security efforts. By providing continuous monitoring and assessment capabilities, Nessus plays a vital role in enhancing a company's cybersecurity posture, making it an indispensable asset for modern businesses aiming to protect their digital environments.
  
<br />


<h2>Tools or Utilities Used</h2>

- <b>Nessus 10.5.1-ubuntu1404_amd64.deb</b> 
- <b>Metasploit</b>


<h2>Environments Used </h2>

- <b>Kali Linux 2023.1</b>
- <b>VMware Workstation 17 Pro</b> 

<h2>Lab simulation walk-through:</h2>

<p align="left">
  
- <b>First, before everything, head over to Tenable's Nessus Plugins page by using your favourite web browser, be it Firefox ESR or Ice Weasel.</b> 
    - Here's the link needed: [Tenable's Nessus Plugins page](https://www.tenable.com/products/nessus/nessus-plugins/obtain-an-activation-code). 
    - Sign up as a Free Home user with your email. Once done, keep an eye on the mail inbox because they're going to send an activation code.
<br />
<br />

- <b>Next, it's time to grab the software.</b>
    - Go to the Nessus Download page at [Nessus Download page](https://www.tenable.com/products/nessus/select-your-operating-system#download)
    - pick the version that fits the local system. Whether Debian 6, 7, 8, Kali Linux 1 AMD64, Debian 6, 7, 8, Kali Linux 1 i386(32-bit), or any Linux distro
<br/>
</p>

<h2>Start installing and using:</h2>

### Task 1: Vulnerability Assessment with Nessus

<p align="left">

#### Lab Steps

1. **Update:**
   - First, I updated the Kali Linux system.<br/>
     <img src="https://imgur.com/7r4NyVd.png" height="80%" width="80%" alt="Nessus Steps"/>
     
2. **Installation:**
   - Opened a terminal, navigated to the Downloads folder, and use `sudo dpkg -i <Nessus-6……>` to install Nessus. Remember, `dpkg` is the package manager for Debian systems, and `-i` installs a package. 
     <img src="https://imgur.com/9MJImib.png" height="80%" width="80%" alt="Nessus Steps"/>
     
4. **Checking Nessus Status:**
   - I used `sudo /etc/init.d/nessusd status` to check the status of the Nessus package on the local system.
     <img src="https://imgur.com/W39BkFC.png" height="80%" width="80%" alt="Nessus Steps"/>

5. **Starting Nessus Daemon & Accessing Nessus Web Interface:**
   - I started the Nessus daemon with `sudo /etc/init.d/nessusd start`.
   - In my browser, went to `https://127.0.0.1:8834` to login to the Nessus web interface. I created a username aka MI5 and password, then entered the activation code received by email.
     <img src="https://imgur.com/KkeS3i9.png" height="80%" width="80%" alt="Nessus Steps"/>

6. **Checking host IP address and Metasploit IP address:**
   - Checked the IP address of the Linux box with `sudo ifconfig -a`
     <img src="https://imgur.com/CPlS7Cx.png" height="80%" width="80%" alt="Nessus Steps"/>
     <img src="https://imgur.com/ySYjmiK.png" height="80%" width="80%" alt="Nessus Steps"/>

7. **Running the First Scan:**
   - In the Nessus web portal, click "New Scan" > "Basic Network Scan". Entered the Linux box's IP subnet as the target, and started the scan.

     <img src="https://imgur.com/HeErPdI.png" height="80%" width="80%" alt="Nessus Steps"/>
     <img src="https://imgur.com/0WfVLAG.png" height="80%" width="80%" alt="Nessus Steps"/>

<br />
</p>

<h2>Finding and Conclusion</h2>

<p align="left">

<img src="https://imgur.com/Gwhiczk.png" height="80%" width="80%" alt="Nessus Steps"/>
<img src="https://imgur.com/BcuZVXI.png" height="80%" width="80%" alt="Nessus Steps"/>

There is a clear indication of how targeted and environment-specific vulnerability scanning results can be. When Nessus scans the host IP address and the results come back clean or with few issues, it suggests that my host system is relatively secure, with fewer vulnerabilities exposed to potential attackers. This is the expected outcome for a well-maintained and regularly updated system, where security patches are applied, and unnecessary services are disabled or properly secured.
<br />
<br />
On the other hand, when Nessus scans the IP address associated with the Metasploit lab environment and returns a plethora of alerts, it reflects the intentional setup of the Metasploit environment. The Metasploit lab is designed to mimic vulnerable systems for educational, training, or testing purposes, offering hands-on experience with various security vulnerabilities and attack techniques. This environment allows users to learn how to exploit vulnerabilities, understand the mechanics behind the attacks, and practice mitigation strategies in a controlled setting.

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
