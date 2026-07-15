# Phase 3 — Core Azure Resource Management

## Goal

Get hands-on with the bread-and-butter tasks that come up constantly in
both real Cloud Admin work and the AZ-104 exam.

## Tasks

* \[x] Create a Resource Group
* \[x] Deploy a free-tier VM into it
* \[x] Practice start/stop/resize on the VM
* \[x] Build a Virtual Network + subnet
* \[x] Apply an Azure Policy (e.g., require a tag on all resources)

## Notes

Task 1) Starting from the Azure portal, I redirected to Resource Manager service via search bar and then went into the Resource groups section. From there I went through the process of creating a resource group named "rg-lab-eastus". I added the following tags in the format, name:value, as follows:environment:lab, owner:kujay, purpose:azure-admin-practice. Afterwards, I reviewed and created the first resource group. See "Resource\_Group\_Creation.png" and "Resource\_Group\_Created.png".



Task 2) Next, I navigated to Compute infrastructure service, went into the Virtual machines section and went through the process of creating my first one. Now this task was bit more difficult to complete. I ran into several issues throughout the process of creating and deploying a virtual machine (vm) into the resource group. The main issue that took me a while to resolve was trying to find a size for the vm that was available in the east US region and cost efficient enough for my $200 credit limit. I Initially wanted to go with Bsv2 size because it was cost-efficient but it was not available in any US regions, so I decided to go with another general one that was recommended, the D2s\_v3. The D2s\_v3 size was for general purpose and a bit more costly, but that was fine since it was still within my credit limit. For the operating system, I went with the Windows Server 2022 Datacenter Gen2 as that is commonly used. I left the rest of the settings as default as none were much relevant for a single lab vm. I enabled auto-shutdown to control cost. Once I got to the review step, the initial validation passed for the vm creation but Azure flagged that the RDP was open to the internet by default, so I decided to lock it down with my ip adddress instead of leaving it wide open. However, Azure failed to save my ip address that it auto-detected several times, so I had to do a quick workaround by manually inputting the IP address and saving it. After checking through to make sure the settings were good to go for the virtual machine and validation has passed with nothing flagged, I finally created the vm named "vm-lab-01". See "VM\_Created.png".



Task 3) With the virtual machine (vm) created, I first tested out the start and stop functions for the vm within the profile, fairly quick and easy to do. Next I went resize the vm by navigating to Size section under the Availability + scale tab. I wanted to see how the resizing process worked so I resized the vm to D4s\_v3 version size with 4 vCPUs and 16 RAM, which costs $274.48 per month, definitely over my credit limit. So I went ahead and resized it back to D4s\_v3 version with 2 vCPUs and 8 RAM as it is more cost efficient to run. The resizing process itself was also fairly quick and easy to do. See VM\_Resize.png screenshot.



Task 4) I tried my hands on building a virtual network and subnet. I navigated to the Virtual networks service of the Azure portal and created a virtual network named "vnet-lab-01". I set the address as 10.1.0.0/16 so it doesn't overlap my existing VM's vnet, which is likely 10.0.0.0/16. Aside from the default subnet I was provided, I added my own, named "subnet-lab-01" with an address of 10.1.1.0/24 so no overlapping occurs with the default subnet. I Kept all other settings at default, reviewed, and deployed my first virtual network after validation passed. See "vnet+subnet\_creation.png" See "vnet\_deployed". 



Task 5) Lastly, I worked on applying an Azure policy. I navigated to the Policy service. Went to the definitions tab under the authoring section. There were many policies listed, so I searched for the "require a tag on resources" policy. Once found, I went through the policy assignment process. I set the scope to the "rg-lab-eastus" resource group, then set the tag name as "Environment". Next, I kept all other setting defaults, then review and created the policy. See "policy\_assigned.png"



