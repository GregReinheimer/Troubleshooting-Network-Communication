# Troubleshooting Network Communication
## Workstations losing connection to network
### Description
**In this lab two workstations lost connection to the network. The tools I used to resolve was the ping command, verifying the activity network lights on the workstations, and checking the Windows Settings app. I tested a number of theories and implemented solutions.** 

**Step 1: Verify Cisco switch ports**

![A1](A1.png)
**Ports 1 and 3 show no blinking lights, therefore no network traffic activity. Trace the ports to the patch panel to identify the specific workstations. The two workstations not connected are the executive and office 1 machines.**

**Step 2: Use Powershell or Command Line on admin workstation and ping each computer on the floor.**

