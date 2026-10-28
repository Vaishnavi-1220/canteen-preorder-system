# Cloud-Based Canteen Pre-Order (Firebase)

Student -> Select Food -> Place Order -> Firestore (cloud DB) -> Canteen Dashboard -> Order Ready

## Services used
Firebase Authentication, Cloud Firestore (real-time DB), Firebase Hosting (CDN, HTTPS).

## Setup (15 min)
1. console.firebase.google.com -> Add project.
2. Build > Authentication > Get started > enable Email/Password and Google.
3. Build > Firestore Database > Create database (production mode, nearest region e.g. asia-south1).
4. Project settings > Your apps > Web (</>) > copy config into public/firebase-config.js
5. Create the canteen staff account: open /index.html once, "Create account" using the admin email.
6. Put that email in BOTH public/firebase-config.js (ADMIN_EMAILS) and firestore.rules (isAdmin).
7. Install and deploy:
   npm i -g firebase-tools
   firebase login
   firebase init   (choose Hosting + Firestore, use existing project, keep public/ and firestore.rules, do NOT overwrite files)
   firebase deploy
8. Students: https://<project>.web.app   Canteen: https://<project>.web.app/admin.html
9. Admin page > "Load sample menu".

Local test: firebase emulators:start or `npx serve public`.
