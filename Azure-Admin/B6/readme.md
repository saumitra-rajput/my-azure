# Configure a Virtual Machine Scale Set

## About
In this challenge, you will configure an Azure virtual machine scale set. First, you will create a scale set that uses load balancing and a common Linux operating system disk image. Next, you will increase the number of virtual machines in the scale set. Finally, you will stop and deallocate a virtual machine instance. 

## Overview 
Understand the scenario
You are an Administrator for Hexelo, an organization that needs to manage highly elastic demand requirements for a critical, client-facing application.

In this Challenge Lab, you will configure an Azure® virtual machine scale set. First, you will create a scale set that uses load balancing and a common Linux operating system disk image. Next, you will increase the number of virtual machines in the scale set. Finally, you will stop and deallocate a virtual machine instance.

## Create a virtual machine scale set
- Sign in to the Microsoft Azure portal.
- Create a virtual machine scale set by using the values in the following table. For any property that is not specified, use the default value.

| Property | Value |
| :--- | :--- |
| Resource group | rg1lod58975668 |
| Virtual machine scale set name | webappscaleset |
| Orchestration mode | Uniform |
| Image | Ubuntu Server latest version - x64 Gen2 |
| Size | DS1_v2 |
| Authentication type | Password |
| Username | azureuser |
| Password | VcMuukx%=qW^ |
| Public IP address | Enabled |
| Load balancing options | Azure load balancer |
| Select a load balancer | Create a load balancer |
| Load balancer name | webappscaleset-lb |

![alt text](/images/b61.png)

- The deployment will take 2-3 minutes to complete.

- Verify that there are two virtual machine instances running in the webappscaleset scale set.
![alt text](/images/b62.png)
Check your work
- Verify that you have created a VM scale set that has 2 instances.

### Increase the number of virtual machine instances in a scale set

- Open an Azure Cloud Shell Bash session without mounting a storage account.
- Increase the number of virtual machine instances to 3 in the webappscaleset scale set that is in the rg1lod58975668 resource group by using the az vmss scale command.
```
az vmss scale --resource-group rg1lod58975668 --name webappscaleset --new-capacity 3
```
![alt text](/images/b63.png)

- Verify that there are three virtual machine instances running in the webappscaleset scale set.
![alt text](/images/b64.png)
- Periodically refresh the Instances page until you see three running virtual machines that have a Status of Running. You may temporarily see an extra virtual machine instance being created, which is a normal part of the imaging process. Ultimately, you will end up with three virtual machines after this step.

- The Instances page with three instances displayed

Check your work
- Verify that you have increased the number of instances in the scale set to 3.

### Deallocate a virtual machine instance in a scale set


- Deallocate the webappscaleset_0 virtual machine instance in the webappscaleset scale set.
![alt text](/images/b65.png)
- Refresh the Instances page and then verify that the status of the webappscaleset_0 instance is Stopped (deallocated).
Check your work
- Verify that you have deallocated instance zero in the VM scale set.


![alt text](/images/b66.png)

### Summary :shipit:

Congratulations, you have completed the Configure a Virtual Machine Scale Set Challenge Lab.

You have accomplished the following:

- Created a virtual machine scale set.
- Increased the number of virtual machine instances in a scale set.
- Deallocated a virtual machine instance in a scale set.