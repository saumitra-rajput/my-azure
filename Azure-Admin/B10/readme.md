# Configure Global Virtual Network Peering

## About
In this challenge, you will configure a virtual network peering between the virtual networks for two applications hosted in different Azure regions. First, you will review existing Azure resources, and then you will verify that you are unable to add virtual network peerings between the existing virtual networks. Next, you will remove overlapping address spaces in the virtual network configuration. Finally, you will configure global virtual network peering between the two virtual networks. 

## Overview 
Configure Global Virtual Network Peering
Challenge Overview

Understand the scenario
You are an Azure® Security Engineer for Hexelo, an organization that needs to manage a virtual network.
In this Challenge Lab, you will configure a virtual network peering between the virtual networks for two applications hosted in different Azure regions. First, you will review existing Azure resources, and then you will verify that you are unable to add virtual network peerings between the existing virtual networks. Next, you will remove overlapping address spaces in the virtual network configuration. Finally, you will configure global virtual network peering between the two virtual networks.

## Started

### Steps
- Sign in to the Microsoft Azure portal.
- Select the Copy to clipboard icon to copy the text string to the clipboard.
Record the public IP address of VM1 in the following Public IP Address text box:
Public IP Address
You will use the public IP address in an upcoming task.
Review the address space and subnet configurations of the VNET1 virtual network.
Review the address space and subnet configurations of VNET2.
The address spaces of virtual networks that you intend to connect should not overlap. You will correct this in an upcoming task.

![alt text]({F999A0BA-740E-4591-8DC1-2405E0BB982A}.png)

Check your work
Verify that you recorded the public IP address of VM1.

### 

addspace
![alt text]({52605249-6DF8-45B9-ADDD-53D8AB9C7989}.png)
subnet
![alt text]({2107E34A-C401-48E4-9E4B-D04EDF004628}.png)
select Ip2 for vmnic2
![alt text]({03E038FA-0C95-4768-B650-C64309A19FFC}.png)
Delete sub1 for vnet2
![alt text]({A0EEE7F9-B198-4B4A-A9E1-3CE06788D14F}.png)
delete addspace in vnet2
![alt text]({7C9DDE35-1438-4450-9D5D-272E6D68B65F}.png)
Adding Vnet peering
![alt text]({D19D5DA1-CBB7-4875-9B95-687AAA5BBF55}.png)

2to1
![alt text]({F8E8B753-DA47-4238-9B34-E893C5BFA589}.png)
1to2
![alt text]({B3F97B90-44AF-487B-BBD8-093275AA8945}.png)

ssh and ping
![alt text]({856A0724-1FC0-40D1-9CEA-8D1374628942}.png)

### Summary :shipit:

Summary
Congratulations, you have completed the Configure Global Virtual Network Peering Challenge Lab.
You have accomplished the following:
Reviewed existing Azure resources.
Added a virtual network peering.
Remediated overlapping address spaces.
Configured global virtual network peering.
