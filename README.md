# Mr Wael English Gradebook

A separate gradebook for Mr Wael's English classes.

## Features

- G12A, G12B, G12C, and G12D English classes
- Student lists, daily participation, attendance, and homework marks
- Per-category and overall averages, weekly reports, CSV export, and print-friendly PDFs
- Egyptian American Diploma admission calculator
- Teacher sign-in with Firebase Authentication
- Private Firestore sync between devices

## Average calculation

- Participation uses the average recorded score out of 15.
- Attendance: Present = 10, Late = 5, Absent = 0.
- Homework: Completed = 10, Late = 5, Missing = 0.
- Overall average converts each available category average to a percentage, then takes their mean.

## Firebase project

This site uses the separate Firebase project **mr-wael-english**. The public web app configuration is in index.html; it contains no service-account credentials. Authentication uses Email/Password. Create the teacher account in Firebase Console → Authentication → Users → Add user; the site intentionally has no public sign-up form.

Cloud Firestore is configured in the Doha region (me-central1) in production mode. The rules in firestore.rules restrict student and mark records to the signed-in user’s own UID path. Rules are published in the project. To publish later updates, use the Firebase CLI command: `npx -y firebase-tools@latest deploy --only firestore:rules --project mr-wael-english`.

The GitHub Pages domain (beshoy1402.github.io) must be listed under Firebase Authentication → Settings → Authorized domains.

## Existing browser data

The app keeps the original waelEnglishGradebookV1 local-storage data intact. On the first teacher sign-in, it asks before uploading that browser’s students and marks. It also keeps a per-user local backup and offers a Settings option to merge or download that backup later. Declining the upload keeps the app in local-only mode until the teacher chooses to upload from Settings.

## Deploy

The website is a single static index.html and can remain on GitHub Pages (Settings → Pages → Deploy from a branch → main → root). Serve it over HTTPS or a local web server; browser modules are not supported when opening the file directly as file://.
