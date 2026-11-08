# Gather

A private, single-group chat app with account registration, role management, file sharing, and profile avatars.

## Run locally

1. Install Python 3.10 or newer.
2. Install the dependency: `python -m pip install -r requirements.txt`
3. Start the server: `python main.py`
4. Open `http://127.0.0.1:5000` and create an account. The first account becomes the owner.

Set `MESSGRAM_SECRET_KEY` to a long, random value before deploying. The default key is only for local development. The SQLite database and uploaded files are stored in the `instance` folder.

## Standalone HTML export

Open `index.html` directly for a local-only demo. Its messages, attachments, and avatar are stored in that browser's IndexedDB and remain after reload. This storage is not the browser's visited-page history, is not shared with other browsers/devices, and can be removed when browser site data is cleared. Use the Flask app and its SQLite database for shared group chat.

## Group features

- Members can sign up, log in, change their avatar, and share text and supported file attachments.
- The owner can promote members to moderator, restore them to member, and ban or unban accounts.
- Chat updates automatically every few seconds. Files are private to signed-in group members and limited to 16 MB.
- Appearance preferences include light/dark mode and violet, blue, teal, coral, and amber accent colors. They are saved in the current browser.

Run the app tests with `python -m unittest discover -s tests`.
