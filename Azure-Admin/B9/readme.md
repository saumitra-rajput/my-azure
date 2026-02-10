# Configure Custom DNS Zone for Private Domain

## About
In this challenge, you will use PowerShell to add a Private domain DNS Zone into Azure. 
## Overview 
Configure Custom DNS Zone for Domain

Understand the scenario

You are an Administrator at Hexelo, a company that is creating a test domain in Azure. The test domain will be called "TestDomain". You will use a DNS Zone in Azure for the domain. A virtual network named TestVnet will be used to maintain your DNS zone. You will complete the steps by using the Azure cloud shell utilizing PowerShell.
## Started

### Create a DNS Zone
- Sign in to the Microsoft Azure portal.
- Create an Azure cloud shell that uses a storage account named lrsstore94352 and shell as the file share name.
- Using the New-AzDNSZone cmdlet, create a new DNS Zone named TestDomain59004565.com in the TestDomainlod59004565 resource group.

- Steps to create a powershell 
![alt text](/images/b81.png)
![alt text](/images/b82.png)

- Created Test DNS zone
```
New-AzDNSZone -name "TestDomain59004565.com" -ResourceGroupName "TestDomainlod59004565"
```

![alt text](/images/b83.png)

Check your work

- Verify that you have created the DNS zone.
- You have successfully created the DNS zone.


### Create a DNS Record Set for your TestDomain

- Using the New-AzDNSRecordSet cmdlet, create a single A type resource record in the TestDomain59004565.com DNS zone that has the following properties:

| Property | Value |
| :--- | :--- |
| **Name** | www |
| **Type** | A |
| **IP Address** | 10.10.10.10 |
| **TTL** | 3600 seconds |

```
New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "TestDomainlod59004565" -TTL 3600 -ZoneName "TestDomain59004565.com" -DnsRecords (New-AzDnsRecordConfig -IPv4Address 10.10.10.10)
```
![alt text](/images/b84.png)

Check your work

- Verify that you have created the A record.
- You have successfully created the A record.

### Summary :shipit:

Congratulations!
- You have completed the Configure Custom DNS Zone for Private Domain Challenge Lab,
- You have used Azure PowerShell to accomplish the following:
   - Provisioned a DNS Zone.
   - Created a record set in the DNS zone