# CometPark

Crowdsourced parking-lot busyness map for UT Dallas, built in 24 hours at **HackUTD 2024: Ripple Effect**.
**2nd Place, Relatability Track.**

Students tap a lot on the campus map, rate how full it is (1–5), and can attach a photo.
Everyone else sees each lot's average rating, rating count, and recent photos.

**[Live site](https://cometpark.vercel.app)** · **[Demo video](https://www.youtube.com/watch?v=U0EZu1LxALA)** · **[Devpost](https://devpost.com/software/cometpark-yjp3k9)**

## Features

- **Interactive campus map**: SVG map of UTD lots with pan and zoom (`react-zoom-pan-pinch`) and a marker per lot.
- **Permit-color filter**: switch between Green, Gold, and Orange permit lots.
- **Busyness ratings with photos**: a 1–5 star form with optional image upload. Each submission is pinned to
  [Pinata](https://pinata.cloud) (IPFS) with lot, permit color, rating, and timestamp as metadata.
- **Lot sidebar**: average rating, number of ratings, and photo reviews tagged "N hours ago".
  Separate desktop and mobile layouts.
- About and Contact pages.

## How it works

- **Read:** the page's Remix loader fetches all submissions from Pinata, and `remapMarkers` averages them per lot.
- **Write:** submitting a rating runs a Remix action that pins it to Pinata server-side.

## Tech stack

Remix 2 (Vite) · React 18 · TypeScript · Tailwind CSS · Pinata (IPFS) · Axios

## Run locally

Requires Node.js 20+ and a Pinata account.

```bash
npm install
# .env
PINATA_API_KEY=...
PINATA_SECRET_API_KEY=...
npm run dev
```

## Team

| Person | Contributions |
| --- | --- |
| **Kenny Quach** ([@kennnyq](https://github.com/kennnyq)) | Project setup, map and markers, lot coordinates, desktop and mobile sidebars, rating form, Pinata loader/action and rating aggregation, deployment |
| Yash Baruah ([@bornayo7](https://github.com/bornayo7)) | About, Contact, and Bad Parking pages, drop-up nav, Pinata upload form iteration, filter and sort |
| Saarim Syed ([@saarim06](https://github.com/saarim06)) | Time-weighted rating prototype |
| Sanjay Bharathi ([@sanjay-b7](https://github.com/sanjay-b7)) | Redesigned and cleaned up the official UTD parking map used in the app, permit color switcher, About page photos |
