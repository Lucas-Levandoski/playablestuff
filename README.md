# PlayableStuff website

Static site for the Google Play developer profile and The Castle: Circular TD listing.

| File | Used for in Play Console |
|---|---|
| `index.html` | **Website** on the developer page and store listing |
| `privacy.html` (+ `privacy-pt.html`) | **Privacy policy URL** (App content → Privacy policy) |
| `app-ads.txt` | Ad network verification (must be at the domain root) |
| `404.html` | Not-found page |

## Before publishing
1. Replace every `CONTACT_EMAIL` with the support email you use in Play Console:
   `sed -i 's/CONTACT_EMAIL/you@example.com/g' *.html`
2. Paste the real lines from the LevelPlay dashboard into `app-ads.txt`.
3. Once the game is live, check the Google Play button link in `index.html`.

## Hosting (GitHub Pages, free)
`app-ads.txt` only works at the **root** of a domain, so use either:
- a user site: repo named `<username>.github.io` → `https://<username>.github.io/`, or
- any repo plus a custom domain (e.g. `playablestuff.com`; add a `CNAME` file with the domain).

Push these files to the repo root, enable Settings → Pages → Deploy from branch `main` / root, wait a minute, then open `/privacy.html` and `/app-ads.txt` to confirm they load.

Then in the game: set `privacyPolicyUrl` on `Assets/_Game/Content/Account/AdRewards.asset` to the hosted `privacy.html` URL.
