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

## Current structure

Main files currently include:

- `index.html` — public homepage
- `trust.html` — about, privacy, terms, disclaimer
- `app.html` — main family tree app
- `site.css` — shared public-site styling

Depending on the current build, additional folders such as `data/` or asset folders may also be required.

## Current architecture

This project is intentionally designed to avoid using a central backend for storing private family-tree records.

Current intended storage model:

- the owner's private family tree is stored in the owner's Google Drive
- browser local storage may still be used for limited cached or transitional state
- Google services such as sign-in and Drive access are used for the core private-tree workflow

This helps reduce centralized custody of sensitive family data and lowers ongoing backend/security maintenance burden.

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

This app uses a decentralized, privacy-first sharing model. All sharing is handled securely through Google Drive's native permission system.

1. **Save:** The owner saves the master family tree file to their personal Google Drive.
2. **Invite:** Inside the app, the owner inputs the invited family member’s exact Gmail address.
3. **Assign Roles:** The owner assigns a role to the invitee, such as **Editor** or **Viewer**.
4. **Grant Access:** The app automatically updates the file permissions on Google Drive to grant secure access to that specific Gmail address.
5. **Join:** The invited family member opens the app, signs in with their authorized Google account, and selects the shared tree.
6. **Collaborate:** Depending on the assigned role, the invited member can view the rich family history or collaboratively edit the tree alongside the owner.

### If you were invited by a family member

1. Open the application using the link provided by the owner.
2. Click **Join**.
3. Sign in using the exact Google account (Gmail address) that the owner invited.
4. The app will securely open the family tree file that was shared with you.
5. Explore the family history or help update records according to the permissions you were given.

### In simple terms

- the **owner** signs in and keeps the main private family tree in their own Google Drive
- invited family members use **Join** to open a tree that has already been shared with them
- the app is mainly meant for family and internal use, not broad public sharing
