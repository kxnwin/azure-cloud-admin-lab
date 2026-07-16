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

Preface: My goal is to simulate Microsoft Entra ID activities to that done in a daily work of an organization by creating users with realistic names, groups with realistic departments, and assigning roles that are suited properly for each user depending on their department.



Task 1) I started off by creating my first test user. I did this by navigating to the Microsoft Entra ID service on the left sidebar and selected the Users tab under the Manage section. I clicked New User and selected Create New User. I went through the creation process, naming the test user Sarah Mitchell. Then I gave the user the principal name of "sMitchell", put their first and last name as the display name, and gave it an auto-generated password by Entra ID for their login. I skipped over the properties and assignments for the user for now. Once all necessary information was set, I reviewed and created the first test user. See "User\_Creation.png" and "Entra\_ID\_Users\_List.png" screenshots.



Task 2) Next, I hopped over to the Groups tab and clicked New Group. I named the group "Accounting", as an example department of an organization. I set the group type as "Security" and inputted "Security group for Accounting department to access shared drives, finance applications, and department resources" for the group description. I added the user, Sarah Mitchell, to be a member of the group then completed group creation. See "group\_creation.png" and "accounting\_group\_members.png" screenshots.



Task 3) After creating my first test user and group, I explored the built-in roles from the Roles and administrators section of Microsoft Entra ID. Looking through the list of roles and admiring how detailed each one was, I was able to find one that would suit Sarah; the Billing Administrator role. I assigned them this role by going to the Users section, clicking on their profile, navigated to the Assigned roles section, and then adding the Billing Administrator role to them. See "Assigning\_User\_Role.png" and "user\_role\_assigned.png" screenshots.



Task 4) To begin this task, I first had to go through a series of steps to retrieve a Microsoft Entra ID P1 license (free trial). First I created an Administrator user with the global administrator role, in order for me to access the Microsoft Admin 365, as it only allowed login from a work account. After creating the Administrator user through Azure's Microsoft Entra ID service, I signed into Microsoft Admin 365 center with the Admin's User Principal Name and password I made for it. I had to set up authentication with Microsoft Authenticator as well as it required me before I could get logged in. Once I set that up, I logged in and looked for the Microsoft Entra ID P1 license (free trial) in the billing section and started the trial. 



Once I had the license added, I assigned the license to the user Sarah through the Active users section of the Microsoft 365 Admin center. I did bump into a small issue where it wasn't allowing me to assign the license to the user because their usage location was not set. Once I set to United Stated for Sarah, I was able to assign the license. I confirmed that Sarah was assigned the license on the Azure portal, I can now start this task. 



First I went to the Microsoft Entra admin center, a view that I was quite familiar with as I currently use this admin center at my current service desk job daily. I navigated to the conditional access section, went to policies tab, then created a new policy from there. I named the conditional access policy "Require MFA" and assigned it to Sarah. Before I could create the policy, I had to first disable security defaults, as I wouldn't allow be to create the policy without disabling it first. After doing so, I selected All resources as Target resources and for the access control, I selected Require multifactor authentication as a control to grant, then created the policy. See "Conditional\_Access\_Policy\_Created.png" 



I now had my first conditional access policy enabled, Require MFA, which is assigned to Sarah whom now has to authenticate upon login. I tested this policy out by signing into portal.azure.com as Sarah and then it gives me a message to keep the account secure by setting up authentication, which tells me that the policy is working. I know this because again, I do assist with this task for end users at my job almost daily, helping them register/reset MFA using Microsoft Authenticator. See "Require\_MFA\_Policy\_Test.png".



Task 5) Last task was to create a dynamic group. I navigated from Microsoft Entra Admin center to the groups section > all groups > new group. I named the Dynamic group "DG\_Accounting", set the group type as Security, and changed to Dynamic User for the membership type. A dynamic query linked popped up afterwards, which I clicked on and it opened up a rule builder. I used the simple UI provided to create a rule: Property = department, Operator = Equals, Value = Accounting. Once the dynamic group was created, I went back to Azure portal and updated Sarah's department to Accounting as it was initially blank. By doing this, the user will get picked up by the rule I've created from the dynamic group since it only cares if the department was Accounting. In just a few seconds, the Dynamic group already had one user added after being created, which was Sarah. This confirmed the rule within the DG\_Accounting group was a success! See "Dynamic\_Group\_Created.png".

