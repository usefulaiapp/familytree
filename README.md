# Family Tree
A family tree web app for family and internal use.

## Project purpose

This project is designed to help families organize member relationships, preserve family memory, and maintain a private family tree in a more owner-controlled way.

The intended direction is:

- privacy conscious
- family/internal use first
- free to use in principle
- no central backend for private tree storage
- owner-controlled private storage
- the owner's private tree is intended to be stored in the owner's own Google Drive
- invited family members may access the tree through approved sharing flows
- export to image / PDF is supported
- private family-tree content should mainly be for the owner and invited family members


## Current architecture

This project is intentionally designed to avoid using a central backend for storing private family-tree records.

Current intended storage model:

- the owner's private family tree is stored in the owner's Google Drive
- browser local storage may still be used for limited cached or transitional state
- Google services such as sign-in and Drive access are used for the core private-tree workflow

This helps reduce centralized custody of sensitive family data and lowers ongoing backend/security maintenance burden.

## Features and Navigation

The app currently has four main views in the navigation:

- **Family Tree:** The main visual view of the tree. You can browse family members and relationships, click a person to view their details, edit information if you have permission, and export the tree as a PNG image or PDF.
- **Community:** A place to add and organize external links that help family members stay connected.
- **Member Table:** A spreadsheet-style view of all family members. This view is excellent for searching for specific people, sorting by generation or name, making bulk edits quickly, and exporting the family data to a CSV or Excel.
- **Members Admin:** The member-management area for the tree owner. Here, the owner can add invited relatives by Gmail address, manage viewing or editing roles, and use the invitation/share flow for access.

## How to use

This app currently has two main ways to start:

- **Sign In** — For the owner who creates and manages the primary family tree.
- **Join** — For family members who were invited to view or contribute to an existing tree.

### If you are the owner

1. Open the application and click **Sign in** using your Google account.
2. Create a new family tree or reopen your previously saved tree.
3. Add family members, relationships, and basic biographical details.
4. Click **Save** to securely sync the tree data directly to your personal Google Drive.
5. Return at any time, log in, and the app will automatically fetch your saved tree.
6. If needed, export the family tree visual as an Image or PDF for physical printing.

### How sharing works

This app currently uses Google Drive as the main sharing path for private family-tree access.

1. **Save:** The owner saves the main family-tree file to their own Google Drive.
2. **Manage access:** In the **Members Admin / 成員管理** page, a user with **Owner** or **Editor** access can enter the invited family member’s Gmail address.
3. **Assign roles:** The invited person can be assigned as **Editor** or **Viewer**.
4. **Share through Drive:** The app then uses Google Drive permissions to share the relevant tree file with that Gmail account.
5. **Join:** The invited family member opens the app, signs in with the invited Google account, and opens the shared tree.
6. **Collaborate:** Depending on the assigned role, the invited person can either view the tree or help edit it.

In simple terms, the current app has three roles: **Owner**, **Editor**, and **Viewer**. **Owner** and **Editor** can manage sharing in the **Members Admin / 成員管理** page, while invited people are added by Gmail address and assigned as **Editor** or **Viewer**. 

### If you were invited by a family member

1. Open the app. You may do this from an invitation link, or by opening the app directly if the tree has already been shared with your account.
2. Click **Join**, or use the shared-file opening flow in the app.
3. Sign in with the exact Google account (Gmail address) that was invited.
4. Open the shared family-tree file. In the current app flow, this may involve selecting the shared `private_tree.json` file through the Google Picker.
5. View the tree or help update it according to the access level you were given.

### In simple terms

- the **owner** signs in and keeps the main private family tree in their own Google Drive
- invited family members use **Join** to open a tree that has already been shared with them
- the app is mainly meant for family and internal use, not broad public sharing

## Core workflows: edit, save, undo, and reload

This app is designed so that the main family-tree file is stored in Google Drive rather than in a central project database.

### 1. Editing and saving

- **Edit a person:** In the **Family Tree** view or **Member Table** view, open a person’s details and edit their information.
- **Changes on screen:** When you save an edit or add a new relative, the change is immediately applied in the app.
- **Save behavior:** In the current app, these changes are also pushed through the app’s save flow right away, rather than waiting for a separate final save button.
- **Drive storage:** When Google Drive access is available, the app attempts to save the updated tree file to Google Drive. If Google APIs or tokens are not ready, the app can still keep the updated state locally first and sync later.

### 2. Undo and redo

- The top header includes **Undo** and **Redo** buttons.
- These are the main tools for stepping backward or forward through recent edits inside the current session.

### 3. Reload from Drive

- The top header also includes **Reload from Drive** when a Drive-backed tree is open.
- This button reloads the current tree file from Google Drive.
- It is useful when you want to refresh the tree from the saved Drive version, including after another collaborator has made changes.
- It can also help you discard unsaved local state by reloading the stored Drive version of the tree.
- 
## Important notes

- This is an independently maintained project and some parts are still evolving.
- Some features or storage behavior may remain transitional while the project is being refined.
- When you create or share a copy of the family tree, please use care and take responsibility for how that copy is stored, shared, or forwarded.
- Please take extra care when handling personal data, photos, or stories relating to living relatives.
- Private family-tree use is mainly intended for the owner and invited family members.

## Development note

This repository is public so the code can be reviewed and inspected. The project is designed to reduce centralized storage of private family-tree data by relying mainly on the owner’s own Google Drive for private tree storage.

To run the app locally, do not open the HTML files directly from disk. Serve the project from a local web server instead. You will also need to create your own Google Cloud project, generate your own OAuth credentials, add them to the code, and configure the allowed JavaScript origins in Google Cloud Console so they match your local server address.

## Status

This repository is currently in active testing and refinement.
