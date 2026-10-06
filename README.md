# finwatch-signin

Static forwarding pages for FinWatch, a household app that runs on a home network. OneDrive and Google do not accept
a home-network address as an OAuth return address, so FinWatch names these pages instead:

- `finwatch/onedrive/` passes a OneDrive sign-in result (code and state, or an error) to FinWatch's backup screen.
- `finwatch/google/` does the same for Google Drive.

Each page forwards only to one fixed address, stores nothing, sends no referrer and removes the code from its own
address and history before moving on. Microsoft returns the code in the address's fragment, which never reaches this
site's server. A code is useless on its own: FinWatch holds the matching PKCE key (and, for Google, the client secret)
and exchanges it on its own server.

Published with GitHub Pages from the `main` branch.
