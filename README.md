# Shubham & Pooja — Wedding Invitation Website

A single-page wedding invitation with an animated opening envelope, couple
reveal, scratch-card countdown, event schedule, photo gallery, venue map,
photo-upload QR, and RSVP.

## File structure

```
index.html              the page itself
assets/
  css/styles.css        all styling
  js/script.js          all interactivity (envelope, animations, countdown,
                         scratch card, QR generator, scroll hint)
  images/                5 photos/illustrations, already compressed
```

## Before you publish — things to update

Open `assets/js/script.js` and search for these three lines near the bottom
(under the "Venue map + photo-upload QR" comment):

```js
var VENUE_QUERY = "Venue To Be Announced";
var DRIVE_UPLOAD_LINK = "https://drive.google.com/drive/folders/15JQ5UsofHH34XoWEHL8_NxVIehA4Clpk";
```

- Replace `VENUE_QUERY` with your real venue name/address — the map and
  the "open in Google Maps" link both use this automatically.
- Replace `DRIVE_UPLOAD_LINK` with your real shared Google Drive folder —
  the QR code regenerates itself from this value, no image editing needed.

Also check `index.html` for the schedule and countdown dates ("13th Feb
2027", "14th Feb 2027", "To Be Announced" venue/time fields) and update
once your dates are locked in.

## Hosting on GitHub Pages

1. Create a new GitHub repository (public, since GitHub Pages on the free
   tier only serves public repos).
2. Push the contents of this folder to the repository root — `index.html`
   should sit directly in the repo root, not inside a subfolder.
3. In the repo, go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**, pick your default
   branch (usually `main`) and the `/ (root)` folder, then **Save**.
5. GitHub will give you a live URL, typically:
   `https://<your-username>.github.io/<repo-name>/`
   It can take a minute or two to go live the first time.

All paths in this site are relative (no leading `/`), so it will work
correctly whether it's served from the repo root or from a subpath like
`/<repo-name>/` — no changes needed either way.

## A note on load time with many guests

Static sites like this are served from a CDN, which is built specifically
to handle many simultaneous visitors — 100 guests clicking the link at the
same moment causes no meaningful slowdown for anyone. The only thing that
affects how fast it opens for an individual guest is their own connection
speed and the file size, which is why the images here are already resized
and compressed for the site (roughly 700KB total, down from a much larger
original).
