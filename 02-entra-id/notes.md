# Phase 2 — Entra ID Fundamentals

## Goal

Practice cloud-side identity administration — the Entra ID mirror of the
on-prem AD work already done day-to-day at work.

## Tasks

* \[x] Create test users and groups
* \[x] Explore built-in roles (Global Admin, User Admin, etc.)
* \[x] Assign RBAC roles to test users
* \[x] Configure a Conditional Access policy
* \[x] Create a Dynamic Group using an attribute-based rule

## Notes

Preface: My goal is to simulate Microsoft Entra ID administration — realistic user names, department-based groups, and roles assigned according to department, rather than generic data. 



Task 1) Created the first test user through Entra ID → Users → Create New User. Named the user Sarah Mitchel, set the principal name to "sMitchell," and used an auto-generated password. Properties and assignments were skipped at creation and configured in later tasks. See "User_Creation.png" and "Entra_ID_Users_List.ong".

Created a Security group named "Accounting" (description: security group for the Accounting department to access shared drives, finance applications, and department resources) and added Sarah mitchell as a member. See "group_creation.png" and "accounting_group_members.png"



Task 2) Reviewed the built-in roles under Roles and Administration, looking for one that would realistic ally fit Sarah's department. See "Roles.png"  



Task 3) Assigned Sarah the Billing Administator role via her user profile → Assigned roles. See "Assigning_User_Role.png" and "user_role_assigned.png" screenshots.



Task 4) Configured a conditional Access policy requiring MFA. 

* Retrieving a Microsoft Entra ID P1 trial license was a prerequisite. This required creating a dedicated Global Administrator account, since the Microsoft 365 admin center only accepts sign-in from a work account (the existing account was a guest/personal-account identity). MFA setup via Microsoft Authenticator was required to complete that admin account's first login.

* Started the Entra ID P1 trial from the Billing section of the M365 admin center, then assigned the license to Sarah. Hit a licensing error — assignment was blocked until Sarah's usage location was set to United States, after which the license applied successfully.

* Built the conditional Access policy ("Require MFA") in the Entra admin center, scoped to Sarah, targeting all resources, with "Require multifactor authentication" as the grant control. Security defaults had to be disabled first, since Conditional Access and Security Defaults are mutually exclusive. See "Conditional_Access_Policy_Created.png"

* Verified the policy by signing in as Sarah at portal.azure.com — she was prompted to set up MFA, confirming enforcement. See "Require_MFA_Policy_Test.png"



Task 5) Created a Dynamic Group ("DG_Accounting") with membership type set to Dynamic User, using the rule department Equals Accounting. Sarah's department attribute was initially blank, so no members matched until it was updated to "Accounting" — after which she was picked up by the rule within seconds, confirming the dynamic query worked correctly. See "Dynamic_Group_Created.png" and "Dynamic_Group_Assigned.png".

* Lesson: Dynamic group membership is purely attribute-driven — being in a related static group (like Accounting) has no bearing on it. The actual attribute has to be populated on the user object.



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