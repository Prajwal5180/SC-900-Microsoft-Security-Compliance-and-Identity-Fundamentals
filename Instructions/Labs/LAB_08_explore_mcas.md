# Lab-08: Explore Microsoft Defender for Cloud Apps

## Lab scenario
In this lab, you will explore the capabilities of Microsoft Cloud App.  You will walk through the information available on the Cloud Discovery dashboard as well as capabilities available to investigate findings and control impact to your organization through policies.  Note:  An organization must have a license to use Microsoft Cloud App which is a user-based subscription service. 

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: Explore Cloud Discovery
+ Task 2: Explore the Cloud app catalog
+ Task 3: Explore the Activity log and Files
+ Task 4: In this task you will explore the policies and alerts pages in Microsoft Cloud app security

## Estimated timing: 30 minutes

## Architecture diagram

![](../Images/sc900lab8.png)

## Task 1: Explore Cloud Discovery

1.	Open Microsoft Edge. In the address bar enter **https://portal.cloudappsecurity.com**.

1. In the Sign in window enter following email  then select **Next**.

   * **Email** : **<inject key="AzureAdUserEmail"></inject>**
     
1. Enter the admin following password and select **Sign in**.

   * **Password** : **<inject key="AzureAdUserPassword"></inject>** 

1. From the left navigation menu, under **System**, select **Settings**.

     ![Picture 1](../Images/Asc-900-image15.png)

1. On the **Settings** page, select **Cloud apps**.

     ![Picture 1](../Images/Asc-900-image16.png)
   
1. On the **Cloud apps** page, Under **Cloud Discovery**, select **Snapshot Reports (2)**, and click **+ Create Snapshot Report (3)**.

    ![Picture 1](../Images/Asc-900-image17.png)
 
1. Under **Overview** tab, click **Next >**.

     ![Picture 1](../Images/Asc-900-image18.png)

1. Under **Report Details** tab, Enter a **Report name** and a **Description**. Select the **source** from which you want to upload the log files. Click **View log format** then **Download sample log** and click on **Next**.
 
   ![Picture 1](../Images/Asc-900-image19.png)
 
1. Under **Upload Traffic Logs** Tab, In **Choose traffic logs** browse and upload the log file which you downloaded. Click **Upload logs >**.

      ![Picture 1](../Images/Asc-900-image20.png)

1. After the upload completes, click on **snapshot reports** link on **Create new Cloud Discovery snapshot report** page.

      ![Picture 1](../Images/Asc-900-image20.png)
   
1. After you upload your log files, it will take some minutes for them to be parsed and analyzed.

1. Click on **Proccessing**, if you encounter error **All discovered cloud related transactions are more than 90 days** following the below subpoints else proceed with next step.
    
    - Open the file which you downloaded with notepade notice the data.
    - Here we need to changes the month date which should be within 90 days period make the changes accordindly.
    - Make sure you changes the month date whch should be within 90 days. And save the file.
    - On the **Cloud apps** page, Under **Cloud Discovery**, select **Snapshot Reports (2)**, and click **+ Create Snapshot Report (3)**.
    - Under **Report Details** tab, Enter a **Report name** and a **Description**.
    - Under **Upload Traffic Logs** Tab, In **Choose traffic logs** browse and upload the log file which you modified. Click **Upload logs >**.
    - After the upload completes, click on **snapshot reports** link on **Create new Cloud Discovery snapshot report** page.
    - Click on **Progressing** and this time you should not encounter with the error **All discovered cloud related transactions are more than 90 days**

1. After you upload your log files, it will take some minutes for them to be parsed and analyzed.

1. Wait till the status of your log files turns **Ready**.

    ![Picture 1](../Images/Asc-900-image29.png)
    
1. Open a new tab  enter **admin.microsoft.com**

1. Sign in with your admin credentials.
    
    - Email/Username: <inject key="AzureAdUserEmail"></inject>  then select **Next**.
    
    - Password: <inject key="AzureAdUserPassword"></inject>
    
1. When prompted to stay signed-in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

    ![Picture 1](../Images/secu.png)
    
1. If this is the first time you visit the Microsoft 365 Defender portal, you may get a pop-up window to take a quick tour.  Close this.

1. From the left navigation panel, select **Cloud apps** to expand the list then select **Cloud Discovery**. This takes you to the Dashboard view.  Note the information available on the dashboard. From the dashboard view, you can select different tabs from the top of the page.  

    ![Picture 1](../Images/dis.png)

1. In the Cloud Discovery page, select the **Discovered apps (1)** tab.  The discovered apps window provides a more detailed view of the discovered apps, including risk score, traffic, number of users and more.

1. From any item on the list, select the ellipses **(⋮) (2)** in the actions’ column of the table.  Note the various options available, including the ability to tag an app as sanctioned or unsanctioned.  Select the ellipses, again, to close the actions box.

    ![Picture 1](../Images/disapp.png)

1. Selecting a specific line item opens a details page for the specific app. Select an item from the list and review the information available on the overview page.  For the selected item,

1. Select the **IP Addresses**, **Users**, and **Discovered resources** tab to see more detailed information.

1. When you're done exploring the details page, return to discovered apps page, by selecting **Cloud Discovery** from the bread crumb on the top of the page.

1. If you select Cloud discovery from the left navigation panel, it will take you back to the dashboard view.
 
1. From the top of the page, select the **IP addresses** tab (this is equivalent to selecting IP addresses from the left navigation pane).

   >**Note:** Here you will find data including number of transactions, amount of traffic and upload amounts, by IP addresses.  Note that you can also filter by specific IP 
   address or    export the data for further analysis.

   ![Picture 1](../Images/ipadd.png)
  
1. From the top of the page (or the left navigation pane) select **Users**.

   >**Note:** This is the same type of information provided when you select IP addresses, but instead it is listed for individual users.  Here again, you filter by specific 
    user and export data for further analysis.
 
1. Click on view all discovered app to view the detailed information.

1. The information provided in these tabs is based on either snap-shot reports from traffic logs you manually upload from your firewalls and proxies or from continuous reports that analyze all logs that are forwarded from your network using Cloud App Security.
   
1. You can connect to apps directly by setting up app connectors that will provide you with greater visibility and control over your cloud apps. From the top right corner of the screen, select **Actions** then select **Cloud Discovery Settings**.

    ![Picture 1](../Images/Asc-900-image23.png)
    
1. From the left side of the screen, under **Connected apps**, select **App connectors**. Now you'll set up a new app connector.  Select **+ Connect an app** and from 
   the drop-down list select **Microsoft 365**.

   ![Picture 1](../Images/Asc-900-image24.png)
   
1. From the Microsoft Azure pop-up window, select **Connect Office 365** then select **Done**.

    ![Picture 1](../Images/Asc-900-image25.png)

    ![Picture 1](../Images/Asc-900-image26.png)

1. You'll see a connected status (if you don't see it, refresh the browser) and information on scanning users, data, and activities.  Return to the Cloud Discovery dashboard, by selecting **Cloud Discovery** from the left navigation panel.
    
1. Now you'll set up a another new app connector.  From the left side of the screen, under **Connected apps**, select **App connectors**.Select **+ Connect an app** and 
   from the drop-down list select **Microsoft Azure**.

    ![Picture 1](../Images/Asc-900-image27.png)
   
1. From the Microsoft Azure pop-up window, select **Connect Microsoft Azure** then select **Done**.  You'll see a connected status (if you don't see it, refresh the browser) and information on scanning users, data, and activities.
  
1. Back on **App Connectors** review the status for both **Microsoft 365** and **Microsoft Azure**.
    
    ![Picture 1](../Images/Asc-900-image28.png)

## Task 2: Explore the Cloud app catalog

Cloud Discovery analyzes your traffic logs against the Microsoft Defender for Cloud Apps cloud app catalog of over 31,000 cloud apps. The apps are ranked and scored based on more than 80 risk factors to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses to your organization.  In this task, you'll explore the capabilities of the Cloud app catalog.

1. From the left navigation panel, select **Cloud app catalog**.

    ![Picture 1](../Images/appcatalog.png)

    >**Note**: The Cloud app catalog enables you to choose apps that fit your organization's security requirements. Admins can do basic filtering of apps as shown on the top of the page, which includes whether the app is sanctioned, unsanctioned, or has no tag, risk score, Compliance risk factor, and security risk factor.  For example, filtering by compliance risk factor lets you search for a specific standards, certification, and compliance that the app may comply with. Examples include HIPAA, ISO 27001, SOC 2, and PCI-DSS.

1. Select **Compliance risk factor** to view the available options.  You can further filter by risk score, by moving the sliders on the risk score on the top of the page. If you moved the slide, be sure to set it so the range is set at 0 to 10.

1. Admins can also search for apps by category.  For example, in the Apps search bar field enter **Microsoft Viva Engage**, then select **Social network**.  Select **Microsoft Viva Engage** for a detailed view.  Hovering your mouse over any topics for a given category will show an information icon that you can select to get more information about that topic.

## Task 3: Explore the Activity log and Files

1. From the left navigation pane, select and explore the **Files** option and note the options to filter data by app, owner, access level, file type, and matched policy. Also, note the option to create a new policy from search and export of the data.

   ![Picture 1](../Images/select-file.png)

1. Click on **Enable file monitoring**, this will navigate you to file window.

   ![Picture 1](../Images/file-1.png)

1. On the Files page, if it says For Defender for Cloud Apps to monitor files in your SaaS apps, select checkbox next to **Enable file monitoring (1)**, for enabling file monitoring, and click on **Save (2)**.

   ![Picture 1](../Images/file-2.png)

1. Select **+ New policy from search**.

   >**Note**: how you can create a policy based on a template, select a policy severity & category, create filters for the policy, create alerts, and even send the alerts to Power Automate.

   ![Picture 1](../Images/filesad.png)

1. Select **Cancel** to exit of the policy creation window, then select **Leave page**.

1. From the left navigation panel, select **Activity Log**, under **Cloud apps**. Here you get visibility into all the activities from your connected apps.
   
   ![Picture 1](../Images/file-3.png)

1. You may not see any data listed as it can take several hours to perform retroactive scans once audit is enabled and lab tenants may experience longer than normal delays. Note the available filter options and the option to create new a policy from search.

## Task 4: In this task you will explore the policies and alerts pages in Microsoft Cloud app security

1. From the left navigation panel, select **Policies (1)** under **Cloud apps**, then select **Policy management (2)**.  The listed policies provide information on the number of alerts generated by the policy, severity, etc.

1. Selecting any line item provides more detailed information about the policy. Select an item from the list, i.e. **Risky sign-in**. 

    >**Note**: that you can also create a policy. Select **+ Create policy (3)** to view the types of policies you can create.  Select **Activity policy** to view the different options available for creating the policy.  Select **Cancel** to exit out of the configuration window.
 
     ![Picture 1](../Images/sc900-managepolicy.png)
     
     ![Picture 1](../Images/sc900-activitylog.png)
     
    >**Note**: that you can also have the option to export policy information.

1. From the left navigation panel, select **Policy templates (1)**. To create a policy from one the available templates, select the **+ (2)** on the left side of the template line item.  View the different configuration options for the policy.  Select **Cancel** to exit out of the page.

   ![Picture 1](../Images/policy-template.png)

1. Close the browser window.

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   
   - Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
   - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

## Review
In this lab, you have completed:
- Explore Cloud Discovery
- Explore the Cloud app catalog
- Explore the Activity log and Files
- In this task you will explore the policies and alerts pages in Microsoft Cloud app security

## You have successfully completed the lab
