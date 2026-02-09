# Configure a Route Table by Using the Azure Portal
Challenge Overview

Understand the scenario
You are an Administrator with Hexelo, a company that is deploying virtual networks for Azure workloads. You need to ensure that traffic is routed through an Azure Firewall. In this challenge you will create a route table to manage the traffic for Azure Firewall. Then, you will create an Azure Firewall in a pre-configured virtual network. Finally, you will create a user-defined route to route the resources in your subnet so they can use the Azure Firewall.
Navigating the Challenge Lab

## About
In this challenge, you will create a route table using Azure Marketplace and define static routes. Note: Once you begin a challenge you will not be able to pause, save, or return to your progress. Please ensure you have set aside enough time to complete the challenge before you start.
## Challenge 

### Create a route tabl

-    Sign in to the Azure portal.
-    Create a route table named RouteTable58965041 in the Vnet-RGlod58965041 resource group. Specify East US Region as the location for the route table.
![alt text](/images/b31.png)

### Create an Azure

Create an Azure Firewall by using the values in the following table. For any property that is not specified, use the default value.

> Azure Firewall Configuration

| Property | Value |
| :--- | :--- |
| **Resource group** | Vnet-RGlod58965041 |
| **Name** | AzureFirewall |
| **Region** | East US |
| **Firewall SKU** | Standard |
| **Firewall management** | Use Firewall rules (classic) to manage this firewall |
| **Choose a virtual network** | Use existing |
| **Virtual network name** | WebAppVnet |
| **Public IP address (new)** | azureFirewalls-ip |
| **Enable Firewall Management NIC** | *(Blank)* |

![alt text](/images/b32.png)

### Add a route to Azure Firewall

 -   Create a route named AzureFWRoute in the RouteTable58965041 route table.
Azure Firewall IP
![alt text](/images/b33.png)
 -   In the routing table entry, add a route with an address prefix of 0.0.0.0/0 and a Virtual appliance next hop address of 10.1.0.4 (the internal IP address of the Azure Firewall).

![alt text](/images/b34.png)


### Summary :shipit:

Congratulations

- You have completed the Configure a Route Table by Using the Azure Portal Challenge Lab.
- You have accomplished the following:
- Provisioned a route table.
- Provisioned an Azure Firewall
- Created a user-defined route for an Azure Firewall


