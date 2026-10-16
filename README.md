# Textlink

A responsive, single-file website that turns text into a unique, shareable URL. Open a generated URL on any device and it displays only the submitted text, preserving line breaks.

## How it works

- Each time you create a link, the site generates a fresh random ID, so even identical texts receive different links.
- The text is UTF-8 encoded and stored inside the URL fragment (`#...`). This means there is no database, server-side storage, sign-up, API key, or link-expiry service.
- Link payloads are not sent to the hosting server as part of the HTTP request because they are in the URL fragment.
- A generated link works while the site remains available at the same domain and path. Changing domains or moving the app to a different path can break old links.
- The payload is encoded, **not encrypted**. Anyone with the link can read the text. Do not share passwords, secrets, or sensitive personal information.
- Since content is carried in the URL, very long texts make very long links. The form allows up to 6,000 JavaScript characters.

## Deploy on GitHub Pages (free)

1. Create a new GitHub repository, for example `textlink`.
2. Upload `index.html` to the repository's root. You can include this `README.md` too.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then press **Save**.
6. Once GitHub Pages publishes the site, open the URL shown on that page. Use that URL to create links.

The code uses the current site URL automatically, including a repository subpath such as `https://username.github.io/textlink/`.

## Alternative: Netlify

Create a new site from the folder containing `index.html`, or deploy the folder with Netlify's manual deploy flow. No build step is required.

## Local testing

Open `index.html` in a modern browser to test the generator and viewer locally. Copy/clipboard behavior may be restricted on `file://`; it works best when served over HTTPS after deployment.

## Files

- `index.html` — the entire app (HTML, CSS, and JavaScript); no build tooling or dependencies required.
