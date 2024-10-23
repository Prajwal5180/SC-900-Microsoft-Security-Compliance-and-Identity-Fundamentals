# Lab-13: Explore sensitivity labels in Microsoft Purview

## Lab scenario
In this lab, you will explore the capabilities of sensitivity labels.  You will go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you will see how to apply a label and the impact of that label, from the perspective of a user.

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: Explore the capabilities of sensitivity labels
+ Task 2: How to apply a label
+ Task 3: Impact of that label

## Estimated timing: 60 minutes

## Architecture diagram

![](../Images/sc900lab13.png)

## Task 1: Explore the capabilities of sensitivity labels
In this task you will gain an understanding of what sensitivity labels can do by going through the settings for an existing sensitivity label that have been created and the corresponding policy to publish the label.

1. Open Microsoft Edge. In the address bar enter https://admin.microsoft.com. 
   
1. In the Sign-in window, enter the following **email/username** and click on **Next**.

    * Email/Username: <inject key="AzureAdUserEmail"></inject>

1. Now enter the password and click on **Sign in**.
   
   * Password: <inject key="AzureAdUserPassword"></inject>
  
1. When prompted to stay signed-in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

    ![](../Images/L13-T1-S5.png)

1. Under **Admin centers (1)**, select **Compliance (2)**.

    ![](../Images/L13-T1-S6.png)

1. A new browser page opens.Since you are already signed in, your email will be listed. You can select your email address, to log in to Microsoft Purview.
    
    ![](../Images/L13-T1-S7.png)

1.Upon logging in to the portal, a pop-up window will appear. Choose **Go to classic portal** in the pop-up.

    ![](../Images/L13-T1-S8.png)
   
1. Now, click on **Switch** next to the **Microsoft 365 compliance portal** option to return to the classic portal.

    ![](../Images/L13-T1-S9.png)

1. You are now located on the homepage of the classic Microsoft Purview portal.

    ![](../Images/L13-T1-S10.png)

1. In the left navigation panel of Microsoft Purview, go to **Solutions (1)**, select **Information Protection (2)**, and then choose **Overview (3)**. On the overview page, click **Turn on now (4)** inside the yellow information box to enable processing of encrypted sensitivity labels in Office online files stored in OneDrive and SharePoint.
   > **Note**: There can be a delay for the setting to propagate through the system. Refresh the Page once.

    ![](../Images/L13-T1-S11.png)

1. Now select **Labels** from the left navigation panel and then select **Create a label**

    ![](../Images/L13-T1-S12.png)

1. On the new label configuration page, enter the details provided below and click **Next (4)**.

    | Setting | Values |
    | -- | -- |
    | **Name** | **Confidential-Finance (1)** |
    | **Display name** | **Confidential-Finance (2)** |
    | **Description for users** | **Confidential-Finance Demo (3)** | 

    ![](../Images/L13-T1-S13.png)

1. Note the scope for this label is set to **Items**. Read the description but **do not** change any settings. Select **Next** at the bottom of the page.

      ![](../Images/sc-900-jap8.png)

1. On the Choose protection settings for labeled items page, select **Apply or remove encryption (1)*** and **Apply content marking (2)** options, then click **Next (3)**.

    ![](../Images/L13-T1-S15.png)

1. Under **Access Control (1)** section, scroll down and click on **Assign Permissions**.

    ![](../Images/L13-T1-S16.png)
    
1. Click on **+Add Users or Groups** in the **Assign Permissions** page that shows up. 

    ![](../Images/L13-T1-S17.png)

1. select your username **odl_user_<inject key="deploymentID"></inject>** and **Megan Bowen** and click on **Add**.

    ![](../Images/L13-T1-S18.png)

1. On the Assign permissions page, check the users you selected in the previous step. These users can interact with the content that has this label applied. Then, click **Save**.

    ![](../Images/L13-T1-S19.png)

1. Under Users and groups, the tenant is defined, allowing all users in your tenant to view content with this label. The finance team is also listed and has co-author permissions. Do not change any settings. Select **Next** on the bottom of the page.

    ![](../Images/L13-T1-S20.png)


1. On the content markings page, take note of the information box on the top of the page. **Turn on (1)** the Content Making and select **Add a watermark (2)**, **Add a header (3)**, & **Add a footer (4)**. Click on **Customize text (5),(6),(7)** on each and provide the text **customize watermark test** and click on **Save**.  Content markings will be applied to the documents but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails. The content marking associated with this label is a watermark. Select **Next (8)** on the bottom of the page.

    ![](../Images/L13-T1-S21.png)

    ![](../Images/L13-T1-S21b.png)

1. You are now in the Auto-labeling for files and emails window. Turn on the **Auto-labeling for files and emails (1)** and read the description of auto-labeling on the top of the page and the information box below it. Select **Next (2)** on the bottom of the page.

    ![](../Images/L13-T1-S22.png)

1. This next window defines protection settings for groups, and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.

    ![](../Images/L13-T1-S23.png)

1. This next window is a preview feature to automatically apply this label to Azure database columns (such as SQL, Synapse, and more) that contain the sensitive info types you choose. This features is not enabled. Select **Next** on the bottom of the page.

      ![](../Images/sc-900-jap19.png)
       
      
1.  Review the settings and click on **Create label**.

      ![](../Images/L13-T1-S25.png)
      
1. Click on **Done** on next window.   

      ![](../Images/sc-900-jap21.png)
          
1. A new window of Create policy will open. Select **Choose sensitivity labels to publish**. A window opens that provides information about the policy. This policy serves to publish the IT-Department-Demo. Select **Confidential-Finance** from label and select **Add** on the bottom of the page. And then click on **Next**.

     ![](../Images/sc-900-jap22.png)
     
1. Under the Sensitivity labels to publish.  Don’t change any settings.  Select **Next** on the bottom of the page.

     ![](../Images/sc-900-jap23.png)
     
1. Click on **Next** on Assign Admin Units(Preview). 

     ![](../Images/sc-900-jap24.png)   

1. Read the description under **Publish to users and groups**.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.

    ![](../Images/sc-900-jap25.png)

1. Under the policy settings.  Don’t change any settings.  Select **Next** on the bottom of the page.

    ![](../Images/sc-900-jap26.png)

1. Under the **Apply a Default label to documents**.  Don’t change any settings.  Select **Next** on the bottom of the page.

    ![](../Images/sc-900-jap27.png)

1. Under the **Apply a Default label to emails**.  Don’t change any settings.  Select **Next** on the bottom of the page.

    ![](../Images/sc-900-jap28.png)
    
1. Under the **Apply a default label to meetings and calendar events**.  Don’t change any settings.  Select **Next** on the bottom of the page.    

    ![](../Images/sc-900-jap29.png)
    
1. Under the **Apply a default label to Fabric and Power BI content**.  Don’t change any settings.  Select **Next** on the bottom of the page.

    ![](../Images/sc-900-jap30.png)
    
1. The last configuration option is to name your policy. Enter the policy name as **Confidential-Finance Policy**.  Select **Next** on the bottom of the page to exit the policy configuration and return to the Information protection page.

    ![](../Images/sc-900-jap31.png)
    
1. Review the settings and click on **Submit** and then select **Done**.

    ![](../Images/sc-900-jap32.png)
    
    ![](../Images/sc-900-lab13-27.png)    
    
    >**Note**- The label created cannot be deleted, it can only be edited. 

1. From the left navigation panel, select Home to return to the Microsoft Purview.

    ![](../Images/L13-T1-S38.png)   

1. Keep this page open, you will use it in the next task.

1. It can take up to 24 hours to publish the labels to the selected users apps

## Task 2: How to apply a label
In this task, you will go through the process of applying a label from the perspective of the user (in this case the user is the admin) and view the content marking that is generated by the label.

1. From the Microsoft Purview home page, select the **app launcher icon**, and **right click on the Word icon** and select **Open in new tab**. 

   ![](/Instructions/Images/L13-T2-S1.png) 

1. Select **+ New blank document**, then enter some text on the page.  On the blue bar on the top of the page, select the down-arrow, next to where it says DocumentXX - Saved, and in the File Name box enter, **Test-label**.

   ![](/Instructions/Images/L13-T2-S2.png) 

1. From the top menu bar, select **Sensitivity**. From the drop down select **Confidential-Finance** (**Note:** If the option is not available, it will take sometime to reflect, and if selecting the label shows error label cannot be added to Word on web, please try refreshing the page once or sign-out and sign-in again).

   ![](/Instructions/Images/L13-T2-S3.png)     

1. From the top menu bar, select **View**, then select **Reading view**.

    ![](/Instructions/Images/L13-T2-S4.png)            

1. Notice how the document includes the watermark. 

    ![](/Instructions/Images/L13-T2-S5.png) 

1. Close the Microsoft Word tabs that are open on your browser to exit from Word.

## Task 3 (optional): Impact of that label
In addition to content marking, the label protection setting was set for encryption. Per the permissions that were configured with this label, members of the finance group can co-author documents with this label applied and users in the Contoso tenant can view (or any document/email with the label applied).  In this task you will send this document to an email address to which you have access (ie., a personal email address) and that is NOT part of the .OnMicrosoft.com domain and see what happens when you try to open the attachment.  

1. From the Microsoft Purview home page, select the **app launcher icon**, and **right click on the Outlook icon** and select **Open in new tab**.

   ![](/Instructions/Images/L13-T3-S1.png) 

1. Select **New message** from the top left corner of the screen.  Enter an email address to which you have access and is not part of the .OnMicrosoft.com domain and enter **Test** in the subject line.

   ![](/Instructions/Images/L13-T3-S2.png) 

1. Select **Attach** and you will find the word document you recently created to which you applied the label **Test-label**. Select **Share link** and press **Send**.

   ![](/Instructions/Images/L13-T3-S4.png) 

1. Check the email to which you sent the document.  Note, the email may be directed to your junk folder.  When you attempt to open the attached word file you will see a notification that you do not have permission to open the document.

1. Close the open browser tabs.
   
## Review
In this lab, you have completed:
- Explore the capabilities of sensitivity labels
- How to apply a label
- Impact of that label

## You have successfully completed the lab

