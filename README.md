# Volunteam — Project 1.3

This project implements the complete **Create Event** data flow for the Volunteam app.

## Requirements implemented

- Fetches events from the API whenever the map screen receives focus.
- Saves successful event responses in AsyncStorage and falls back to that cache when the API is unavailable.
- Filters out past or invalid events and displays future events as map markers.
- Fits the map to the available future events and the current user's location.
- Shows the actual number of displayed events in the map footer.
- Provides a two-step create flow: choose a map location, then complete the event form.
- Validates every field and keeps Save disabled until the form is complete.
- Requests camera or photo-library permission before selecting a photo.
- Uploads the selected photo to ImgBB and displays its thumbnail, filename, and size.
- Persists the new event to the API and refreshes the map when returning to it.

## Setup

1. Install dependencies:

   ```bash
   npm install --legacy-peer-deps
   ```

2. Copy `.env.example` to `.env` and replace the sample values:

   ```text
   API_URL=http://YOUR_COMPUTER_IP:3333
   IMGBB_API_KEY=YOUR_IMGBB_API_KEY
   ```

   Create a free image-upload key at <https://api.imgbb.com/>. Never commit the real key.

3. Start the local API in one terminal:

   ```bash
   npm run api
   ```

4. Start Expo in a second terminal. For this Expo SDK version, provide the variables to the process.

   PowerShell:

   ```powershell
   $env:API_URL="http://YOUR_COMPUTER_IP:3333"
   $env:IMGBB_API_KEY="YOUR_IMGBB_API_KEY"
   npx expo start --lan --clear
   ```

## Demo login

- Email: `luigi@carluccio.it`
- Password: `password`

## Verification

```bash
npm run typecheck
npm test
```

For offline-cache testing, first load the map while the API is running. Stop the API and reload the map; the app will show the saved events with an offline banner.
