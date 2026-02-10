# Configure Blob Storage with Public Access 

Ps note: for images ext it will be b91 series

## About

In this challenge, you will create an Azure storage account with a public container, upload files to the account, and test public access to the account. 

## Overview ## Overview 
Configure Blob Storage with Public Access
Challenge Overview


Understand the scenario
You are an Administrator for Hexelo, an organization that is migrating their primary web app from their data center to Azure. In this Challenge Lab you will configure storage for various binary large object (blob) files used by the web app. First, you will create a storage account that has a public blob container. Next, you will upload blob files to the container. Finally, you will test the configuration by using a test page provided with the web app.
## Started

### Create a storage account that has a blob container
- Sign in to the Microsoft Azure portal.
- Create a storage account named sa59005671 in the CSSClod59005671 resource group, by using Standard performance, Locally-redundant storage (LRS), and Allow enabling anonymous access on individual containers.

![alt text](/images/b91.png)

Allow anomonys access

![alt text](/images/b92.png)
- Add a blob container named public to the sa59005671 storage account, setting the public access level to Blob.

- Copy the key1 storage account access key value here: TESTKeyBlob

Check your work
- Verify that you have created a storage account with a name prefixed by sa.
- Verify that you have created a container named public in the storage account.
- Verify that you have set the public access level to Blob for the public container in the storage account.
- Verify that you have copied the key1 storage account access key.


### Upload image file

- Upload any image file (for example, .JPG, .PNG, or .GIF) on your computer to the public container, in the sa59005671 storage account, as a 64 KiB block blob by using the Hot access tier.
- Add a Blob index tag on the uploaded blob file by using the Key/Value pair of source / Portal.
Expand this hint for guidance on adding a Blob index tag to a file.

![alt text](/images/b93.png)

Check your work
- Verify that you have uploaded a blob file to the public container in the storage account.
- Verify that you have uploaded a blob file to the public container by using the hot access tier.
- Verify that you have uploaded a blob file to the public container by using the block blob type.
- Verify that you have added a blob index tag to the blob file in the storage account.

### Test the web application

- Copy the URL property value of the uploaded blob file here: <storage_account_name>.blob.core.windows.net
- Add a Blob index tag on the second uploaded file by using the Key/Value pair of source / Archive.
Copy the URL property value of the second uploaded blob file here: 

![alt text](/images/b94.png)
![alt text](/images/b95.png)
- Open the Web App home page from the wa59005671 blade in the portal, and then select the Test Blob Containers link to open the File Test page.

- The File Test page should be displayed.The File Test page
- On the File Test page, in Storage account name, enter sa59005671, in Storage account key, enter <storagekey>, and then select Test to confirm your work.

- The File Test page should be displayed after the test.The File Test page after testThe Test Status should be set to 1 to show success.
- You have provided the storage account name and the access key to the web app so it has full access to the storage account and is able to list the blob files in the container.
- On the File Test page, open the blob files by using the links provided. You should see your image files open in the browser.
- When you open the blob files by using the links provided, you are then accessing the files by using anonymous read operations outside of the application. This shows the blob public access level in action.

Check your work
- Verify that you have copied the URL property of the blob file in the public container.
- Verify that you have uploaded a second blob file to the public container by using the cool access tier.
- Verify that you have added a blob index tag to the second blob file in the storage account.
- Verify that you have copied the URL property of the second blob file in the public container.
- Verify that you have proved that the first blob file can be accessed anonymously by using the URL.
- Verify that you have proved that the second blob file can be accessed anonymously by using the URL.

webapp
![alt text](/images/b96.png)

![alt text](/images/b97.png)
### Summary :shipit:

Congratulations!

You have completed the Configure Blob Storage with Public Access Challenge Lab.
You have accomplished the following:
Provisioned Azure storage.
Created a blob storage container with public blob access.
Uploaded files to the blob container.
Added blob index tags to files.
Verified that a web app has access to files in the blob container.
