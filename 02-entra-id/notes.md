# Phase 2 — Entra ID Fundamentals

## Goal

Practice cloud-side identity administration — the Entra ID mirror of the
on-prem AD work already done day-to-day at work.

## Tasks

* \[x] Create test users and groups
* \[x] Explore built-in roles (Global Admin, User Admin, etc.)
* \[x] Assign RBAC roles to test users
* \[ ] Configure a Conditional Access policy
* \[ ] Create a Dynamic Group using an attribute-based rule

## Notes

Preface: My goal is to simulate Microsoft Entra ID activities to that done in a daily work of an organization by creating users with realistic names, groups with realistic departments, and assigning roles that are suited properly for each user depending on their department.



Task 1) I started off by creating my first test user. I did this by navigating to the Microsoft Entra ID service on the left sidebar and selected the Users tab under the Manage section. I clicked New User and selected Create New User. I went through the creation process, naming the test user Sarah Mitchell. Then I gave the user the principal name of "sMitchell", put their first and last name as the display name, and gave it an auto-generated password by Entra ID for their login. I skipped over the properties and assignments for the user for now. Once all necessary information was set, I reviewed and created the first test user. See "User\_Creation.png" and "Entra\_ID\_Users\_List.png" screenshots.



Task 2) Next, I hopped over to the Groups tab and clicked New Group. I named the group "Accounting", as an example department of an organization. I set the group type as "Security" and inputted "Security group for Accounting department to access shared drives, finance applications, and department resources" for the group description. I added the user, Sarah Mitchell, to be a member of the group then completed group creation. See "group\_creation.png" and "accounting\_group\_members.png" screenshots.



Task 3) After creating my first test user and group, I explored the built-in roles from the Roles and administrators section of Microsoft Entra ID. Looking through the list of roles and admiring how detailed each one was, I was able to find one that would suit Sarah; the Billing Administrator role. I assigned them this role by going to the Users section, clicking on their profile, navigated to the Assigned roles section, and then adding the Billing Administrator role to them. See "Assigning\_User\_Role.png" and "user\_role\_assigned.png" screenshots.



Task 4 \& 5) TBD, requires Microsoft Entra premium, which unfortunately come with the free trial of Azure. I will return to these two tasks once I complete the rest of the phases and finding if any other tasks requires premium as well, as then will I register for the free trial of premium. For the moment though, if I were to create a conditional access policy for Sarah, I would name the policy "Require MFA". The condition for it will be if they are working outside of company network, then they will be required to sign in with multifactor authentication.

