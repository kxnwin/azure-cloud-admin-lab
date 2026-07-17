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

Task 1) Created a resource group named "rg-lab-eastus" via Resource Manager → Resource groups. Added tags in name:value formtat — environment:lab, owner:kujay, purpose:azure-admin-practice — then reviewed and created. See "Resource_Group_Creation.png" and "Resource_Group_Created.png"



Task 2) Deployed the first VM into the resource group — the more involved task of the phase. 

* Sizing was the main obstacle: the initial pick, B2s (cost-efficient), wasn't availible in any US region on a new subscription. Switched to D2s_v3 — general purpose, slightly more cost, but well within the $200 credit line. 

* OS: Windows Server 2022 Datacenter Gen2, a common real-world baseline. All other settings left at default as not relevant for a single lab VM. Auto-shutdown enabled to control cost. 

* Validation flagged RDP open to the internet by default — locked it down to a specific IP instead. Azure's IP auto-detect failed to save correctly on the first few attempts, so the IP was entered manually as a workaround. 

* Validation passed clean on final review; created as "vm-lab-01". See "VM_Created.png".



Task 3) Tested start/stop/ functions on the VM — quick and straightforward. Then practiced resizing via Availiability + scale → Size: resized up to D4s_v3 (4 vCPUs, 16GB RAM, $274.48/month) to see the process work, then resized back down to D2s_v3 (2 vCPUs, 8GB RAM) for cost efficiency. Resize operation itself was fast in both directions. See "VM_Resize.png". 

Lesson: Resizing is quick and low-risk to test on a lab VM, but the cost swing between sizes can be dramatic — worth checking the monthly estimate before committing to a size for anything beyond a quick test.


Task 4) Built a virtual network and subnet. Created "vnet-lab-01" with address space 10.1.0.0/16 — chosen to avoid overlap with the existing VM's vnet (10.0.0.0/16). Added a second subnet, "subnet-lab-01" (10.1.10/24), alongside the default subnet, again to avoid any overlap. All other settings left at default; deployed after validation passed. See "vnet+subnet_creation.png" and "vnet_deployed.png"



Task 5) Applied an Azure Policy. Located the built-in "Require a tag on resources" policy definition, assigned it with scope set to the "rg-lab-eastus" resource group and tag name "Environment", keeping all other settings default. Reviewed and created. See "policy_assigned.png"



## Key Terms

* VM Size (SKU): The hardware profile a VM runs on — determines vCPU count, RAM, storage limits, and cost (e.g., D2s_v3).
* NSG (Network Security Group): A firewall-like set of rules controlling inbound/outbound traffic to Azure resources.
* RDP (Remote Desktop Protocol): The protocol used to remotely access a Windows VM's desktop.
* Auto-shutdown: A VM setting that automatically powers off the VM on a schedule, used to control cost.
* Virtual Network (VNet): An isolated network within Azure used to host and connect resources like VMs.
* Subnet: A segmented range of IP addresses within a VNet, used to organize and control traffic between resources.
* Azure Policy: A governance tool that enforces rules across resources, such as requiring specific tags.
Tag: A name:value label attached to a resource for organization, cost tracking, or policy enforcement.