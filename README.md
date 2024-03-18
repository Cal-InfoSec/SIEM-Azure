# Building a Home Lab in Oracle Virtual Box (Sandbox Enviroment) 
Setting up an Enviroment to for testing new methods, processes, or possible tools to use. 
## Objective
Building a home lab is to create a practical learning environment where you can develop and enhance your cybersecurity skills, gain hands-on experience, and prepare for professional certifications and challenges in the field.

### Skills Learned
- Virtualization: Learn how to create, configure, and manage virtual machines (VMs) in Virtual Box.
- Operating Systems: Gain experience installing, configuring, and securing various operating systems (OS) within virtual machines.
- Network Configuration: Practice setting up and managing virtual networks, including IP addressing, DHCP, DNS, and routing.
- Network Configuration: Practice setting up and managing virtual networks, including IP addressing, DHCP, DNS, and routing.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
**Preface**: Before starting this Project, ensure your PC has Virtualization enabled and your PC specs are capable of Virtualizing.
drag & drop screenshots here or use imgur and reference them using imgsrc
Every screenshot should have some text explaining what the screenshot is about.

 ![Oracle Website](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/7e1b309e-8b25-4f54-8128-2d4870d3a7c5)
 1. **Step 1**: To Start Off lets download [Oracle Virtual Box](https://www.virtualbox.org/). Once on the Webpage, Click the "Download Virtual Box" button which will take you to it's latest Platform packages. Click the Hosts that matches your OS. I will be doing a Windows installation.

![VM custom set up](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/eeace1f8-334b-4a4d-af6c-a071b940170d)   
 2. **Step 2**: Once Downloaded, Click next which will take you to the custom set up page which you can use to better utilize your systems re!
   - For instance, if you don't have enough storage on your C: Drive or Main Drive, install the application on another drive. Sometimes you may miss some dependencies on your system and have to download additional items. Allow the Setup programm to download these dependencies and follow through with the set up.

[VM oracle App page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/e6562eae-2e27-46c8-8c3a-fd655818d5f0)
sources.
 3. **Step 3**:Once Downloaded, the application page should look like this.
 ![Win Installation Media Web Page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/1b9de1c8-51c0-4f62-88b2-cd12cdbf63e0)
 4. **Step 4**: Next we'll need to download our ISO file or our Operating System we're going to virtualize. We will be virtualizing a [Windows 10 OS.](https://www.microsoft.com/en-ca/software-download/windows10)
  - Once you download and open the setup file. Accept terms and then it will show a page asking what we would like to do.
![Win tool Installation Media option](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/00658c45-6d90-4d04-9afb-4426cd4198b6)
 5. **Step 5**: On the "What do you want to do?" page, we're going to select the **Second** option, Create installation media.
    - You can Select your language options to whatever you may like.
![Win tool Installation ISO file](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/f783d8e3-2056-4f2e-9613-c6772d03e6d4)
 6. **Step 6**: Choosing which Media to use should be an ISO File which can be downloaded anywhere on your PC. Please remember where you installed your ISO file.
      ![VM oracle New VM Pg](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/136f0de0-61ac-489a-b596-50e4cce2397e)
 7. **Step 7**: Now we'll set up our VM in Oracle Virtual Box. Click the Spiky Blue Ball Icon labeled "New". Name the sandbox VM to whatever you deem fit. Keep the folder selected the same. For the ISO Image, locate and select the Windows ISO file downloaded prevoiusly downloaded.
     - Check "Skip Unattended Installation" if you'd like to conifigure the amount of resources this VM utilizes. This can be updated later on. I will be skipping the Unattended Installation for this project.

 8.  
