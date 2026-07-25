# Phase 4 — Hybrid Identity Tie-In

## Goal

Connect this lab to the on-prem Hyper-V AD lab. This is the differentiator —
most entry-level candidates can only speak to one side (on-prem OR cloud),
not the sync between them.

## Prerequisites

* On-prem AD lab: domain controller, OU structure, and Entra Connect sync
must be functional first (see companion repo)

## Tasks

* \[x] Confirm on-prem test users sync into Entra ID via Entra Connect
* \[x] Verify synced users land in the correct cloud groups/RBAC roles
* \[x] Write up the full end-to-end flow: on-prem AD → Entra Connect →
Entra ID → RBAC assignment
* \[x] Diagram the hybrid identity architecture

## Notes

This phase's work was performed and documented in detail in the companion on-prem lab (onprem-hybrid-identity-lab), Phase 4 — see that repo for full troubleshooting notes (networking, DNS, IE security zone issues, Entra Connect installation) and the RBAC verification walkthrough.



Summary of what was verified from this (Azure lab) side:



Task 1 - Confirmed all 8 on-prem KuCorp OU users (plus the svc-EntraConnect service account) synced successfully into this tenant via Entra Connect, showing On-premises sync: Yes in Entra ID. See "Entra\_Connect\_Sync\_Successful.png".



Task 2 - Confirmed synced users correctly inherit cloud group membership based on synced attributes — specifically, Sarah Mitchell (Department: Accounting) automatically landed in DG\_Accounting, the dynamic group built in this lab's Phase 2. See "Cloud\_Membership\_Synced.png"



Discovered and corrected a gap from this lab's original Phase 2 Task 3: the "Billing Administrator" role assigned to the original Sarah was a Microsoft Entra ID directory role, not Azure RBAC. Assigned true Azure RBAC (Reader) to DG\_Accounting at the rg-lab-eastus scope to properly demonstrate group-based cloud access tied to on-prem identity



Task 3 - See on-prem lab Phase 4 for the complete technical narrative.



Task 4- Verified end-to-end via Check access: synced Sarah inherits Reader on rg-lab-eastus through DG\_Accounting membership

Full flow diagram: See "Onprem\_to\_Cloud\_Diagram.png".



