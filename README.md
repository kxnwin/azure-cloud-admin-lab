# Azure Cloud Administration Lab

Hands-on Azure/Microsoft Entra ID administration lab, built to develop real
cloud administration skills toward a Systems Administrator → Cloud
Administrator career path. This lab runs in parallel with a separate
[hybrid on-prem Active Directory + Entra ID lab](https://github.com/kxnwin/onprem-hybrid-identity-lab), and Phase 4 below ties the two together.

## Why this lab exists

I currently work as a Service Desk Specialist supporting Active Directory,
Entra ID, and identity/access management for a 20,000+ user enterprise
environment. This lab is where I go beyond day-to-day support tickets and
practice the administrator-level tasks — resource management, RBAC,
governance, networking — that the next step in my career requires.

## Roadmap

* \[x] **Phase 1 — Environment Setup**

  * \[x] Create free Azure account
  * \[x] Familiarize with Azure Portal navigation
* \[x] **Phase 2 — Entra ID Fundamentals**

  * \[x] Create test users and groups
  * \[x] Explore and assign built-in RBAC roles
  * \[x] Configure a Conditional Access policy
  * \[x] Create a Dynamic Group with an attribute-based rule
* \[x] **Phase 3 — Core Azure Resource Management**

  * \[x] Create a Resource Group and deploy a free-tier VM
  * \[x] Practice start/stop/resize operations
  * \[x] Build a Virtual Network + subnet
  * \[x] Apply an Azure Policy (e.g., required tagging)
* \[ ] **Phase 4 — Hybrid Identity Tie-In**

  * \[ ] Document how on-prem AD users sync into Entra ID via Entra Connect
  * \[ ] Confirm synced users receive correct cloud RBAC roles
  * \[ ] Write up the end-to-end hybrid identity flow
* \[ ] **Phase 5 — AZ-104 Prep**

  * \[ ] Work through Microsoft Learn's AZ-104 learning path
  * \[ ] Schedule/take the AZ-104 exam

## Repo structure

```
azure-cloud-admin-lab/
├── README.md                  ← you are here
├── docs/
│   └── session-log.md         ← running log of each work session
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

Each phase folder has a `notes.md` — jot down what you did, screenshots
(drop image files in the same folder and link them), what broke, and what
you learned.

## Tools \& environment

* **Platform:** Microsoft Azure (free tier)
* **Identity:** Microsoft Entra ID
* **Learning path:** Microsoft Learn — AZ-104 (Azure Administrator Associate)
* **Companion project:** On-prem Hyper-V hybrid AD/Entra ID lab (desktop)

## Status

🟡 In progress — Hyper-V lab in progress, must be set up properly before starting phase 4.

