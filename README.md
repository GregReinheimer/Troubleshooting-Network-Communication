# Troubleshooting Network Communication
## Workstations losing connection to network
### Description
**In this lab, two workstations lost connectivity in a LAN network. To troubleshoot the issue, I used several tools and methods, including the ping command, verifying NIC activity lights, and checking the Windows Settings application. I tested multiple possible causes and implemented solutions to restore network communication.** 

### Step 1: Verify Cisco Switch Ports

### Observation
**Ports 1 and 3 on the Cisco switch showed no blinking lights, indicating no network traffic activity.**

### Action
**Traced the affected ports to the patch panel to iddentify the corresponding workstations.**

### Result
**The disconnected workstations were identified as:**
- **Executive workstation**
- **Office 1 workstation**

![A1](https://github.com/user-attachments/assets/0bb31466-3522-4335-bb85-37c5a33ecce8)



### Step 2: Ping Each Workstation from the Admin Workstation

### Action
**Used Powershell/CLI on the admin workstation to ping all workstation IP addresses on the network.**

### Result
**Two workstations failed to respond to ping requests.**
- **Packets Sent: 4**
- **Packets Received: 0**
- **Packets Lost: 4**

**This confirmed both systems were disconnected from the network.**

![A2](https://github.com/user-attachments/assets/287bcfce-5e95-49dc-9b7e-e7dd69c9212b)



### Step 3: Verify the Admin Workstation Connectivity

### Action
**Checked the NIC link/activity lights on the back of the admin workstation to confirm network traffic.**

### Result
**The NIC lights were active, indicating a working network connection.**

![A3](https://github.com/user-attachments/assets/51d8a5bf-e8cb-4e01-8675-a22718bdd6f2)

### Additional Verification
**Opened the Windows Settings application and confirmed the Ethernet connection was enabled and connected.**

![A4](https://github.com/user-attachments/assets/aec17b50-fe55-4572-8bcf-9b6d7054e71f)

### Conclusion
**The admin workstation was functioning properly and connected to the network.**



### Step 4: Verify the Executive Workstation Connectivity

### Action
**Checked the NIC link/activty lights on the Executive workstation.**

### Result
**The NIC lights were not blinking, indicating no active network connection.**

![A5](https://github.com/user-attachments/assets/2d7415ce-6811-4b24-88e3-b4f45da22971)


### Additional Verification
**Checked the Ethernet status in the Windows Settings application.**

### Result
**The workstation showed no network connectivity.**

![A6](https://github.com/user-attachments/assets/a1ec50be-36df-4eef-b9d1-03751d260329)


### Initial Troubleshooting Theories
**Possible causes include:**
- **Faulty NIC**
- **Defective Ethernet Cat 6a cable**
- **Faulty connection between the switch and patch panel**


### Step 5: Test for a Faulty NIC

### Action
**Moved the Ethernet cat 6a cable from the add-on NIC to the onboard Ethernet port.**

### Result
**The link/activity lights became active, indicating restored connectivity.**


![A7](https://github.com/user-attachments/assets/b7048d14-fc24-439b-bd41-db2dbfb944ef)


### Verification
**Pinged both the admin workstation and server IP addresses.**

### Result
**Both ping tests were successful.**
- **Packets Sent: 4**
- **Packets Received: 4**
- **Packets Lost: 0**


![A8](https://github.com/user-attachments/assets/3c7285ad-faaf-404d-993b-f80451a2962e)


### Resolution
**The Executive workstation had a faulty NIC.**


### Step 6: Troubleshoot the Office 1 Workstation

### Action
**Repeated the same troubleshooting process used on the Executive workstation.**

### Result
**The NIC and workstation cable tested successfully, eliminating those as possible causes.**

### Additional Verification
**Tested the Ethernet cat 6a cable between the switch and patch panel.**

### Result
**The cable was defective.**

### Resolution
**Replaced the faulty Cat 6a cable, and network connectivity was restored to the Office 1 workstation.**



