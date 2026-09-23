# Connect Firebase Firestore

The app already loads the Firebase Web SDK and saves bookings in the `bookings` Firestore collection. It uses local browser storage until the Firebase configuration in `index.html` is completed.

## 1. Create or select a Firebase project

1. Open [Firebase Console](https://console.firebase.google.com/).
2. Select **Add project**, or open an existing project.
3. On the project overview page, click the **Web** (`</>`) icon under **Get started by adding Firebase to your app**. Give the web app a name and register it.

## 2. Find and paste the configuration

1. In Firebase Console, click the gear next to **Project Overview** and choose **Project settings**.
2. Scroll to **Your apps**, select the web app, then find **SDK setup and configuration** and choose **Config**.
3. Copy each matching value from `firebaseConfig` into the empty `FIREBASE_CONFIG` block in [index.html](index.html). Keep the quote marks and property names.
4. Save the file and reload the site.

Firebase web configuration values identify the app; Firestore Security Rules—not hiding this browser-visible configuration—protect the database.

## 3. Enable Firestore

1. In Firebase Console, go to **Build > Firestore Database**.
2. Click **Create database**, select a location, and complete the setup.
3. During initial development, choose a temporary test configuration only if appropriate. Before sharing the site, replace it with restrictive rules.

This app lets visitors create bookings and reads all bookings to show which passes are taken. Its existing admin sign-in is only a user-interface check, so it is not sufficient protection for a public production database. For a production launch, add Firebase Authentication for every booking user and write rules that allow only the intended users and fields.

## Optional: enable the existing admin login

The page also includes Firebase Authentication for the admin-login dialog. To use it, go to **Build > Authentication > Sign-in method**, enable **Email/Password**, then add the matching admin user under **Users**. Update `ADMIN_EMAIL` in `index.html` to that user’s email address.

## References

- [Firebase web setup](https://firebase.google.com/docs/web/setup)
- [Cloud Firestore Security Rules](https://firebase.google.com/docs/firestore/security/get-started)
