# networkwalks-B082-week1-Cybersecurity-lab-setup
## **Cybersecurity Lab Setup**

Creating an isolated virtual lab for penetration testing and ethical hacking practice. 

In this lab, I will be able to practice hacking tools, scanning and malware testing without putting my actual computer or my home and work network at risk. 

## __Project Overview and Purpose__

This project center on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.

The  key objective of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing tasks can be performed securely and repeatedly.

In order to accommodate future additions of machines and their use as targets for authorized security testing, the lab is set up on a private virtual network.

## __Lab Configurations__

<img width="437" height="762" alt="image" src="https://github.com/user-attachments/assets/7c7bd07b-5f7c-4265-8c67-f2a49750541e" />

<br><br>
## __Below are the Steps i Followed:__

<img width="1172" height="276" alt="image" src="https://github.com/user-attachments/assets/a583c8ca-cc9b-4c6d-9c07-4a29ae74b7d9" />


### **Step 1:** **Download & install 7-zip**
<img width="1053" height="398" alt="image" src="https://github.com/user-attachments/assets/b30ff42d-3717-49fd-9ea1-8e2b8164fbdb" />

_7-Zip was installed to extract the Kali Linux virtual-machine package, which is distributed as a .7z archive._


### **Step 2:** **Download & install Virtualbox**

The VirtualBox was downloaded and installed as a Hypervisor.

<img width="1230" height="607" alt="image" src="https://github.com/user-attachments/assets/1161aa45-c403-4d69-8a01-ffa9cc745a1d" />

### **Step 3:** **Create the NAT Network** 
A dedicated NAT Network was created in VirtualBox as follows:

**Configuration:** Network Name:  _NatNetwork_  IPv4 Prefix: _10.0.0.0/24_  DHCP: _Enabled_  IPv6: _Disabled_

<img width="1912" height="1017" alt="image" src="https://github.com/user-attachments/assets/179fafa6-d554-44cf-8356-5dc32488d58e" />

A **NAT Network** was chosen because multiple virtual machines connected to the same NAT Network can communicate with each other while also having outbound network connectivity.

This will enable communication between target virtual machines (VMs) and potential attackers within the lab.

### Step 4. Download & import Kali Linux 
The Kali-Linux virtual machine (vm) was downloaded from the official Kali Linux website and imported into the VirtualBox.

<img width="717" height="601" alt="image" src="https://github.com/user-attachments/assets/41eddd6f-40e4-47d7-ba85-993a4017ac52" />

_Extracting Kali-Linux files_


The VM was allocated 2048 MB of RAM as per the below: 
<img width="1260" height="897" alt="image" src="https://github.com/user-attachments/assets/63fb8d37-e293-4f72-97b2-d2bd8f2bf2ff" />
<br><br>
<img width="1740" height="772" alt="image" src="https://github.com/user-attachments/assets/4b25fd1f-09be-49d4-81b2-f4d5e723e3e1" />  
_The VM network adapter was configured as per the above._

### Step 5. Setup the IP configuration of Kali Linux

The Kali Linux network configuration was checked and configured with a consistent IPv4 address as follows:

<img width="1265" height="797" alt="image" src="https://github.com/user-attachments/assets/0af50d79-76d0-495f-b6c9-762a2f92cdf9" />

_A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises._

### Step 6. Take snapshot of the VM

A VirtualBox snapshot was made once the first setting was finished.  The snapshot depicts the laboratory's clean baseline.
In the event that a subsequent exercise modifies or damages the virtual machine configuration, the machine can be restored to this baseline.

<img width="1256" height="768" alt="image" src="https://github.com/user-attachments/assets/08fae74a-853e-478c-a94d-a59e612921e1" />

#### Starting Kali-linux
<img width="1907" height="462" alt="image" src="https://github.com/user-attachments/assets/bb742060-3e94-4b4d-bad4-4a0f82407268" />


## Below are some of the challenges experience while setting up the lab.
#### Internet Connectivity Issues After Static IP Configuration

Internet connectivity issues were experienced after manually configuring the IPv4 settings.
<img width="916" height="693" alt="image" src="https://github.com/user-attachments/assets/d8087e3b-ab9e-4793-8a12-cf2da49abfb1" />
<img width="1248" height="673" alt="image" src="https://github.com/user-attachments/assets/1f5d855f-d15a-4c69-8c11-44690ae17b9b" />

### How the Internet Connectivity issue was Fixed

**Step 1: Resetting the Network Card**

<img width="1270" height="902" alt="image" src="https://github.com/user-attachments/assets/5e99b5b3-c999-485a-987f-dd20470541b9" />

<br><br>
**Step 2: The below command was used to fix the Internet connectivity issues**

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

<img width="1231" height="772" alt="image" src="https://github.com/user-attachments/assets/7779a7da-850c-435a-956a-8d4c6c5842df" />

<br><br>

**Connectivity issues fixed/Internet restored**

<img width="1265" height="801" alt="image" src="https://github.com/user-attachments/assets/09141419-258e-4da2-9560-a04a5c87cb43" />

<br>

## 💡 What I Learned
Through this project, I gained knowledge about setting up a virtual environment for cybersecurity practice. 

_**The key concepts I learned amongst others, include:**_

**- Virtual Machine Networking**

I have learned how VirtualBox virtual network adapters connect virtual machines to various networks and how network setup influences machine-to-machine communication.

**- NAT vs NAT Network**

A NAT network and a standard NAT configuration have distinct purposes.

A NAT network provides network address translation for external connections while enabling communication between several virtual machines (VMs) connected to the same virtual network.  Because of this, it can be used to create a multi-machine cybersecurity lab.

**- Static IP Configuration**

I have learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

**- VM Snapshots**

I discovered that before engaging in risky or experimental behaviors, a clean snapshot should be taken.
This offers a known-good recovery point for prospective cybersecurity drills. 

**- Documentation**

I have learned that documentation is a crucial component of a professional cybersecurity project, e.g. documenting commands, configurations, screenshots, issues, and fixes.

## 🔐 Security & Ethical Use

This lab is solely meant to be used for educational reasons.

## 🔗 Tools & Resources

**7-Zip:** https://7-zip.org/download.html  
**VirtualBox:** https://virtualbox.org/wiki/Downloads   
**Kali Linux:** https://kali.org/get-kali    

## 👤 Author

**Iyaloo Shivute**    
Cybersecurity Intern B082

LinkedIn:  www.linkedin.com/in/iyaloo-shivute

## 📌 Project Information
**Program Name**: Cybersecurity at Networkwalks | **Week**: 01 | **Project**: Cybersecurity & Pentesting Lab Setup | **Repository**: GitHub
