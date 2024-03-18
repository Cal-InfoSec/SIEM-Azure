# Building a Basic Home Lab Running Active Directory (Oracle VirtualBox)
Building and configuring Virtual Machines to house an  Active Directory Enviroment on our Local Machine and Router. 
## Objective
Provides a hands-on learning experience that covers essential concepts and skills in Windows network administration, virtualization, scripting, and user management. It serves as a foundational exercise for those aspiring to pursue careers in system administration, network engineering, or cybersecurity within Windows-based environments.

### Skills Learned
- Virtualization: Learn how to create, configure, and manage virtual machines (VMs) in Virtual Box.
- Operating Systems: Gain experience installing, configuring, and securing various operating systems (OS) within virtual machines.
- Network Configuration: Practice setting up and managing virtual networks, including IP addressing, DHCP, DNS, and routing.
- Network Configuration: Practice setting up and managing virtual networks, including IP addressing, DHCP, DNS, and routing.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
- Oracle Virtual Box
- Active Directory
- Powershell
- Windows Server Manager

### Plan Of Action + Diagram:
![image](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/d0ce77be-5ba7-4cda-bda7-076ab1c340b2)
**Domain Controller Process**
First we're going to gather our Software, Oracle Virtual Box, Windows 10 ISO, and Server 2019 ISO. After Virtual Box is installed, we're going create 2 seperate machines. One with the Win 10 (our client) and the other with Server 2019 (Domain Controller). We'll deploy our Domain controller first as it house our Active Directory and we'll give it two network adapters, one for internal network and one for external (Internet). Once Domain Controller is up and running we're going to assign IP addressing to our **Internal** network. Next We'll install Active Directory(AD) to our Domain controller (DC). Then we'll configure Routing and NAT so the private network can connect to the internet through the DC. On the DC, we're going to them set up DHCP sp when a new client or Windows 10 machine can automatically get assigned an IP address. Before we move onto our client machine we'll run a Power Shell Script to create 100 users.
**Client Machine Process**
Now that our users our created, we'll deploy our Client Machine with the Win 10 ISO file. This Client will be connected to the **Internal** VM network. We'll log into the client with one of user logins generated by our powershell script. 
## Steps For Windows 10 Server Virtual Machine

 ![Oracle Website](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/7e1b309e-8b25-4f54-8128-2d4870d3a7c5)
 1. **Step 1**: To Start Off lets download [Oracle Virtual Box](https://www.virtualbox.org/). Once on the Webpage, Click the "Download Virtual Box" button which will take you to it's latest Platform packages. Click the Hosts that matches your OS. I will be doing a Windows installation.

![VM custom set up](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/eeace1f8-334b-4a4d-af6c-a071b940170d)   
 2. **Step 2**: Once Downloaded, Click next which will take you to the custom set up page which you can use to better utilize your systems re!
   - For instance, if you don't have enough storage on your C: Drive or Main Drive, install the application on another drive. Sometimes you may miss some dependencies on your system and have to download additional items. Allow the Setup programm to download these dependencies and follow through with the set up.

[VM oracle App page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/e6562eae-2e27-46c8-8c3a-fd655818d5f0)
sources.
 3. **Step 3**:Once Downloaded, the application page should look like this.
 
 ![Win Installation Media Web Page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/1b9de1c8-51c0-4f62-88b2-cd12cdbf63e0)
 4. **Step 4**: Next we'll need to download our ISO file or our Operating System we're going to virtualize. We will be virtualizing a [Windows 10 OS.](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
  - Once you download and open the setup file. Accept terms and then it will show a page asking what we would like to do.
    
![Win tool Installation Media option](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/00658c45-6d90-4d04-9afb-4426cd4198b6)
 5. **Step 5**: On the "What do you want to do?" page, we're going to select the **Second** option, Create installation media.
    - You can Select your language options to whatever you may like.
   
![Win tool Installation ISO file](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/f783d8e3-2056-4f2e-9613-c6772d03e6d4)
 6. **Step 6**: Choosing which Media to use should be an ISO File which can be downloaded anywhere on your PC. Please remember where you installed your ISO file.
      
![VM oracle New VM Pg](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/05af67f9-fa6a-42b9-942c-1bc199af4b3e)

 7. **Step 7**: Now we'll set up our VM in Oracle Virtual Box. Click the Spiky Blue Ball Icon labeled "New". Name the sandbox VM to Dpmain controller as this VM will be used to manage another Vm later on. Keep the folder selected the same. For the ISO Image, locate and select the Windows ISO file downloaded prevoiusly downloaded.
     - Check "Skip Unattended Installation" if you'd like to conifigure the amount of resources this VM utilizes. This can be updated later on. I will be skipping the Unattended Installation for this project. Click Next.
    ![VM oracle Summary Page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/7b1c7290-a7ad-4f8c-8f35-f1716f16f6f8)

8. **Step 8**: For Hardware, I will using 4 Gb or 4096 Mbp of Memory and 1 Cpu Core. Virtual Memory I will keep at 50 Gb of Virtual Memory. Your summary Page should look like this^.

![VM Win Setup No Prod Key](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/77d598f1-75ad-4de7-8c3a-9d24daa85ab9)
9. **Step 9**: Next we're going to power on Our new VM within our Virtual Box Manager App. To do so, Click the Green Arrow "Start". Once it's running, a Windows 10 set up should appear. I'll be leaving my OS Language, time etc. all default so click next and install now.

![VM Windows Installing Page](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/436634ca-ae8e-4fdf-a765-892b8f8c0686)
10. **Step 10**: Next select Windows server 2019 Standard Evaluation (desktop experience). Accept License Terms. The type of Installation  we'll be doing is a Custom: Install Windows Only then click next. Next Windows should be Installing!

![VM log in screen](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/148b439d-6c04-49a0-9fe9-5e889a777041)
11. **Step 11**: Once Installed choose a password to memorize then click settings. It'll finish setting up and show a login screen to which you'll input your new password to login. 

![VM Insert Guest Additions File](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/748215d2-0f1a-4499-a9ed-9450c7f9ffbf)
12. **Step 12**: After Logging in you'll want to click yes on making the PC discoverable on the network. close out server Manager for now. To make the input smoother on the VM. At the top of the VM window click the Devices tab and select "Insert Guest Additions CD Image" then go into your File explorer and click "This PC"

![VM Guest Additions Reboot  later](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/b7eb8895-5130-4974-a2b1-6dd867e90912)
13. **Step 13**: Click the blue box with a star on it then click the file "VBoxWindowsAdditions-amd64". Complete the install fully through then select reboot later or reboot now if you'd like. 
![image](https://github.com/Cal-InfoSec/SIEM-Azure/assets/81139563/ff21cf3c-d18d-45ab-bae4-719fe3595586)
14. **Step 14**: Then in the Power setting of your VM, Shut down the VM. Go to your Virtual Box Manager App and start your Machine Back up. should notice a seamless integration of inputs. To Input "Ctrl+Alt+Delete" into the VM. Located at the top of your VM window is an Input Tab, Click the tab then select keyboard and "Ctrl+Alt+Delete". At  this part of the Project, your Home Lab is considered complete. However from here on will be setting up our active directory which will utilize the VM as a Domain Controller.

## Setting up Active Directory

15. **Step 15**:  
16. **Step 16**:
17. **Step 17**:
