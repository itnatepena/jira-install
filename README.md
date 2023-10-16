![image](https://github.com/itnatepena/jira-install/assets/147539410/5f823690-8f88-4f77-b4f6-4a338d5b9a0d)

# Installing Jira on the Local Network

## Introduction

This project demonstrates how to set up Atlassian Jira on an Azure virtual machine (VM) within a local network, configure network permissions, and create a shared to-do list accessible from another VM on the same network. It covers Jira installation, network setup, and task sharing.

## Prerequisites

- Microsoft Azure subscription
- Two Azure VMs
- Basic knowledge of Azure networking

## Step 1: Install Jira on VM1

1. Create and configure an Azure VM (VM1).
2. Install Jira on VM1 and set up your Jira instance.

![image](https://github.com/itnatepena/jira-install/assets/147539410/e9bd3288-bcfc-4544-9ad1-d868dcfca2c0)

![image](https://github.com/itnatepena/jira-install/assets/147539410/6d978e95-afe8-4460-9561-4921be01d52c)


## Step 2: Set Up Network Permissions

1. Configure Network Security Group (NSG) rules for VM1.
2. Allow incoming traffic on port 8080 for Jira.
   
![image](https://github.com/itnatepena/jira-install/assets/147539410/305d6424-3e98-451a-a8f1-23ac6d4e4dea)

3. Allow inbound IPv4 traffic for VM2 to access Jira.
![image](https://github.com/itnatepena/jira-install/assets/147539410/ce24b8f9-e0d2-432d-8940-5c40947b817a)
<br> I've also added access to all of the local network computers that will be on 10.0.0.0/24.


## Step 3: Create VM2 and Test Connectivity

1. Create another Azure VM (VM2) on the same virtual network as VM1.
![image](https://github.com/itnatepena/jira-install/assets/147539410/03c73fa8-5e9a-4a4c-a7b0-6eb3d6d1ea16)

2. Test connectivity to Jira on VM1 using a web browser from VM2.
You may run into some issues, Personally, I had to also check the firewall and allow the same rules, IPv4 and 8080 inbound rules for VM1.

Here I made sure Jira was currently running as a service.
![image](https://github.com/itnatepena/jira-install/assets/147539410/199e1b69-668b-42e1-8aee-dfc93095f3a8)

Here I added a rule to Windows Firewall to allow inbound 8080 port access.
![image](https://github.com/itnatepena/jira-install/assets/147539410/ba39e868-746a-4f5e-83d1-ea4841029111)



## Step 4: Install and Configure Jira (Continued)

1. Finish the Jira setup on VM1.

![image](https://github.com/itnatepena/jira-install/assets/147539410/bca28c5a-e5fb-452d-aef7-68bc7f03a3cc)

You should be able to see this page now. If you aren't, there is likely an issue with the network. 

2. Configure your Jira instance as needed.
You may need to create an account, or if you have one already, you need to find the license key.
![image](https://github.com/itnatepena/jira-install/assets/147539410/c265c083-cbe3-4064-8678-23bc3f98c274)

![image](https://github.com/itnatepena/jira-install/assets/147539410/a6b830e8-0dc8-4b8c-a959-ed7e39677b4b)

![image](https://github.com/itnatepena/jira-install/assets/147539410/7d07aff6-a6be-4df6-8c4a-bcf1031b06df)



## Step 5: Add New Tasks to Jira

1. Create a to-do list in your Jira instance on VM1.

![image](https://github.com/itnatepena/jira-install/assets/147539410/ac63ef3e-3fe8-41ce-a2ce-564d9e45efaa)

2. Add tasks, for VM2 to view.
![image](https://github.com/itnatepena/jira-install/assets/147539410/2b0a014e-4d4e-498c-9812-1dcceda8e341)


## Step 6: Access To-Do List from VM2

1. On VM2, use a web browser to access Jira on VM1 via its public IP or hostname.
   ![image](https://github.com/itnatepena/jira-install/assets/147539410/e3a7002a-892c-45b5-b0bc-25e80763c9af)
Here I have accessed Jira which is located on VM1 from VM2(or VM3 in my case) 
2. Log in to Jira on VM1.
3. View and manage the shared to-do list.
![image](https://github.com/itnatepena/jira-install/assets/147539410/fe781c44-54a8-4c12-8433-00fc80a4cd9f)


## Conclusion

This project showcases the installation of Atlassian Jira, the configuration of network permissions for inter-VM connectivity, and sharing tasks between Azure VMs on the local network. It emphasizes the fundamental setup of Jira and collaborative task management.

Feel free to reach out if you have any questions or need further assistance.
