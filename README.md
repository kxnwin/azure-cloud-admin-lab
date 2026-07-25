# Azure Cloud Administration Lab

Hands-on Azure/Microsoft Entra ID administration lab, built to develop real
administration skills toward a Systems Administrator → Cloud
Administrator career path. This lab runs in parallel with a separate
[hybrid on-prem Active Directory + Entra ID lab](https://github.com/kxnwin/onprem-hybrid-identity-lab) and Phase 4 below ties the two together.

## Why this lab exists

I currently work as a Service Desk Specialist supporting Active Directory,
Entra ID, and identity/access management for a 20,000+ user healthcare enterprise
environment. This lab is where I practice admin-level skills — Entra ID user/group management, RBAC and Conditional Access, resource groups and VMs, networking — that go beyond what I do day-to-day on the service desk.

## Roadmap

* [x] **Phase 1 — Environment Setup**

  * [x] Create free Azure account
  * [x] Note what's included (credit, free services, always-free tier)
  * [x] Explore the portal (Entra ID, Virtual Machines, Resource Groups)
  * [x] Set a spending alert/budget


* [x] **Phase 2 — Entra ID Fundamentals**

  * [x] Create test users and groups
  * [x] Explore and assign built-in RBAC roles
  * [x] Configure a Conditional Access policy
  * [x] Create a Dynamic Group with an attribute-based rule

* [x] **Phase 3 — Core Azure Resource Management**

  * [x] Create a Resource Group and deploy a free-tier VM
  * [x] Practice start/stop/resize operations
  * [x] Build a Virtual Network + subnet
  * [x] Apply an Azure Policy (e.g., required tagging)

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
* **Companion project:** On-prem Hyper-V hybrid AD/Entra ID lab

## Status

🟡 In progress — Phase 5.

