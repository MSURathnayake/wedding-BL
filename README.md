# Nil Manel wedding invitation (React + Vite)

    npm install
    npm run dev      # local preview
    npm run build    # production build in dist/ (deploy to Vercel as a Vite project)

- Names, date, venue, timeline and all texts, in English and Sinhala: `src/config.js`
- Song and couple picture: `public/assets/` (song.mp3, couple.jpg)
- RSVP replies go to a Google Sheet and guest photos to a Drive folder through `apps-script/Code.gs`.
  Follow the steps at the top of that file, then paste the web-app URL into `appsScriptUrl` in `src/config.js`.
  Until then, RSVP replies stay in the browser and guest photos only show on that device until the page is reloaded.

## Pre-shoot gallery
Copy your photos into `public/assets/preshoot/` (JPG, around 1600px wide is plenty) and list the file names in `PRESHOOT` in `src/config.js`.

## RSVP in Excel
Replies land in the "RSVP" tab of your Google Sheet and a "Summary" tab counts adults, children and total guests.
Use File > Download > Microsoft Excel (.xlsx) in Google Sheets whenever you need the Excel file.

## Page order
Couple photo, invitation card (names and date), the couple, the families, pre-shoot gallery, countdown, venue, day flow, RSVP, wishes, guest photos.
Texts for the couple and family sections are samples in `src/config.js` (`coupleSec`, `familySec`, English and Sinhala).

## Pre-shoot gallery (sliding 3-card carousel)
The photos in `public/assets/preshoot/` (01.jpg to 07.jpg) are sample pictures. Replace them with your own and keep the names in `PRESHOOT` in `src/config.js`.

## Guest photo upload opens on the wedding day
`photosOpenISO` in `src/config.js` sets the moment it opens (default: midnight at the start of the wedding day, Sri Lanka time).
Before that the section shows a locked card; it unlocks by itself, even on a page that is already open, and stays open afterwards.
To preview the open state early, add `?unlock` to the page address.
