
# Lab-05: Explore Azure Network Security Groups (NSGs)

## Lab scenario
In this lab, you will explore the function of network security groups in Azure.  You will do this by create the VM without any network security group (NSG).  Without any NSG to filter traffic, all the ports in the VM are exposed to the public internet.  You will then go through the process of creating an NSG and assigning the VM's interface to that NSG.  Once configured you will test the connection to the VM, using the default NSG rules and also rules that you will create.

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: In this task you will create a Windows 10 virtual machine
+ Task 2: Create a network security group and assign the network interface of the VM to that NSG and create a new inbound rule for RDP traffic
+ Task 3: Test the newly created inbound NSG rule to confirm that you can establish a remote desktop (RDP) connection to the VM
+ Task 4: Allow outbound internet traffic to validate that you can connect to the internet

## Estimated timing: 60 minutes
 
## Architecture diagram

![](../Images/sc900lab5.png)
  
## Task 1:  In this task you will create a Windows 10 virtual machine

In this task, you’ll create a Windows 10 virtual machine to set up an isolated environment for testing and development purposes.

1. On Azure Portal page, in **Search resources, services and docs (G+/)** box at the top of the portal, enter **Virtual Machines**, and then select **Virtual Machines** under services. Virtual Machines.

     ![Picture 1](../Images/sc900-lab5-1.png)

1. From the top left of the page, select **+ Create** then select **Azure Virtual machine**.

     ![Picture 1](../Images/sc900-5-1.png)

1. From the basics tab, fill in the following information (for anything not listed, leave the default settings):

   | Setting | Action |
   | -- | -- |
   | **Subscription** |  Leave the default value (this is the Azure subscription provided by the authorized lab hoster) |
   | **Resource group** |  select the existing resourcegroup **LabsSC900-<inject key="DeploymentID" enableCopy="false"/>**. |
   | **Virtual machines name** |  enter **SC900-WinVM**. |
   | **Region** |  Leave the default region. |
   | **Availability Options** | Select **No infrastructure redundancy required** from the drop-down. |
   | **Security type** |  Select **Standard** from the drop-down.
   | **Image** |  from the drop-down, select **Windows 10 Pro, Version 22H2 – x64 Gen 2**. |
   | **Size** |  select **see all sizes** from the drop-down and select **B2s**, then press **Select** on the bottom of the page. |
   | **Username** |  enter **AzureUser**. |
   | **Password** |  enter **SC900AzureLabs**. |
   | **Public inbounds ports** |  select **None**. |
   | **Licensing** |  select **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights**, so that a checkmark appears in the box. |
   | **Select** | **Next: Disks**. | 
        
1. You are now in the **Disks** tab for the VM configuration, change the OS disk type to **Standard SSD** and Leave all other settings to the default .

    ![Picture 1](../Images/sc900-lab5-2.png)
      
1. Switch to the **Networking** tab, and configure the following setting:

    | Settings | Values |
    | -- | -- |
    | NIC network security group | **None**|

      ![Picture 1](../Images/sc900-5-11.png)

1. Leave the remaining defaults and then click the **Review + create** button at the bottom of the page.

1. Once Validation is passed click the **Create** button. It can take about five minutes to deploy the virtual machine.

1. Monitor the deployment. It may take a few minutes for the resource group and virtual machine to be created. 

1. From the deployment blade or from the Notification area, click **Go to resource**. 

   >**Note**: This VM has a public IP address and no NIC network security group.  From a security perspective this leaves the VM exposed.  We will address this in a subsequent task. Select Create.  It may take several minutes for the VM deployment to complete.

1. Note the name of the network interface, **sc900-winvmxxx** (the XXX will be specific to the network interface of your VM).

1. Once the VM deployment is complete, select **Go to resource**.
   
    ![Picture 1](../Images/4.png)

1. You are now in the SC900-WinVM page.  Note the public IP address. 

1. From the top of the page, select **Connect** > **Connect** then under **Navtive RDP** select **Download RDP file**. 

1. Open the downloaded file and select **Connect**. 

   > **Note:** The port prerequisite is not met.  In order to satisfy the prerequisite, an inbound network security rule with the destination port 3389, used by RDP, must be configured.  You'll do that in the next task, when you create a network security group.

   ![Picture 1](../Images/08.png)
   
1. On **sc900-winvmxxx** virtual machine blade, navigate to **Networking**, select **Network Settings**, scroll down, and click on **Add Network Security Group**. Next, click on **Create Port Rule** and select the **Inbound Port Rule** tab from the dropdown menu. Please note that there is currently no network security group associated with the virtual machine's network interface or the subnet linked to it.

   ![Picture 1](../Images/add_network.png)
    
   - The default view is for inbound port rules.  Note that the network interface for this VM has no network security groups configured.  The same is true if you select 
     Outbound port rules.
   - Select **Effective security rules 0** link.  Note that it says, "No network security groups or applications security groups are associated with the network interface".

> - **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="24fbcf68-d975-439f-9d37-7e35ffd329f4" />

## Task 2:  Create a network security group and assign the network interface of the VM to that NSG and create a new inbound rule for RDP traffic

In this task, you’ll create a network security group, assign it to the VM’s network interface, and set up a new inbound rule to allow RDP traffic.

1. On Azure Portal page, in **Search resources, services and docs (G+/)** box at the top of the portal, enter **Network security groups**, and then select **Network security groups** under services (do not select Network security groups classic).

1. From the top of Network security groups page, select **+ Create**.

1. On the Basics tab of the Create network security group page, specify the following settings:

   | Setting | Action |
   | -- | -- |
   | **Subscription** | Leave the default value (this is the Azure subscription provided by the authorized lab hoster) |
   | **Resource group** | Select **LabsSC900-<inject key="DeploymentID" enableCopy="false"/>** |
   | **Name** |  **NSG-SC900** |
   | **Region** |  leave the default value |
   | **Select** | **Review + create** then select **Create**. |
    
1. Once the deployment is complete, select **Go to resource**.

1. On the top of the page underneath where it says Essentials, you'll see some basic information about the NSG you created.  Two points to note are that there are no Custom Security rules and there are no subnets nor network interfaces associated with this NSG.  Although there are no custom security rules, there are default inbound and outbound rules that are included with every NSG, as shown on the page.  Review both the inbound and outbound rules. The default inbound rules deny all inbound traffic that is not from a virtual network or an Azure load balancer.  The outbound rules deny all outbound traffic except traffic between virtual networks and outbound traffic to the internet.

1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.

1. Select the **Associate (1)**, and choose for the **sc900-winvmxxx** from the drop down.

   ![](../Images/associate-1.png)

   >**Note**: **If the option is disabled in the dropdown for network interface associations, follow below steps:**
     - Go to the **sc900-winvmxxx** network interface, select **Network Security Group (1)** under settings. You will see the currently selected NSG; click on it, choose **None (2)** from the dropdown, and Click on **save (3)** .

       ![](../Images/sc-900.png)
   
     - Then, proceed to complete steps 6 and 7.     

1. In the associate network interface page, select **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM). then select **ok** on the bottom of the window. As the interface is being associated you will see a notification box in the top right corner of the screen.

1. Once the interface is associated to the NSG, it will show up on the list.

1. Navigate to SC900-WinVM Overview page, under **Networking**  select **Network settings** from the left navigation pane and then **Inbound port rule** from the **+ Create port rule** drop down.

    ![Picture 1](../Images/L5T2S10.png)

1. The default inbound rules deny all inbound traffic that is not from a virtual network or an Azure load balancer so you need to set up a rule to allow inbound RDP 
    traffic (traffic on port 3389). Recall that you cannot remove the default rules, but you can override them by creating rules with higher priorities.

1. From the left navigation pane under **settings** select Inbound security rules and specify the following settings:
    
    | Setting | Action |
    | -- | -- |
    | **Source** |  **Any** |
    | Source port ranges | **\*** |
    | Destination |  **Any** |
    | Service |  **RDP** |
    | Action |  **Allow** |
    | Priority |  **1000**. Note: rules with lower numbers have higher priority and are processed first. |
    | Name |  Leave the default name or create your own descriptive name. |
    | Select **Add** |
    
    > **Note:** the warning sign at the bottom of the page. We're using RDP only for testing purposes and to demonstrate the functionality of the NSG.
  
    > **Note:** Once the rule is provisioned, it will appear on the list of inbound rules (you may need to refresh the screen). On the newly added rule, you'll see a 
      warning sign.  As stated above, we're using RDP to only for testing purposes and to demonstrate the functionality of the NSG. Select the newly added rule.

> - **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="8ecbe441-8eed-4208-8da0-bbd3c55a6f26" />

## Task 3: Test the newly created inbound NSG rule to confirm that you can establish a remote desktop (RDP) connection to the VM

In this task, you'll test the newly created inbound NSG rule to confirm that you can establish a remote desktop (RDP) connection to the VM.  Once inside the VM you'll work check outbound connectivity to the internet from the VM. 

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.If you previously closed the browser tab,

1. select the blue search bar on the top of the page and select Virtual machines, then select the VM, **SC900-WinVM**.

1.  From the top of the page, select **Connect** > **Connect** then select **Download RDP file**.

1. A Remote Desktop Connection window opens, select **Connect**.

1. You will be prompted for your credentials.  For Username, enter **AzureUser**.  For the Password, enter **SC900AzureLabs**.

   >**Note**: If you encounter **The logon attempt failed** click on **More choices** > **Use a different account** provide username:  **.\AzureUser** and password : **SC900AzureLabs**

1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified.  Do you wish to connect anyway?  Select **Yes**.

1. You are now connected to the VM. In this case you were able to connect to the VM because the inbound traffic rule you created allows inbound traffic to the VM via RDP.

1. After a few seconds on the Welcome screen you'll see a window to Choose privacy settings for your device, select **Accept**.  On the Networks window, select **No**.

1. With the VM up and running, test outbound connectivity to the internet from the VM.
    
    - From the VM, select **Microsoft Edge** to open the browser.  Since this is the first time you open Microsoft Edge, you may get a pop-up window, select **Start       
    without your data**, then select **Continue without this data**, then select **Confirm and start browsing**.
    - Enter **www.bing.com** in the browser address bar and confirm you're able to connect to the search engine.
    - Once you've confirmed that you can access www.bing.com, close the browser window in the VM, but leave the VM up.

1. Minimize the VM, by selecting the underscore **_** in the blue tab that shows the VM's IP address. This brings you back to the SC900-WinVM | Connect page. 

1. From the left navigation panel, select **Networking**.

1. Keep the browser tab open you'll use it the next task.

## Task 4: Allow outbound internet traffic to validate that you can connect to the internet

In this task, you’ll configure outbound internet traffic for the VM to ensure it can successfully connect to the internet for validation.

1. You should be on the SC900-WinVM | Networking page. If you previously closed the browser tab, select the blue search bar on the top of the page and select Virtual machines, then select the VM, **SC900-WinVM**, then select **Network settings**.

1. Select the **Outbound port rules** tab.  You'll see the default outbound rules.

   > **Note** the default rule "AllowInternetOutBound". This rule allows all outbound internet traffic. You cannot remove the default rule, but you can override it by 
      creating a rule with higher priority. From the right side of the page,

1. Select **Outbound port rule** from the **+ Create port rule** drop down

   ![Picture 1](../Images/L5T4S3.png)

1. On the Add outbound security rule page, specify the following settings:

    | Setting | Action |
    | -- | -- |
    | Source |  **Any** |
    | Source port ranges |  **\*** |
    | Destination |  **Service Tag** |
    | Destination service tag |  **Internet** |
    | Service |  **Custom** (leave the default) |
    | Destination port ranges |  * (be sure to put an asterisk in the destination port ranges field) |
    | Protocol | **Any** |
    | Action | **Deny** |
    | Priority |  **4000** |
    | Name |  **DenyInternet** |
    | Select | **Add** |
    
1. Once the rule is provisioned, it will appear on the list of outbound rules.  Although it appears on the list, it will take a few minutes to take effect (wait a few minutes before continuing with the next steps).  

1. Return to your VM (the icon for the VM should be shown on the task bar on the bottom of the page).

1. Open the Edge browser in your VM and enter **https://www.bing.com**.  The page should not display.

   > **Note:** if you are able to connect to the internet and you verified that all the parameters for the outbound rule were properly set, it is likely because it takes                   a few minutes for the rule to take effect.  Close the browser, wait a few minutes and try again. Azure subscriptions in the lab environment may experience                   longer than normal delays.   

1. Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up windows indicates Your remote session will be disconnected. Select **OK**.

1. In this task you successfully configured an outbound rule in your NSG, to block outbound internet traffic.

> - **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="ce6c9e7b-b43c-4e76-8684-24dca8019552" />

## Review
In this lab, you have completed:
- In this task you will create a Windows 10 virtual machine
- Create a network security group and assign the network interface of the VM to that NSG and create a new inbound rule for RDP traffic
- Test the newly created inbound NSG rule to confirm that you can establish a remote desktop (RDP) connection to the VM
- Allow outbound internet traffic to validate that you can connect to the internet

## You have successfully completed the lab
