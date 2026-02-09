# Configure a Virtual Machine by Using a Custom Script Extension

## About
In this challenge, you will automate the configuration of a web app on a new server. First, you will create a storage account, and then you will create a Windows virtual machine. Next, you will create the configuration files. Finally, you will apply a PowerShell Desired State Configuration (DSC) extension, and then you will verify that the web app loads. Note: Once you begin the challenge, you will not be able to pause, save, or exit and then return to your challenge. Please ensure that you have set aside enough time to complete the challenge before you start.

## Overview 
Understand the scenario

You are an Administrator for Hexelo, and organization that needs to manage Windows® virtual machines in Azure®.

In this Challenge Lab, you will automate the configuration of a web app on a new server. First, you will create an Azure storage account, and then you will create a Windows virtual machine. Next, you will create a custom Windows PowerShell® script, and then you will upload the script to the Azure storage account. Finally, you will install the web app in the virtual machine by using a custom script extension.

## Started

### Create a storage account

- Sign in to the Azure portal.
- Select the Copy to clipboard icon to copy the text string to the clipboard.
- Create a storage account named sa58968062ais in the rg1lod58968062 resource group by using the default settings.
![alt text]({93DE175F-8F98-4BAE-AE25-D8CB50AF43D7}.png)

- Add a container named scripts to the sa58968062ais storage account.

![alt text]({FD4D46E5-7B80-4948-8F5F-070DD85DCFA3}.png)

### Create an Azure virtual machine

- Create a virtual machine by using the values in the following table. For any property that is not specified, use the default value.
| Property | Value |
| :--- | :--- |
| **Resource group** | rg1lod58968062 |
| **Virtual machine name** | VM1 |
| **Image** | Windows Server 2019 Datacenter - x64 Gen2 |
| **Size** | DS1_v2 |
| **Username** | azureuser |
| **Password** | dn2BYbAMVu26 |
| **Select inbound ports** | HTTP (80), RDP (3389) |
| **Boot diagnostics** | Disable |
- While it is possible to add the custom script extension at the time that you create the virtual machine, in this Challenge Lab, you will add the extension in the next task.
![alt text]({E012D03E-1242-40FF-9466-9D9DA988E332}.png)
- Do not continue until the deployment is complete. This may take a few minutes.
- Record the public IP address of VM1 in the following Public IP Address text box:
![alt text]({943361D8-4FDA-4724-AC5B-A360F27FEB3F}.png)
Public IP Address: 74.235.200.237

You will use the public IP address in an upcoming task.
### Create a custom PowerShell script

- Copy the content from the Windows PowerShell configuration script, paste the content into a text editor-for example, Notepad-on your local computer, and then save the file on your desktop as Install-WebApp.ps1.

```
# Configure firewall rule
netsh advfirewall firewall add rule name="http" dir=in action=allow protocol=TCP localport=80

# Install IIS feature
Install-WindowsFeature Web-Server -IncludeManagementTools

# Copy new index.html file
Invoke-WebRequest 'https://raw.githubusercontent.com/LODSContent/ChallengeLabs_ArmResources/master/Labs/AIS/index.html' -OutFile 'C:\inetpub\wwwroot\index.html'

```
- Upload the Install-WebApp.ps1 file to the scripts container in the sa58968062ais storage account.
Check your work
![alt text]({5709DB2F-ED06-4867-B413-08992CA2BE31}.png)

- Verify that you have uploaded the Install-WebApp.ps1 file to the scripts container in the storage account.

![alt text]({4AF3AA56-E5C2-4B9D-8D84-7D3A79FB8A7D}.png)


### Add a custom script extension

- Add a custom script extension for the VM1 virtual machine by using the Install-webApp.ps1 script file in the sa58968062ais storage account.
![alt text]({7E7C2B2F-8980-45EC-89AC-D901251ACCCD}.png)

- Wait until the custom script extension has been provisioned.
![alt text]({E6EC45A9-8368-4F50-92F0-2633E827C5FC}.png)
- The custom script extension showing a status of provisioning succeeded
This will take approximately 3-5 minutes.
![alt text]({CC1171F4-7A6C-4373-9E82-272F37883DA2}.png)
- Open a new browser window, go to http://74.235.200.237 to test the configuration, and then refresh the browser window until the Test Web App Deployment page is displayed.
- It may take as long as 10 minutes for the virtual machine extension to be created and for the script to finish running, but you can start testing and refreshing the page while the Azure deployment is still in progress. When the deployment is finished, you will see the following web page:
Before Script Deployment
![alt text]({F5B5DCFE-CE96-40F8-932E-B50D4B147EA7}.png)

The Test Web App Deployment page
![alt text]({E47815E2-087E-4C15-8A08-818624BFB83B}.png)
> Check your work
- Verify that you have added a custom script extension to VM1 by using the Install-webApp.ps1 script.
- Verify that you have displayed the Test Web App Deployment page that was installed by the custom script extension.


### Summary :shipit:
# 🎊 Challenge Complete: Automation Accomplished!

Congratulations on successfully automating your web app deployment! You've demonstrated a solid grasp of **Cloud Infrastructure** and **Configuration Management**.

###  Summary

You have completed the end-to-end lifecycle of a managed web server deployment:

*   **Storage Provisioning**: Established an **Azure Storage Account** to host essential deployment artifacts.
*   **Server Deployment**: Provisioned a **Windows Virtual Machine (VM1)** with specific sizing and networking requirements.
*   **Desired State Authoring**: Developed the configuration files required to define the web server role.
*   **DSC Extension Orchestration**: Leveraged the **PowerShell Desired State Configuration (DSC)** extension to automate the installation of IIS and the web app, ensuring "zero-touch" setup.
*   **Service Verification**: Validated that the automation was successful by confirming the web app is live and reachable.
