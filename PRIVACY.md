# Gnuke — Privacy Policy

_Last updated: 2026-07-16_

Gnuke is a personal Chrome extension that unsubscribes from a sender and trashes their
mail from inside Gmail. It runs entirely in your browser. There is no Gnuke server.

## What it accesses

- **Your Gmail**, via the Google Gmail API using the `gmail.modify` scope. Gnuke lists a
  sender's messages, moves them to Trash, and (for undo) records their message IDs. It
  can also send an unsubscribe email from your address when a sender's List-Unsubscribe
  header requires it. It never reads message bodies beyond the headers needed to find an
  unsubscribe link, and it never deletes permanently.
- **Sender unsubscribe endpoints.** When you nuke a sender, Gnuke may POST to that
  sender's one-click unsubscribe URL (RFC 8058), exactly as your mail client would.
- **Domain favicons.** To label the notification, Gnuke requests a favicon from Google's
  public favicon service, passing only the sender's domain.

## What it stores

- Job records (sender address, affected message IDs, counts) in Chrome's local
  `storage`, solely to power **Undo**. These stay on your device and are cleared
  automatically after a short retention window.
- Your Google OAuth token is managed by Chrome's `identity` API and cached by the
  browser. Gnuke does not copy or transmit it anywhere.

## What it does NOT do

- No analytics, tracking, ads, or telemetry.
- No data is sent to the developer or to any third party other than Google (Gmail API,
  favicon service) and the sender's own unsubscribe endpoint.
- No data is sold or shared.

## Contact

Questions: pcarrau@gmail.com
