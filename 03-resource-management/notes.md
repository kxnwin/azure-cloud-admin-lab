# Phase 3 — Core Azure Resource Management

## Goal

Get hands-on with the bread-and-butter tasks that come up constantly in
both real Cloud Admin work and the AZ-104 exam.

## Tasks

* \[x] Create a Resource Group
* \[x] Deploy a free-tier VM into it
* \[ ] Practice start/stop/resize on the VM
* \[ ] Build a Virtual Network + subnet
* \[ ] Apply an Azure Policy (e.g., require a tag on all resources)

## Notes

From the azure portal, I navigated to the Resource Manager section to create a resource group named "rg-lab-eastus". Next, I added the following tags to it, (name:value): environment:lab, owner:kujay, purpose:azure-admin-practice. After adding the tags, I submitted and now have created my first resource group. See "Resource\_Group\_Creation.png" and "Resource\_Group\_Created.png". 



Next I created a virtual machine. Ran into several issues with the process of setting it up, mainly trying to find the size the was good to use and available in the selected region (US East). Initially wanted to go with Bsv2 quota but it was not available in any US regions, so decided to go with another general one that was recommended, the D2s\_v3. I was initially going for Bsv2 because it's more cost-efficient vs the D2s\_v3, but the D2s\_v3 is a general purpose/compute optimized family, which works fine too, just a bit more costly. For the operating system, I went with the Windows Server 2022 Datacenter Gen2. Mostly left other settings at default (disks, networking, management, monitoring, advanced tabs) as none were much relevant for a single lab vm. I did enable auto-shutdown to control cost. Initial validation passed for vm creation but Azure flagged that the RDP was open to the internet by default, so I decided to lock it down with my ip adddress instead of leaving it wide open. Azure failed to save my ip address that it auto-detected several times, so I had to workaround and manually input the IP address and save it, which worked. After checking through to make sure the settings were good to go for the virtual machine and validation has passed, I created the vm. See "VM\_Created.png".

