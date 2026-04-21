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

This is an independently maintained project. Parts of the code, structure, or wording may be drafted or refined with AI assistance.

## Status

This repository is currently in active testing and refinement.
