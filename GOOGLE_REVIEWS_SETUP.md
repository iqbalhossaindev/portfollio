# Google Live Reviews Setup for GitHub Pages

This version keeps the website design unchanged and only improves Google live rating/review loading.

## Required Google Cloud settings

### 1. Enable APIs
Enable these in Google Cloud Console:

- Maps JavaScript API
- Places API

### 2. API key application restriction
Use **Websites** restriction. Add all domains where the site can open:

```text
https://theiqbal.com/*
https://www.theiqbal.com/*
```

If you test on GitHub Pages before the custom domain is active, also add your exact GitHub Pages URL, for example:

```text
https://YOUR-GITHUB-USERNAME.github.io/*
https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPO-NAME/*
```

### 3. API restrictions
Restrict the key to:

- Maps JavaScript API
- Places API

### 4. Billing
Google Maps Platform billing must be enabled.

## If it still says syncing

Open your website in Chrome, then open:

```text
Menu > More tools > Developer tools > Console
```

Check for errors like:

- `RefererNotAllowedMapError` = add the current domain to Website restrictions
- `ApiNotActivatedMapError` = enable Maps JavaScript API / Places API
- `BillingNotEnabledMapError` = enable billing
- `Google sync failed: NOT_FOUND` = Place ID is wrong
- `Google sync failed: REQUEST_DENIED` = API key or API permission problem

## Note
Google Places usually returns only a small number of Google reviews, not every review.
