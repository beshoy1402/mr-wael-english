# Mr Wael English Gradebook

A separate gradebook for Mr Wael's English classes.

## Classes
- G12A — English
- G12B — English
- G12C — English
- G12D — English

## Features
- Add students by class
- Daily participation, attendance, and homework records
- Per-category and overall student averages
- CSV reports that open in Excel
- Print-friendly reports (browser Save as PDF)
- Mobile-friendly layout

## Average calculation
- Participation: average of recorded participation scores (0–100).
- Attendance: Present = 100, Late = 50, Absent = 0.
- Homework: Completed = 100, Late = 50, Missing = 0.
- Overall average: arithmetic mean of available category averages. Categories with no records are excluded, not treated as zero.

## Storage status
This starter version stores data in the current browser using localStorage. Data does not sync between devices and may be lost if browser site data is cleared. Firebase Authentication and Firestore are intentionally not configured yet. Add the Firebase web app configuration after creating the separate Firebase project.

## Deploy
Open index.html locally, or enable GitHub Pages in Settings → Pages → Deploy from a branch → main → root.
