# Azure Cloud Administration Lab

Hands-on Azure/Microsoft Entra ID administration lab, built to develop real
administration skills toward a Systems Administrator → Cloud
Administrator career path. This lab runs in parallel with a separate
[On-Prem Hybrid Identity Lab](https://github.com/kxnwin/onprem-hybrid-identity-lab) and Phase 4 below ties the two together.

## Why this lab exists

This lab is something I built to learn cloud administration skills, mainly around the Azure portal and Entra ID, which I utilize constantly at my job. My daily work in Active Directory and Entra ID is mostly looking things up like user accounts, group memberships, MFA methods, and lockout status to help troubleshoot issues. I also use an internal tool that can do some of those things as well but also gives me the ability to reset user passwords. This lab is where I go past day-to-day troubleshooting and actually practice the admin side: creating users and groups, assigning roles, setting up policies, that kind of thing. 

## Roadmap

* [x] **Phase 1 — Environment Setup**

  * [x] Create a free Azure account (portal.azure.com)
  * [x] Note what's included (credit, 12 months of free services, always-free tier)
  * [x] Explore the portal (Entra ID, Virtual Machines, Resource Groups)
  * [x] Set a spending alert/budget

* [x] **Phase 2 — Entra ID Fundamentals**

  * [x] Create test users and groups
  * [x] Explore and assign built-in Entra ID and Azure roles
  * [x] Configure a Conditional Access policy
  * [x] Create a Dynamic Group with an attribute-based rule

* [x] **Phase 3 — Core Azure Resource Management**

  * [x] Create a Resource Group
  * [x] Deploy a free-tier Virtual Machine (VM) into it
  * [x] Practice start/stop/resize operations on the VM
  * [x] Build a Virtual Network + Subnet
  * [x] Apply an Azure Policy (required tagging)

* [x] **Phase 4 — Hybrid Identity Tie-In**

  * [x] Confirm on-prem test users sync into Entra ID via Entra Connect
  * [x] Verify synced users land in the correct cloud groups/RBAC roles
  * [x] Write up the full end-to-end flow: on-prem AD → Entra Connect →
Entra ID → RBAC assignment
  * [x] Diagram the hybrid identity architecture

* [ ] **Phase 5 — AZ-104 Prep**

  * [ ] Work through Microsoft Learn's AZ-104 learning path
  * [ ] Schedule/take the AZ-104 exam

## Repo structure

```
azure-cloud-admin-lab/
├── README.md                  ← you are here
├── 01-setup/
│   └── notes.md
├── 02-entra-id/
│   └── notes.md
├── 03-resource-management/
│   └── notes.md
├── 04-hybrid-identity/
│   └── notes.md
└── 05-az104-prep/
    └── notes.md
```

## Tools \& environment

* **Platform:** Microsoft Azure (free tier)
* **Identity:** Microsoft Entra ID
* **Learning path:** Microsoft Learn — AZ-104 (Azure Administrator Associate)
* **Companion project:** On-Prem Hybrid Identity Lab

## Status

🟡 In progress — Phase 5.