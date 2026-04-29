---
layout: default
title: Users
has_children: false
parent: Settings
grand_parent: Gally
nav_order: 4
---

The **Users** dashboard, located under the Settings tab, allows you to manage administrative users within Gally. From this page, you can view the list of existing users, create new ones, and assign them specific roles to control their access and permissions. 

### Users Dashboard

<img width="1610" height="655" alt="image" src="https://github.com/user-attachments/assets/89e25e20-7151-4f4c-b281-f10f20c48239" />

The main grid provides a clear overview of all configured users. From this interface, you can:

*   **Create a User:** Click the **Create User** button located at the top right of the screen to add a new admin user.
*   **Filter & Search:** Use the **Filter** menu to easily find specific users, and the **Clear all** button to reset your view.
*   **Manage Users:** The grid lists key information for each user, including their **First name**, **Last name**, **E-mail**, **Role(s)** (for example, Administrator or Contributor), and whether their account is **Enable** (Yes/No). You can click the **Edit** link in the Actions column to modify an existing user's profile.

### Creating a New User

When you click to create a new user, you will be presented with a dedicated form containing the following fields:

| Configuration Field | Default Value | Description |
| :--- | :--- | :--- |
| **Enable** |Yes| A mandatory toggle switch to activate or deactivate the user's account. |
| **First name** || A mandatory text field for the user's given name. |
| **Last name** || A mandatory text field for the user's family name. |
| **E-mail** || A mandatory text field for the contact email address of the user, which is also used for account initialization. |
| **Password** || An optional, masked field for the user's password. |
| **Role(s)** || A mandatory dropdown menu allowing you to assign specific administrative roles to control the user's capabilities within Gally. |

To save the new user configuration, click the **Create** button at the top right of the screen, or use the **Back** link to return to the grid without saving.

#### User Initialization
Once a new user is successfully created, the system automatically sends an email containing an initialization link to their provided email address. The user must use this link to initialize their account and securely gain access to the platform.
