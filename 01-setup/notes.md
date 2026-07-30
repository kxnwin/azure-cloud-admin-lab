# Phase 1 — Environment Setup

## Goal

Get an Azure account running and get comfortable navigating the portal
before deploying any actual infrastructure.

## Tasks

* [x] Create a free Azure account (portal.azure.com)
* [x] Note what's included: $200 credit (30 days), 12 months of popular
services free, always-free services
* [x] Explore the portal: Virtual Machines, Entra ID, Resource Groups
* [x] Set a spending alert/budget so the free tier doesn't get exceeded
by accident

## Notes

**Task 1 - Create a free Azure account (portal.azure.com)**

Created an Azure account through portal.azure.com. The signup process required a phone number and a card on file, which was unexpected since the account itself is free.  

**Task 2 - Note what's included: $200 credit (30 days), 12 months of popular services free, always-free services**

Azure dashboard showed the $200 in credit immediately, confirming that the free-trial credit was applied. The other free-tier services weren't tested directly, but were noted as part of what the free account includes.  

**Task 3 - Explore the portal: Virtual Machines, Entra ID, Resource Groups**

Explored the portal and its variety of services and resources. Spent more time in Microsoft Entra ID specifically, see "Microsoft_Entra_ID.png" (Entra ID overview shown in screenshot was taken during phase 2 rather than the original phase 1 exploration, but the portal layout is identical either way).
 
Familiarized with the layout of the Microsoft Entra admin center due to the nature of using this service daily at work, looking at things like user's information like their properties, group memberships, licenses and MFA methods.

Reviewed Virtual Machines and Resource Groups to get a feel for two commonly used services before touching them directly in later phases. Resource Groups was empty and no Virtual Machines existed yet at this point, since neither had been created.

**Task 4 - Set a spending alert/budget so the free tier doesn't get exceeded by accident**

Set up a budget via Azure's Cost Management tool. Created an alert threshold at $5, to catch any unexpected spending early rather than risk burning through the $200 credit unnoticed. See "Budget_Alert_Configured.png".

Lesson: Setting a spending alert matters even on a small lab budget — going over a limit without noticing means spending more than intended, which is a real cost risk in a company setting if left unmonitored.

## Key Terms

* Virtual Machine: A computer that exists as software rather than as a physical hardware. Can be used for a lot of things such as running a server, testing software, being a desktop someone can log into, lab practice, etc.
* Resource Group: A container that holds Azure resources like virtual machines, networks, or storage, grouped together for a project. 
* Entra ID: A cloud-based service for identity and access management — used to create users and groups, and assign roles to control what people can access. 
* Cost Management: A service for setting a spending limit on Azure resources (like VMs), so usage doesn't go over a certain amount without you knowing. 