# Phase 2 — Entra ID Fundamentals

## Goal

Practice cloud-side identity administration — the Entra ID mirror of the
on-prem Active Directory work already done day-to-day at work.

## Tasks

* [x] Create test users and groups
* [x] Explore and assign built-in Microsoft Entra ID and Azure roles
* [x] Configure a Conditional Access policy
* [x] Create a Dynamic Group using an attribute-based rule

## Notes

**Preface** - My goal is to utilize Microsoft Entra ID service to simulate a realistic organization, creating realistics user names, groups, and roles assigned according to properties like job title or department, rather than generic data. Practice going through the workflow as someone who would use this service. 

**Task 1 - Create test users and groups**

 Created the first test user through Microsoft Entra ID → Users → Create New User. Set name as "Sarah Mitchell", user principal name (UPN) as "sMitchell", and enabled account and auto-generated password. Properties and assignments were skipped at creation and configured in later tasks. See "User_Creation.png" and "Test_User_Created.ong".

Created the first group through Microsoft Entra ID → Groups → New Group. Set group type as security, titled it "Accounting", typed the description as "security group for the Accounting department to access shared drives, finance applications, and department resources," and set membership type as assigned. See "Group_Created.png"

Added the "Accounting" group membership to Sarah through Microsoft Entra ID → Groups → All Groups → Accounting → Manage → Members → Add members. See "Accounting_Group_Membership.png".

**Task 2 - Explore and assign built-in Microsoft Entra ID and Azure roles**

Reviewed the built-in Microsoft Entra ID roles through Microsoft Entra ID → Roles and administrators. See "Roles.png" Found the "Billing Administrator" role which suites Sarah based on her department (Accounting).

 Assigned Sarah the role via Microsoft Entra ID → Users → Sarah Mitchell → Assigned roles → Add Assignments. See "User_Role_Assigned.png".

Explored Azure RBAC roles via Resource Manager → Resource Groups → rg-lab-eastus → Access Control (IAM) → Add role assignment. Selected the "Reader" RBAC role and assigned it to the Accounting dynamic group we created in task 4. See "Azure_RBAC_Role_Assigned.png".    

Lesson: Directory roles govern permissions within Entra ID/M365 admin functions; Azure RBAC governs permissions on Azure resources (VMs, resource groups, etc.) via IAM. 

**Task 3 - Configured a conditional Access policy requiring MFA**

Retrieving a Microsoft Entra ID P1 trial license was a prerequisite. This required creating a dedicated Global Administrator account, since the Microsoft 365 admin center only accepts sign-in from a work account (the existing account was a guest/personal-account identity). MFA setup via Microsoft Authenticator was required to complete that admin account's first login.

Started the Entra ID P1 trial from the Billing section of the M365 admin center, then assigned the license to Sarah. Hit a licensing error — assignment was blocked until Sarah's usage location was set to United States, after which the license applied successfully.

Built the Conditional Access policy ("Require MFA") in the Entra admin center, scoped to Sarah, targeting all resources, with "Require multifactor authentication" as the grant control. Security defaults had to be disabled first, since Conditional Access and Security Defaults are mutually exclusive. See "Conditional_Access_Policy_Created.png"

Verified the policy by signing in as Sarah at portal.azure.com — she was prompted to set up MFA, confirming enforcement. See "Require_MFA_Policy_Test.png"

**Task 4 - Create a Dynamic Group with an attribute-based rule** 

Created a Dynamic Group ("DG_Accounting") with membership type set to Dynamic User, using the rule department Equals Accounting. Sarah's department attribute was initially blank, so no members matched until it was updated to "Accounting" — after which she was picked up by the rule within seconds, confirming the dynamic query worked correctly. See "Dynamic\_Group\_Created.png" and "Dynamic_Group_Assigned.png".

Lesson: Dynamic group membership is purely attribute-driven — being in a related static group (like Accounting) has no bearing on it. The actual attribute has to be populated on the user object.

## Key Terms

* RBAC (Role-Based Access Control): Assigns permissions to users based on an assigned role rather than granting access individually.
* Security Group: A group type used to manage access to resources (as opposed to a Microsoft 365 Group, which is collaboration-focused).
* Billing Administrator: A built-in Entra ID role scoped to managing billing and subscription-related tasks.
* Conditional Access: A policy engine that enforces access controls (like requiring MFA) based on conditions such as user, location, or device.
* Security Defaults: Microsoft's baseline, one-size-fits-all tenant security settings; must be disabled to use custom Conditional Access policies.
MFA (Multi-Factor Authentication): Requires a second verification step beyond a password to sign in.
* Entra ID P1: A premium licensing tier that unlocks features like Conditional Access and Dynamic Groups.
* Usage Location: A user attribute specifying their country/region, required before certain licenses can be assigned.
* B2B Guest Account: An external identity invited into a tenant, distinct from a native work/school account — has different sign-in behavior for some admin tools.
* Dynamic Group: A group whose membership is automatically calculated based on user or device attributes, rather than manually assigned.

