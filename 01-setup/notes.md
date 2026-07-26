# Phase 1 — Environment Setup

## Goal

Get an Azure account running and get comfortable navigating the portal
before deploying any actual infrastructure.

## Tasks

* [x] Create free Azure account (portal.azure.com)
* [x] Note what's included: $200 credit (30 days), 12 months of popular
services free, always-free services
* [x] Explore the portal: Virtual Machines, Entra ID, Resource Groups
* [x] Set a spending alert/budget so the free tier doesn't get exceeded
by accident

## Notes

**Task 1 - Create free Azure account (portal.azure.com)**

 Created an Azure account. Signup required a phone number and a card on file even though the account itself is free. 

**Task 2 - Note what's included: $200 credit (30 days), 12 months of popular services free, always-free services**

 Azure dashboard showed the $200 in credit immediately, confirming how the free-trial credit gets applied. 

**Task 3 - Explore the portal: Virtual Machines, Entra ID, Resource Groups**

 Explored the portal and its vast amount of services and resources. Spent more time in Microsoft Entra ID specifically (See "Microsoft_Entra_ID.png" (Entra ID overview shown here reflects a later point in the lab (Microsoft Entra ID P1, 3 Users)— this screenshot was taken during phase 2 work rather than the original phase 1 exploration, but the portal layout/navigation is identical either way). I was familar with the Users section of the Entra ID as I use it daily at my current service desk job within the Microsft Entra admin center, looking at users' information like their groups and licenses. However, noticed it was different layout as the Entra ID for this lab was navigated through the Azure portal rather than the admin center, so it had different functionality, yet some similarities. Looked over virtual machines and resource groups to get a feel for two commonly used services before touching them directly in later phases. Resource Groups was empty at this point since none had been created yet. 

**Task 4 - Set a spending alert/budget so the free tier doesn't get exceeded by accident**

Set up a budget in Cost Management with an alert threshold at $5, to catch any unexpected spend early rather than risk burning through the $200 credit unnoticed.

*  Lesson: Setting a spending alert matters even on a small lab budget — going over a limit without noticing means spending more than intended, which is a real cost risk in a company setting if left unmonitored.

## Key Terms

* Resource Group: A container that holds Azure resources like virtual machines, networks, or storage, grouped together for a project. 
* Entra ID: A cloud-based service for identity and access management — used to create users and groups, and assign roles to control what people can access. 
* Cost Management: A tool for setting a spending limit on Azure resources (like VMs), so usage doesn't go over a certain amount without you knowing. 