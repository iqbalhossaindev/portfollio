# Google Live Reviews Setup for GitHub Pages

This repo is still a static website. No backend/server was added.

## What was fixed

- Removed the duplicate Google Maps API script setup.
- Added one clean Google Business config block in `index.html`.
- Added a safer Google Maps JavaScript API loader.
- Added clear error messages instead of staying stuck on `Syncing with Google…`.
- Kept the existing website design unchanged.

## Where to edit

Open `index.html` and find:

```js
const GOOGLE_BUSINESS_CONFIG = {
  apiKey: 'YOUR_API_KEY',
  placeId: 'YOUR_PLACE_ID',
  syncIntervalMs: 30 * 60 * 1000,
  requestTimeoutMs: 12000
};
```

Use your restricted browser API key and your Google Place ID.

## Google Cloud requirements

Enable these APIs in the same Google Cloud project:

1. Maps JavaScript API
2. Places API

Billing must be enabled.

## API key restrictions

Use **Application restrictions → Websites** and add:

```txt
https://theiqbal.com/*
https://www.theiqbal.com/*
```

For GitHub Pages testing, also add your GitHub Pages URL, for example:

```txt
https://YOUR-GITHUB-USERNAME.github.io/*
```

Use **API restrictions → Restrict key** and allow only:

```txt
Maps JavaScript API
Places API
```

## Important notes

- Static websites can show live Google rating and up to 5 Google reviews using the Google Maps JavaScript API Places Library.
- If it still shows an error, open the browser console and check the exact Google error message.
- Common problems: wrong Place ID, billing disabled, API not enabled, or website domain not added to key restrictions.
