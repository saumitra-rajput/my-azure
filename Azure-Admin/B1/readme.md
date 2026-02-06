# Configure a Near Real-Time Metric Alert

## About

In this challenge, we will configure a near real-time metric alert. First, you will create a Linux virtual machine. Next, you will create an action group, and then you will create a near real-time metric alert that uses the action group. Finally, you will test the alert.

## Challenge 
You are an Administrator with Hexelo, an organization that needs to manage virtual machines in Azure®.
In this Challenge Lab, you will configure a near real-time metric alert. First, you will create a Linux virtual machine. Next, you will create an action group, and then you will create a near real-time metric alert that uses the action group. Finally, you will test the alert.

## Started




   - Sign in to the Microsoft Azure portal.
   - Select the Copy to clipboard icon to copy the text string to the clipboard.
    Open an Azure Cloud Shell Bash session without mounting a storage account.
    ![alt text](/images/b1.png)

   - Create a new Linux virtual machine that generates an SSH key pair by using the az vm create command and the values in the following table:


        | Property | Value |
        | :--- | :--- |
        | **Resource group** | rg1lod58910673 |
        | **Name** | VM1 |
        | **Image** | Ubuntu2204 |
        | **Size** | Standard_DS1_v2 |
        | **Admin Username** | azureuser |
     
     ![alt text](/images/b2.png)
   - Record the public IP address of VM1 in the following Public IP Address text box:
    Public IP Address :23.100.23.95
   - Create an SSH connection to the virtual machine by using azureuser@.
    ![alt text](/images/b3.png)
   -  Update the Linux virtual machine by using the sudo command and the apt-get tool with the update option.
   - Please ensure that you have updated the Linux virtual machine before moving on to the next task.
   ![alt text](/images/b4.png)
   - Close the Cloud Shell window.
    
> Check your work
   - Verify that you have created a Linux virtual machine named VM1.
   - Verify that you have recorded the public IP address of VM1 for later use.
   - Verify that you have updated the VM1 virtual machine.
### Create an action group

    Create an action group by using the Monitor tool and the values in the following table. For any property that is not specified, use the default value.
Azure Monitor> Alerts> Action group.
![alt text](/images/b5.png)

![alt text](/images/b6.png)
| Property | Value |
| :--- | :--- |
| **Resource group** | rg1lod58910673 |
| **Action group name** | Cloud Operations |
| **Short name** | CloudOps |
| **Notification type** | Email/SMS/Push/Voice |
| **Notification name** | Email CloudOps |
| **Email** | Your personal or work email address |

  
Verify that your personal email has been added to the Cloud Operations action group.
Check your work

![alt text](/images/b7.png)

### Create a virtual machine metric alert


    Create an alert rule named Percentage CPU greater than 85 for VM1 that will send a notification that has a description of Alert when the average Percentage CPU is greater than 85 to the Cloud Operations alert group.
    Check your work
![alt text](/images/b8.png)

![alt text](/images/b9.png)
Verify that you have created an alert rule named Percentage CPU greater than 85 that will send an email to the Cloud Operations alert group when the average percentage CPU on VM1 is greater than a threshold of 85 for a period of one minute.

### Test the near real-time metric alert


  - Re-establish an ssh connection to VM1 as azureuser@23.100.23.95.
  - Install the stress tool by using thesudo and apt-get commands.
  - Generate a CPU load of 8 hogs on the virtual machine for a period of 480 seconds by using the sudo and stress commands.
   - Leave the Cloud Shell window open to ensure that the generated CPU load triggers a notification alert.
   - It may take up to 10 minutes for the alert to become active.
   - Verify that you have received an email notification that contains the text  Azure monitoring rule 'Percentage CPU greater than 85' was activated for 'virtualMachines/VM1'.


Check your work


Verify that you have generated a CPU load that triggered an email notification stating that The Azure monitoring rule 'Percentage CPU greater than 85' was activated for 'virtualMachines/VM1'.

```
sudo apt-get stress

sudo stress --cpu 8 --timeout 480

```


### Summary

Summary
Congratulations, you have completed the Configure a Near Real-Time Metric Alert Challenge Lab.
You have accomplished the following:
Created a Linux virtual machine.
Created an action group.
Created a near real-time metric alert on a virtual machine.
Tested the near real-time metric alert.