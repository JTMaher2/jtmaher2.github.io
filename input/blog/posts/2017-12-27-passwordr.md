Title: Passwordr
Published: 2017-12-27
Category: news
---
Today, I am announcing [Passwordr](https://passwordr-3917b.firebaseapp.com), a website for managing passwords with a single master password.
You can log into Passwordr with your Google account. After you log in, you will be prompted for a master password. This password does not have to be the same as your Google password.

Passwordr is open source. Its code can be found [here](https://github.com/jtmaher2/passwordr-site).
Passwordr uses the [Web Cryptography API](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/) to securely encrypt all data. It stores everything in a [Cloud Firestore](https://firebase.google.com/docs/firestore/) database.
Passwordr has been tested to work in Chrome, Edge, and Firefox. If you have any feedback, feel free to open a new issue on Github.