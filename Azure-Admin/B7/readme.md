# Configure Blob Storage with Private Access

## About
In this challenge, you will create an Azure storage account with a private container, and then configure a web app to use that container for storage. 
## Overview 
Configure Blob Storage with Private Access
Challenge Overview


Understand the scenario
You are an Administrator for Hexelo, an organization that is migrating their primary Web App from their data center to Azure. In this Challenge Lab you will configure storage for various binary large object (blob) files used by a Web App. First, you will create a Storage account that has a private blob container, and then you will upload blob files to the container. Next, you will generate a shared access signature (SAS), and then you will configure application settings in a web app. Finally, you will test the configuration using a test page provided with the web app.

## Started

### Create a Storage account that has a private blob container


- Sign in to the Microsoft Azure portal.
- Create a Storage account named sa58976641 in the CSSClod58976641 resource group, by using Standard performance and Locally-redundant storage (LRS).
- Add a blob container named private to the sa58976641 Storage account, setting the public access level to Private.

![alt text](/images/B71.png)
- Copy the key1 Storage account access key value here: TestingABCC8r3Wy3Fokaytestingkey1rL+A

Check your work

- Verify that you have created a storage account with name prefixed by sa.

- Verify that you have created a container named private in the storage account.

- Verify that you have set the public access level to Private for the private container in the storage account.

- Verify that you have copied the key1 storage account access key.

### Upload files to the private container


- Upload any image file (for example, .JPG, .PNG, or .GIF) on your computer to the private container, in the sa58976641 Storage account, as a 64 KiB block blob by using the Hot access tier.

![alt text](/images/b72.png)
- Add a Blob index tag on the uploaded blob file by using the Key/Value pair of source / PrivateFiles.

- Copy the URL property value of the uploaded blob file, and then enter it in the following text box: https://sa58976641.blob.core.windows.net/private/WhatsApp Image 2026-02-06 at 9.03.09 PM.jpeg


- Upload a second image file (for example, .JPG, .PNG, or .GIF) on your computer to the private container, in the sa58976641 Storage account, as a 256 KiB block blob by using the Cool access tier.

![alt text](/images/b73.png)
- Note that the list of blob files is sorted by file name alphabetically, not by creation time.

- Add a Blob index tag on the second uploaded file by using the Key/Value pair of source / ArchivePrivateFiles.

![alt text](/images/b74.png)

- Copy the URL property value of the second uploaded blob file, and then enter it in the following text box:https://sa58976641.blob.core.windows.net/private/hanuman.jpeg


Check your work
- Verify that you have uploaded a blob file to the private container by using the hot access tier.

- Verify that you have copied the URL property of the first blob file in the private container.

- Verify that you have uploaded a second blob file to the private container by using the cool access tier.

- Verify that you have copied the URL property of the second blob file in the private container.

- Verify that you have added a blob index tag to both blob files in the private container.


### Generate a SAS token for the private container



- Generate a SAS token for the private container that allows read access for 8 hours, copy the token value, and then enter the value in the following text box:



- Add application settings to the wa58976641 Web App by using the values in the following table. For any property that is not specified, use the default value.

| Name | Value |
| :--- | :--- |
| StorageAccountName | sa58976641 |
| StorageAccountKey | 0MWe756zH5 |
| StorageAccountSAS |dfdfdf |

![alt text](/images/b75.png)
> Select Add

![alt text](/images/b76.png)


![alt text](/images/b77.png)

- Ensure that the wa58976641 Status is Running, open the Web App home page by using the Default domain, and then select the Test Blob Containers link to open the File Test page.

![alt text](/images/b78.png)
- It may take a minute for the home page to open for the first time.

![alt text](/images/b79.png)

- The File Test page should be displayed.The File Test page

- On the File Test page, enter the values displayed in the following table, and then select Test.


| Name | Value |
| :--- | :--- |
| StorageAccountName | sa58976641 |
| StorageAccountKey | 0MWeC8r3Wy3FlVqC+lrL+AStkI9Jgg== |
| StorageAccountSAS | TOkeneljrle |


![alt text](/images/b710.png)


- You should see a message: You have properly configured the private blob container but not the public blob container. Public container does not exist. This is correct, as you will only create a private container in this Challenge Lab.

![alt text](/images/b711.png)

![alt text](/images/b712.png)
- The File Test page should be displayed after the test.The File Test page after testThe Test Status should be set to 2 to show success.


- On the File Test page, locate the message: These are the files in the private container without a SAS. These links should fail.

- Attempt to open the blob files by using the links provided. You should see an error message in the browser: Public access is not permitted on this storage account..

- On the File Test page, locate the message: These are the files in the private container with a SAS. These links should return files.

- Open the blob files by using the links provided-you should see your image files open in the browser.

Check your work
- Verify that you have created an application setting named StorageAccountName in the web app.

- Verify that you have created an application setting named StorageAccountKey in the web app.

- Verify that you have created an application setting named StorageAccountSAS in the web app.

- Verify that you have proved that the first blob file can be accessed by using the URL.

- Verify that you have proved that the second blob file can be accessed by using the URL.



### Summary :shipit:

Congratulations, you have completed the Configure Blob Storage with Private Access Challenge Lab.

You have accomplished the following:

- Provisioned Azure storage.
- Created a private blob storage container.
- Uploaded files to the blob container.
- Added blob index tags to files.
- Generated a SAS token for the container.
- Added application settings to a Web App.
- Verified that a Web App has access to files in the blob container.
