# Firebase setup

Firestore is the shared source of truth, so every device sees the same
bookings. In the Firebase console for project `dandiya-93c98`:

1. Enable **Authentication > Sign-in method > Email/Password**.
2. Add the user `dandiya@gmail.com` using the intended administrator password.
3. In **Firestore Database > Rules**, deploy the contents of `firestore.rules`.

The rules let visitors create bookings, while only that authenticated Firebase
account can edit or delete them. The page reports save/delete failures instead
of incorrectly reporting success.
