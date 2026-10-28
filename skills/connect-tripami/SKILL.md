---
name: connect-tripami
description: Connect or troubleshoot Tripami OAuth, account identity, expired access or missing permissions. Use for connection setup and recovery, not routine trip briefings or itinerary edits.
---

Use the Tripami connection supplied by this plugin. The server is https://api.tripami.io/mcp and uses OAuth with automatic client registration. Use the platform connection flow; have the user sign in with the same Tripami account used in the mobile app and approve the displayed access. Never ask for passwords, access tokens or client secrets in chat.

If tools are available, first call tripami.connection_status to report the account display name and granted permissions. The fingerprint distinguishes accounts without exposing a user ID; it is not an email or proof of mobile-account identity. Then verify access with tripami.list_trips. An authenticated status checks now, not future token expiry. Successful tool discovery alone does not verify account access. Do not create a test trip or change a real itinerary for setup. If no trips exist, report that accurately and ask whether the user wants to create one.

When there are similarly named trips, present their dates and destinations and ask which one to use. An empty list can also mean the user connected a different Tripami account; let them check or reconnect rather than creating duplicates.

For unavailable tools or expired access, use the platform's refresh/reconnect controls. No authentication bypass or fallback identity is allowed. The website, support and privacy pages are https://tripami.io, https://tripami.io/support/ and https://tripami.io/privacy/.

Distinguish authentication errors (use the platform reconnect flow), insufficient_scope (request only the needed permissions), trip_not_found (check account and membership), and a successful empty list (no accessible matching trips). Tool discovery is not an account check. Never claim that an unavailable or ungranted category contains no records.
