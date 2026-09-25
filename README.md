# Microsoft-Entra-ID---User-Management-Guide-Scripts
A comprehensive guide and set of automation scripts for managing users in **Microsoft Entra ID** (formerly Azure Active Directory). This repository covers creating internal users, inviting external guest users (B2B), and soft/hard deleting user accounts via the **Entra Admin Center** and **Microsoft Graph PowerShell**
Purpose & Scope
This article provides instructions for creating, inviting, and deleting users in Microsoft Entra ID, including details on user types and their authentication methods. It also covers creating users in external tenants for Microsoft Entra External ID scenarios.

Value Proposition
Understanding how to manage users effectively in Microsoft Entra ID enhances organizational flexibility and security, ensuring appropriate access levels for different user types.

Quick Summary of Content
User Types: Describes internal members, internal guests, external members, and external guests, along with their authentication methods and privileges.
Prerequisites: Lists required roles for user creation and management.
Creating Users: Step-by-step process for creating new users, including filling out necessary fields and assigning roles or groups.
Inviting External Users: Instructions for inviting external guests, including email invitation processes.
Deleting Users: Steps to delete users, including role requirements and recovery options for deleted accounts

Microsoft Entra ID allows you to create several types of users in your tenant, which provides greater flexibility in how you manage your organization's users.

This article explains how to create a new user, invite an external guest, and delete a user in your workforce tenant. It also includes information about creating users in an external tenant for Microsoft Entra External ID scenarios.
Types of users
Before you create or invite a new user, take some time to review the types of users, their authentication methods, and their access within your Microsoft Entra workforce tenant. For example, do you need to create an internal guest, an internal user, or an external guest? Does your new user need guest or member privileges?

Users in workforce tenants
A Microsoft Entra workforce tenant has the following user types:

Internal member: These users are most likely full-time employees in your organization.
Internal guest: These users have an account in your tenant, but have guest-level privileges. It's possible they were created within your tenant prior to the availability of B2B collaboration.
External member: These users authenticate using an external account, but have member access to your tenant. These types of users are common in multitenant organizations.
External guest: These users are true guests of your tenant who authenticate using an external method and who have guest-level privileges.
For more information about the differences between internal and external guests and members, see B2B collaboration properties.

Authentication methods vary based on the type of user you create. Internal guests and members have credentials in your Microsoft Entra tenant that can be managed by administrators. These users can also reset their own password. External members authenticate to their home Microsoft Entra tenant and your Microsoft Entra tenant authenticates the user through a federated sign-in with the external member's Microsoft Entra tenant. If external members forget their password, the administrator in their Microsoft Entra tenant can reset their password. External guests set up their own password using the link they receive in email when their account is created.

Reviewing the default user permissions may also help you determine the type of user you need to create. For more information, see Set default user permissions.

Users in external tenants
A Microsoft Entra tenant in an external configuration is used exclusively for Microsoft Entra External ID scenarios. An external tenant can include the following user types:

Internal user: These users authenticate internally, and are typically admins with assigned Microsoft Entra roles in your external tenant.
External user: These users are consumers and business customers of the apps registered in your external tenant. They have a local account with default user privileges and authenticate via a local account or via external identity providers. See how to create a new external user.
External guest: These users sign in with their own external credentials and are typically admins with assigned Microsoft Entra roles in your external tenant.
For more information, see Default user permissions for external tenants.

Prerequisites
The required role of least privilege varies based on the type of user you're adding and if you need to assign Microsoft Entra roles at the same time. Whenever possible you should use the least privileged role.

Task	Role
Create a new user	User Administrator
Invite an external guest	Guest Inviter
Assign Microsoft Entra roles	Privileged Role Administrator
Create a new user
Sign in to the Microsoft Entra admin center as at least a User Administrator.

Browse to Entra ID > Users.
<img width="1388" height="638" alt="image" src="https://github.com/user-attachments/assets/cf0f39fc-2cd8-4321-8eb6-fe87a0f3acd7" />
Select New user > Create new user.
<img width="568" height="314" alt="image" src="https://github.com/user-attachments/assets/3fe58b11-3c21-46d3-9899-02ac92684912" />
Complete the remaining tabs in the New user page.
Basics
The Basics tab contains the core fields required to create a new user. Before you begin, review the guidance on user name properties.

User principal name: Enter a unique username and select a domain from the menu after the @ symbol. Select Domain not listed if you need to create a new domain. For more information, see Add your custom domain name.
Mail nickname: If you need to enter an email nickname that is different from the user principal name you entered, uncheck the Derive from user principal name option, then enter the mail nickname.
Display name: Enter the user's name, such as Chris Green or Chris A. Green
Password: Provide a password for the user to use during their initial sign-in. Uncheck the Auto-generate password option to enter a different password.
Account enabled: This option is checked by default. Uncheck to prevent the new user from being able to sign-in. You can change this setting after the user is created. This setting was called Block sign in in the legacy create user process.

<img width="656" height="539" alt="image" src="https://github.com/user-attachments/assets/0d51eadb-5f3d-43a5-92ee-076eee2b9cd5" />

Either select the Review + create button to create the new user or Next: Properties to complete the next section.

Properties
There are five categories of user properties you can provide. These properties can be added or updated after the user is created. To manage these details, go to Entra ID > Users and select a user to update.

Identity: Enter the user's first and last name. Set the User type as either Member or Guest.
Job information: Add any job-related information, such as the user's job title, department, or manager.
Contact information: Add any relevant contact information for the user.
Parental controls: For organizations like K-12 school districts, the user's age group may need to be provided. Minors are 12 and under, Not adult are 13-18 years old, and Adults are 18 and over. The combination of age group and consent provided by parent options determine the Legal age group classification. The Legal age group classification may limit the user's access and authority.
Settings: Specify the user's global location.
Either select the Review + create button to create the new user or Next: Assignments to complete the next section.

Assignments
You can assign the user to an administrative unit, group, or Microsoft Entra role when the account is created. You can assign the user to up to 20 groups or roles. You can only assign the user to one administrative unit. Assignments can be added after the user is created.

To assign a group to the new user:

Select + Add group.

From the menu that appears, choose up to 20 groups from the list and select the Select button.

Select the Review + create button.
<img width="1203" height="287" alt="image" src="https://github.com/user-attachments/assets/eb40c034-af35-47b5-abd3-479efc43a46a" />
To assign a role to the new user:

Select + Add role.
From the menu that appears, choose up to 20 roles from the list and select the Select button.
Select the Review + create button.
To add an administrative unit to the new user:

Select + Add administrative unit.
From the menu that appears, choose one administrative unit from the list and select the Select button.
Select the Review + create button.
Review and create
The final tab captures several key details from the user creation process. Review the details and select the Create button if everything looks good.
