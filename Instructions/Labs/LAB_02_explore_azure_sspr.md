
# Lab-02: Microsoft Entra self-service password reset

## Lab scenario

In this lab, you, as an admin, will walk through the process of enabling self-service password reset. With SSPR enabled, you will then assume the role of a user and go through the process of registering for SSPR and also resetting your password.  Lastly, you as the admin will be able to view audit logs and usage data & insights for SSPR.

## Objectives

In this lab, you will complete the following tasks:

+ Task 1: Creating a basic group
+ Task 2: Configure Password reset for users
+ Task 3: Registration process for a self-service password reset
+ Task 4: Process of resetting your password
+ Task 5: View the Audit logs and the Usage & insights data associated with password reset.

## Estimated timing: 15-20 minutes

## Architecture diagram

![](../Images/sc900lab2-1.png)

## Task 1:  Creating a basic group

In this task, you, as the admin, will add user, Adele Vance, into the SSPRSecurityUsers group.  Also, you will be resetting the user’s password so that you can do the first-time login, as the user, and register for SSPR.

1. In the Azure portal, in the **Search resources, services, and docs (G+/)** text box at the top of the Azure portal page,  type **Microsoft Entra ID** and press the **Enter** key.

   ![](../Images/lab08-sc300-3.png)

1. On the **Microsoft Entra ID** page, from the left navigation menu, select **Groups (2)** under **Manage (1)**.

   ![](../Images/select-groups.png)
   
1. From the **Groups** page select **New group**.

   ![](../Images/sc-5.png)
   
1. Populate the **New Group** fields as follows and Select **Create (4)**

   - Group type: **Security (1)**.

   - Group name: **SSPRSecurityGroupUsers (2)**.

   - Group description: **Add an optional description to your group (3)**.
       
     ![](../Images/new-group-field.png)

1. Navigate back to the **Microsoft Entra ID** home page, from the left navigation menu, select **Password reset** under **Manage**.

   ![](../Images/sc-4.png)

1. On the **Password reset | Properties** page, under **Self service password reset enabled**, choose **Selected (1)** option and then select your Microsoft Entra ID group,by clicking on the **No group selected (2)**.

   ![](../Images/sc-6.png)
   
1. Select **SSPRSecurityGroupUsers (1)** group, after that choose **Select (2)**.

   ![](../Images/password-reset-properties1.png)

1. Once your Microsoft Entra ID group is selected, make sure that it appears under **Select group (1)** and then click on **Save (2)**.

   ![](../Images/sc-7.png)

1. Close the Properties window of Password reset by selecting the X at the top right corner of the page.
   
1. In Microsoft Entra ID Overview page, click on the **Groups (2)** blade under the **Manage (1)** section.

   ![](../Images/select-groups.png)
  
1. Navigate to **All groups** from the left Navigation pane. In the Search groups field, select **SSPRSecurityGroupUsers**.  It will take you to the configuration option for this group.

   ![](../Images/select-created-group.png)
 
1. From the left navigation pane, select **Members (2)** under **Manage (1)** section.

   ![](../Images/choose-members.png)

1. From the top of the page, select **+ Add members**.

   ![](../Images/choose-members1.png) 

1. In the Search box, enter **Adele (1)**.  Once the user, **Adele Vance (2)**, appears below the search box, select the check box next to it then press **Select (3)** from the bottom of the page.

   ![](../Images/choose-members2.png)
   
1. Close out of the SSPRSecurityUsers window, selecting the **X** on the top right corner of the screen,

1. Return to the **Microsoft Entra ID** page.

1. From the left navigation panel select **Users (2)** under **Manage (1)**.

   ![](../Images/select-users.png)
   
1. Select **Adele Vance** from the list of users.

   ![](../Images/select-users1.png)

1. Select **Reset password (1)** from the top of the page. Since you have not previously signed in as **Adele Vance**, you will need to reset the password

1. When the Reset password window opens, select **Reset Password (2)**.  

   ![](../Images/Passwordreset1.png)

   >**IMPORTANT**: Make a note of the new **password**, as you will need it in a subsequent task, to be able to sign in as the user.

   ![](../Images/sc-8.png)
   
1. Close the password reset window by selecting the **X** at the top right corner of the page.

1. Close the Adele Vance window by selecting the **X** at the top right corner of the page.

1. Close the Users window by selecting the **X** at the top right corner of the page.

1. Keep the **Microsoft Entra ID** Overview window open as you will use it in the subsequent task.

## Task 2: Configure Password reset for users

In this task, you, as the admin, will learn how to configure Password reset for users, including the configuration of the types of authentication methods to use.

1. Go to the **Microsoft Entra ID** home page.

1. From the left navigation pane, select **Password reset**.

   ![](../Images/select-password-reset.png)

1. The properties for self-service password reset are displayed.  Ensure that **Self-service reset** is **selected** for the group, which is listed, the **SSPRSecurityUsers**.  Put your cursor over the information icon next to where it says **Select group** and note what it says, **Defines the group of users who are allowed to reset their own passwords**. You must include users in the group, you can’t individually select users.  Also, if you change the group, then the group you select replaces the group currently listed.  As such, it is recommended that you simply add users to the SSPR group.  Lastly, note the blue information box, **These settings only apply to end users in your organization. Admins are always enabled for self-service password reset and are required to use two authentication methods to reset their password**.

   ![](../Images/sc-9.png)

1. From the left navigation panel of Password reset, select **Authentication Methods (1)**.

   - In the *Number of methods required to reset*, select **1 (2)**. Note the information box on the screen.

   - Notice the different methods available to users.  **Email** and **Mobile phone (3)** should already be checked; if not, select them and click on **Save** if any changes have been made.

     ![](../Images/sc-10.png)

1. From the left navigation panel of Password reset, select **Registration (1)**.  

   - Ensure the setting to *Require users to register when signing in* is set to **Yes (2)**.  Leave the *Number of days before users are asked to re-confirm their authentication information*, to the default of **180 (3)** and click save if any changes have been made.  Take note of the information box on the page.

     ![](../Images/password-reset-registration.png)

1. From the left navigation panel of Password reset, select **Notifications (1)**.  

   - Ensure the setting to *Notify users on password resets* is set to **Yes (2)**.  Leave the setting for *Notify all admins when other admins reset their password* to **No (3)**.

     ![](../Images/password-reset-notification.png)

1. Note how the Password reset navigation pane also includes options to view **Audit logs** and **Usage & insights** under Activity.

   ![](../Images/password-reset-auditlog-usage.png)    

1. **Sign out (2)** from all the browser tabs by clicking on the user icon **(1)** next to the email address on the top right corner of the screen. Then close all the browser windows.

   ![](../Images/sc-11.png)   

## Task 3: Registration process for a self-service password reset

>**Important:** Before proceeding with this task, in your Mobile phone, download the **Microsoft Authenticator App**.

In this task, you as user **Adele Vance**, will go through the registration process for a self-service password reset.  This task requires that you have access to a mobile device where you can receive text messages.
 
1. Open Microsoft Edge.

1. Go to [login.microsoftonline.com](https://login.microsoft.com) portal.

1. You will be prompted to sign-in, click on **Use another account**.

    ![](../Images/use-another-acc.png)

1. Sign in as Adele Vance,

    - In the Sign in window enter **adelev@mocholxxxxx.onmicrosoft.com** (where xxxxxx can be found in the **Environment** Tab beside the Lab Guide section) or you can also paste the **User 01 UPN** value directly, then select **Next**.
       
       ![](../Images/username-env.png)

       ![](../Images/username-enter.png)
       
    - Enter the password you noted in the earlier task. Select **Sign in**.
  
       >**Note:** If you face any issue while entering the password which states to either incorrect password. Login as <inject key="AzureAdUserEmail"></inject> to the Azure portal reset the password for the user again and note the Temporary password Follow step 19 and 20 from Task 1.

       ![](../Images/password-enter.png) 

1. Since this is your first sign-in as Adele Vance, you will be prompted to reset your password. Enter your old password in Current password field. For your new password enter **SC900-Lab** and then enter **SC900-Lab** in the confirm password field. Select **Sign in**.

    ![](../Images/UpdatePassword.png)
   
   >**Note:** We are using this password only for the convenience of the lab. As a best practice, you would typically enter a more secure password.

1. In the **Action Required** tab, choose **Ask later**. In the **Action Required** tab, choose **Ask later**. If you're prompted to stay signed in, you can select **No**.

1. A pop-up displays indicating that **More information required**. This is because as a member of the SSPRSecurityUsers group, the configuration requires its members to register when they sign in. Select the **Next** button.

    >**Note**:  An alternative to having users do the registration, themselves, is for admins to directly configure the authentication methods when they add a user. This requires admins to know and set the ​phone numbers and email addresses that users use to perform a self-service password reset and reset a user’s password.

   ![](../Images/sc-13.png) 


1. Now, Enter the phone number where you can receive a text code and select the **Next** button.

   ![](../Images/sc-900-dec24-lab2-2.png)
  
1. A new window opens indicating a code was just sent to the phone you entered **(1)**.  Enter the code you are received and select **Next (2)**.

   ![](../Images/enter-code(1).png)

1. A window opens indicating **Verification complete. Your phone has been registered**.  Select **Next**.

   ![](../Images/auth71.png)
   
1. Select **Done**, on the **Success!** page.

   ![](../Images/auth8.png)

1. You'r sign-in has been completed now. You should be on the **Office 365** landing page. If you see that your sign-in time has expired, just re-enter the password, SC900-Lab.

   ![](../Images/MS365.png)
   
1. Sign out of the Office 365 page and close your browser window.
  
    > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
    > - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
    > - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
    > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
 
    <validation step="40262c29-497d-4b45-a9cb-48830f9bb272" />

## Task 4 (Optional): Process of resetting your password

In this task, you, as user Adele Vance, will go through the process of resetting your password.

1. Open Microsoft Edge.

1. Go to [login.microsoft.com](https://login.microsoft.com) portal.

1. Sign in as **Adele Vance**, by entering your email **Adele@mocholxxxx.onmicrosoft.com** (user email id of Adel Vance) and select the **Next** button. You may, instead, see a Pick an account window open, if so, select the account for **Adele Vance**.

1. From the Enter password window, select **Forgot my password**.

   ![](../Images/forget-pass-0.png)   

1. The Get back into your account window opens. Verify that the email for **Adele Vance**, **Adele@azureholxxxx.onmicrosoft.com** **(1)**, is shown in the email or username box.  If not, enter it. In the empty box, enter the characters displayed in the image or the words from the audio **(2)**. Once you have entered them, select **Next (3)**.

   ![](../Images/forget-pass.png)

1. The screen shows Get back into your account and shows *Verification step 1 > choose a new password*. Leave the default setting **Text my mobile phone**.  *Initially your prompted to enter your phone number, enter then click on* **Text**. After that you are prompted to enter the code sent to your mobile phone number.  Once you have entered it, select the **Next** button.
   
   ![](../Images/forget-pass-1.png)

1. In the next screen you are prompted to enter the new password and confirm the new password.  Enter those now and select the **Finish** button.

   ![](../Images/forget-pass-2.png)

1. You will see a message on the screen that your password has been reset.  Select **click here** to sign in with your new password.

   ![](../Images/Forget-pass-3.png)

1. From the Pick an account information box, select **Adele@mocholxxxx.onmicrosoft.com**, enter your new password, then select the **Sign in** button. If you are prompted to Stay signed in. select **No**.

1. You should now be on the **Office 365** Page.

   ![](../Images/MS365.png)

1. Sign out by selecting the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then the close all the browser windows

## Task 5 (Optional):  View the Audit logs and the Usage & insights data associated with password reset

In this task, you, as the administrator, will briefly view the Audit logs and the Usage & insights data associated with password reset.

1. Open Microsoft Edge.

1. In the address bar enter and sign in to the Azure portal at https://portal.azure.com with the Azure credentials.

     * Email/Username: <inject key="AzureAdUserEmail"></inject>

1. Now enter the following password and click on **Sign in**.
  
     * Password: <inject key="AzureAdUserPassword"></inject>
  
1. When prompted to stay signed- in, select **Yes**. 

1. Search **Microsoft Entra ID (1)** and then select **Microsoft Entra ID (2)** from the services.

   ![](../Images/lab08-sc300-3.png)

1. From the left navigation pane, select **Password reset**.

   ![](../Images/select-password-reset.png)

1. From the left navigation pane, select **Audit logs (1)**.  Notice the information available and the available filters. 

1. Note that you can download logs. To download Select **Download (2)**, You can even format the download as CSV or JSON then click on **Download (3)** if required.

   ![](../Images/audit-download1.png)

1. Close the window by selecting the **X** on the top right corner of the screen.

1. From the left navigation pane, select **Usage & insights**.

1. Notice the information available that pertains to Registration.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the registration or usage data from the previous task.

1. From the top of the page select **Usage** to view the number of Self-service password resets and account unlocks by the method.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the usage data from the previous task.

   ![](../Images/sc-900-dec24-lab2-6.png)

1. Close the open browser tabs.

## Review
In this lab, you have completed:

- Creating a basic group
- Configure Password reset for users
- Registration process for a self-service password reset
- Process of resetting your password
- View the Audit logs and the Usage & insights data associated with password reset


## You have successfully completed the lab
