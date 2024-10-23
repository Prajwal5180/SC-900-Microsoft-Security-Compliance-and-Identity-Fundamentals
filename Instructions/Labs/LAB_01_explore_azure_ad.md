 
# Lab-01: Explore Microsoft Entra ID User Settings

## Lab scenario

In this lab, you'll access Microsoft Entra ID. Additionally, you'll create a user and configure the different settings, including adding licenses.

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: Accessing Microsoft Entra ID through the Microsoft 365 Admin portal and through the Azure portal
+ Task 2: Creating a basic group
+ Task 3: Create a new user in the Microsoft Entra ID and explore some of the services
+ Task 4: Sign in to the user first time

## Estimated timing: 30 minutes

## Architecture diagram

![](../Images/sc900lab1.png)

## Task 1: Accessing Microsoft Entra ID through the Microsoft 365 Admin portal and through the Azure portal

As a subscriber to Microsoft 365 you're already using Microsoft Entra ID.  In this task, you will walk through accessing Microsoft Entra ID through the Microsoft 365 Admin portal and through the Azure portal.

1. Open another tab in Microsoft Edge, in the address bar enter **[admin.microsoft.com](https://admin.microsoft.com/)** to access the Microsoft 365 admin center.

1. Sign in with the following credentials.
    
    -  In the Sign in window enter following email  then select **Next**.

       * Email : **<inject key="AzureAdUserEmail"></inject>**
     
    -  Enter the admin following password and select **Sign in**.

       * Password : **<inject key="AzureAdUserPassword"></inject>** 
          
1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

    ![](../Images/sc900-image4.png)

1. Under Admin centers, select **Identity** (you may need to scroll down).  

    ![](../Images/sc900-image5.png)

1. A new browser page opens to the My Dashboard page of the Microsoft Entra admin center. From the dashboard’s main windows, you will see several tiles, including the Organization’s Identity tile ( the tenant and the Azure AD edition), a tile for users and groups, and more.

1. From the left navigation pane, under favorites select **Identity**.  In the main window, you will see another navigation panel that lists all the services that are available in Azure AD. To the right, you will see information about the tenant and links to identity types you can create and featured services.  

    ![](../Images/sc900-image6.png)
 
1. Now open a new browser window and in the address bar, enter **portal.azure.com**.  Since you are already signed in as <inject key="Username" enableCopy="false" /> and you originally used those same credentials to redeem your Azure pass, you should be logged in as the admin when you access the Azure portal.  You can verify this by checking the email on the top-right corner of the page and hovering your mouse over the user icon.

    ![](../Images/SC-900-4x.png)

1. The Azure portal’s landing page shows Azure services, including Virtual Machine, storage accounts, databases, and much more.

    ![](../Images/sc900-image7.png)

1. Select More Services, then select Microsoft Entra ID. If you don't immediately see it, you can enter Microsoft Entra ID on the blue search bar and select Microsoft Entra ID from result list.

    ![](../Images/T1-S9a.png)

    ![](../Images/T1-S9b.png)

1. You are now seeing the Microsoft Entra ID for your Microsoft 365 tenant. Whichever approach you use to access Microsoft Entra ID services (the Microsoft 365 admin portal or the Azure portal) you end up in the same place – the Microsoft Entra ID where you can administer all the Azure AD services.

    ![](../Images/lab1-1.png)
   
1. Keep this browser page open for the next task.

## Task 2: Creating a basic group

1. On the Microsoft Entra ID page, from left navigation pane select **Groups** under the **Manage** section and then select **New group**.

    ![](../Images/T2-S1.png)

1. Populate the **New Group** fields as follows and Select **Create**

    1. Group type: **Microsoft 365**.

    2. Group name: **Operations**.

    3. Group email address: **Leave Default**.

    4. Group description: **Add an optional description to your group**.

        ![](../Images/sc900-image9.png)

       > **Note:** Kindly refresh the screen if the newly created group is not visible.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

 <validation step="6be841cf-5bd0-4c51-9b70-a308b628beb9" />

## Task 3: Create a new user in the Microsoft Entra ID and explore some of the services

In this task, you’ll learn how to create a new user in the Microsoft Entra ID and explore some of the services that can be managed at the user level.

1. In Microsoft Entra ID Overview page, from the left navigation select **Users** under the **Manage** section.

    ![](../Images/T3-S1.png)

1. Notice that your tenant is already configured with users. Select **+ New user** at the top of the page and select **create new user** from the drop down.

    ![](../Images/sc900-image10.png)
   
1. Populate the **Identity** fields as follows and select **Next: Properties >**.

    1. User principal name: **sara**

    1. Display Name : **Sara Perez**

    1. Uncheck **Auto-generate password**

    1. Password:  enter a temporary password that adheres to the password requirements and make note of it, as you will need it to complete the subsequent task.
    
    >**Note** : When Sara signs in for the first time, she will be prompted to change her password.

      ![](../Images/sc-900-1.1.png)

1. On the **Properties** tab under settings specify the following and select **Next: Assignments >**

   1. Usage location: **United States** (select the drop-down then scroll down to find this option). Configuring usage location is required for assigning licenses.

      ![](../Images/sc900-image(11).png)
   
1. In the **Assignments** tab :

    - Click **Add Group**,this displays the available groups.  Notice the list of available groups.

    - Select **Operations**, you may need to scroll down, then press **Select**. Notice how the text next to groups has been updated to reflect 1 group selected.  

       ![](../Images/sc900-image12.png)

1. Next to Roles, select **Add role**. The list of Directory roles appears.  Scroll down to view the various built-in roles, to view the various roles, but don’t change the user role.  Close out of this window by selecting the **X** on the top right-hand corner of the page.

      ![](../Images/sc900-image13.png)

1. From the bottom of the page, select the **Review + create** and **Create** button.

1. Navigate back to **Microsoft Entra ID** user blade and verify the user appears on the user list (names are listed in alphabetical order).Kindly refresh the screen if the newly created user is not visible.

1. From the user list select the user you just created, **Sara Perez**, the profile page opens.

      ![](../Images/sc900-image14.png)

1. The left navigation panel shows the various options that can be configured for the user.  Select **Groups**.  Here you can see additional information about the group.  Verify the Operations group is listed (it may take several minutes for the group assignment to show up).  

    ![](../Images/sc900-image15.png)
    
1. From the left navigation panel select **Licenses**.  Notice that there are no license assignments found for this user.
To add a license, click on **Go to the Microsoft 365 admin center** from the alert message.

     ![](../Images/T3-S11.png)

1. Log in to the Microsoft 365 admin center. Since you are already signed in as <inject key="Username" enableCopy="false" />, you will be automatically logged in when you access the portal.

     ![](../Images/T3-S12a.png)
    
1. From the left navigation panel, under **users (1)**, select **Active users (2)**.

     ![](../Images/T3-S13.png)

1. From the list of users, select **Sara Perez**.

     ![](../Images/T3-S14.png)

1. A window will open displaying the user's information. Select the **Licenses and apps tab (1)**. Check the box for **Office 365 E3 (no Teams) license (2)** and click **Save changes (3)**. A notification at the top of the screen will confirm that the license assignment was successful. Close the window by clicking the **X (4)** in the top-right corner.

     ![](../Images/T3-S15a.png)

1. You have successfully created and configured a user in Microsoft Entra ID.

1. Navigate back to the Microsoft Azure Portal and return to the Microsoft Entra ID Overview page. **Copy** the **email address** of the newly created user (e.g., sara@azureholxxxx.onmicrosoft.com), as you will use it to sign in for the next task.

   >**Note** : You can retrieve the email ID from the environment details page.

     ![](../Images/T3-S16.png)

1. Sign out from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

     ![](../Images/T3-S17a.png)

     ![](../Images/T3-S17b.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
     
<validation step="23fc9a6d-edce-49f8-99f4-7f3727e3124f" />

## Task 4: Sign in to the user first time

In this task, you will sign in as Sara Perez, for the first time.

1. Open Microsoft Edge.

1. In the address bar enter **[login.microsoft.com](https://login.microsoft.com)** or https://login.microsoft.com.

1. Sign in using the email address **sara@azureholxxxx.onmicrosoft.com** that you copied in step 17 of Task 3.

   ![](../Images/sc900-image18.png)

   >**Note** : You can retrieve the email ID from the environment details page.

1. Enter the temporary password that you have provided earlier.

    ![](../Images/sc900-image19.png)

1. You are now prompted to Update your password. In the Current password field, enter the temporary password that you have provided earlier.

1. In the New password field enter, **SC900-Lab**.  In the Confirm your password field enter SC900-Lab, then select Sign in.  **Note**: As a best practice, a more secure password should be used. This password is chosen, for expediency and only for the purpose of this lab.

     ![](../Images/sc900-image20.png)

1. You should now be successfully signed in to Microsoft 365.

     ![](../Images/T4-S4a.png)

1. **Sign out** from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then close all the browser windows.

## Review
In this lab, you have completed:
- Accessing  Microsoft Entra ID through the Microsoft 365 Admin portal and through the Azure portal
- Creating a basic group
- Create a new user in the Microsoft Entra ID and explore some of the services
- Sign in to the user first time

## You have successfully completed the lab

