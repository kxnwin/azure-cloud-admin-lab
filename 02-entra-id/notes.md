# Phase 2 — Entra ID Fundamentals

## Goal

Practice cloud-side identity administration — the Entra ID mirror of the
on-prem Active Directory work.

## Tasks

* [x] Create test users and groups
* [x] Explore and assign built-in Microsoft Entra ID and Azure roles
* [x] Configure a Conditional Access policy
* [x] Create a Dynamic Group using an attribute-based rule

## Notes

**Task 1 - Create test users and groups**

Created a test user through Entra ID → Users → Create New User. Set name as "Sarah Mitchell", user principal name (UPN) as "sMitchell", and enabled account and auto-generated password. Properties and assignments were skipped at creation and configured in later tasks. See "User_Creation.png" and "Test_User_Created.png".

Created a group through Entra ID → Groups → New Group. Set group type as security, titled group as "Accounting", input description as "security group for the Accounting department to access shared drives, finance applications, and department resources," and set membership type as assigned. See "Group_Created.png"

Added the "Accounting" group membership to Sarah through Microsoft Entra ID → Groups → All Groups → Accounting → Manage → Members → Add members. See "Accounting_Group_Membership.png".

**Task 2 - Explore and assign built-in Microsoft Entra ID and Azure roles**

Reviewed the built-in Microsoft Entra ID roles through Entra ID → Roles and administrators. Found the "Billing Administrator" role which suits Sarah based on her department (Accounting).
Assigned Sarah the role via Entra ID → Users → Sarah Mitchell → Assigned roles → Add Assignments. See "User_Role_Assigned.png".

Explored Azure RBAC roles via Resource Manager → Resource Groups → rg-lab-eastus (resource group created in phase 3) → Access Control (IAM) → Add role assignment. Selected the "Reader" RBAC role (a common role for users who can see resources, their configurations, settings, metrics but can't create, modify, or delete anything) and assigned it to the "DG_Accounting" dynamic group created in task 4. See "Azure_RBAC_Role_Assigned.png".

Lesson: Directory roles gives permissions within Entra ID/M365 admin functions whereas Azure RBAC gives permissions on Azure resources (VMs, resource groups, etc.) via IAM. Assigning the wrong type can create a false sense of access. For instance, giving Sarah Billing Administrator granted her department-relevant access, but it didn't actually let her view or interact with any Azure resources. The Reader role assigned to her group is what actually gives her real, working access to the resource group.  

**Task 3 - Configured a Conditional Access policy requiring MFA**

Before configuring a conditional access policy, retrieving a Microsoft Entra ID P1 trial license was a prerequisite. This required creating a dedicated Global Administrator account, since the Microsoft 365 admin center only accepts sign-in from a work account; the existing account was a personal account. Signed into the admin center with the Administrator account created. MFA setup via Microsoft Authenticator was required to complete that admin account's first login. Once completed, admin login was successful to get onto the admin center. 

Navigated to Entra ID P1 trial license by going through Microsoft 365 admin center → Marketplace → All products → Microsoft Entra ID P1 Trial. Had to set up payment method as required although it won't charge for the free trial.

Once Microsoft Entra ID P1 Trial license was added to the account, assigned the license to Sarah by going through Billing → Licenses → Microsoft Entra ID P1 → Assign licenses. Ran into a licensing error that the assignment was blocked until Sarah's usage location was set to United States, which the license then applied successfully after updating usage location. See "Entra_ID_P1_License_Assigned.png".

Built the Conditional Access policy ("Require MFA") through Microsoft Entra admin center → Entra ID → Conditional Access → Create new policy. Scoped policy to Sarah, targeting all resources, with "Require multifactor authentication" as the grant control. Security defaults had to be disabled first, since Conditional Access won't work if it's enabled. See "Conditional_Access_Policy_Created.png" and "Security_Defaults_Disabled.png"

Verified the conditional access policy worked by signing in as Sarah on portal.azure.com in which MFA setup was prompted, confirming enforcement. See "Require_MFA_Policy_Test.png"

**Task 4 - Create a Dynamic Group with an attribute-based rule** 

Navigated to Entra ID → Groups → New group. Created a Dynamic Group ("DG_Accounting") with membership type set to Dynamic User, using the rule "department Equals Accounting". Sarah's department attribute was initially blank, so she did not match until it was updated to Accounting, after which she was picked up by the rule within seconds, confirming the dynamic group is working correctly as it should. See "Dynamic_Group_Created.png" and "Dynamic_Group_Assigned.png". 

Lesson: Dynamic group membership is purely attribute-driven, whereas being in a static group like Accounting doesn't do anything. The actual attribute has to be populated on the user object. If Sarah did not have Accounting listed in her department property, then the group would have never auto-assigned to her because she did not meet the rule that was set. 

## Key Terms

* Entra ID (Directory) Role: A role that gives access to do certain things within the Entra ID/M365 realm (e.g., Billing Administrator).
* Azure RBAC (Role-Based Access Control): A role that gives access to do certain things to Azure resources, like resource groups or VMs (e.g., Reader), assigned through a resource's Access Control (IAM).
* Security Group: A group type used to manage access to resources.
* Conditional Access: A policy engine that enforces access controls (like requiring MFA) based on conditions such as user, location, or device.
* Multi-Factor Authentication (MFA): Requires a second verification step beyond a password to sign in.
* Entra ID P1: A premium licensing tier that unlocks features like Conditional Access and Dynamic Groups.
* Dynamic Group: A group whose membership is automatically calculated based on user or device attributes, rather than manually assigned.

