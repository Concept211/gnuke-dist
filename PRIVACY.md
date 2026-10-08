# Gnuke — Privacy Policy

_Last updated: 2026-10-08_

Gnuke is a personal Chrome extension that unsubscribes from a sender and trashes their
mail from inside Gmail. It runs entirely in your browser. There is no Gnuke server.

## What it accesses

- **Your Gmail**, via the Google Gmail API using the `gmail.modify` scope. Gnuke lists a
  sender's messages, moves them to Trash, and (for undo) records their message IDs. It
  can also send an unsubscribe email from your address when a sender's List-Unsubscribe
  header requires it. It never reads message bodies beyond what it needs to find an
  unsubscribe link, and it never deletes permanently.
- **Your Gmail filters**, via the `gmail.settings.basic` scope, only when you choose
  **Block**. Gnuke creates one filter that sends that sender's future mail to Trash.
- **A private Gnuke folder in your Google Drive**, via the `drive.appdata` scope, only if
  you turn on **Sync across computers**. See below.
- **Sender unsubscribe endpoints.** When you nuke a sender, Gnuke may POST to that
  sender's one-click unsubscribe URL (RFC 8058), exactly as your mail client would.
- **Domain favicons.** To show a sender's logo, Gnuke requests a favicon from Google's
  public favicon service, passing only the sender's domain.

## What it stores

- On your computer, in Chrome's local `storage`: the list of senders you nuked or
  blocked, with counts and dates, and the message IDs Undo needs. Undo records are
  deleted after 30 days, when Gmail empties its Trash.
- Your "keep" choices (for example, keep starred mail) in Chrome's `storage.sync`, so
  they follow your Chrome profile if you use Chrome sync.
- Your Google OAuth token is managed by Chrome's `identity` API and cached by the
  browser. Gnuke does not copy or transmit it anywhere.

## Sync across computers (optional, off by default)

If you turn it on from the Gnuke popup, Google asks you once to let Gnuke use its own
app data folder in your Google Drive. Gnuke keeps one file there holding the same list
and Undo records described above, so your other computers signed in to that Gmail
account can show them. The folder is hidden from your Drive and only Gnuke can open it.
Gnuke cannot see any of your other Drive files.

The file goes straight between your browser and Google. It never passes through a Gnuke
server, because there isn't one. **Turn off**, on any computer, erases the file's contents
and stops sync on all of them; each computer keeps only its own local list. You can also remove
Gnuke's access at any time at <https://myaccount.google.com/permissions>.

## What it does NOT do

- No analytics, tracking, ads, or telemetry.
- No data is sent to the developer or to any third party other than Google (Gmail API,
  Drive app data folder if you turn on sync, favicon service) and the sender's own
  unsubscribe endpoint.
- No data is sold or shared.

## Contact

Questions: pcarrau@gmail.com
