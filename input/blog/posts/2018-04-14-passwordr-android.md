Title: Passwordr for Android
Published: 2018-04-14
Category: news
---
Today, I am announcing [Passwordr for Android](https://github.com/JTMaher2/Passwordr-Android), an Android app for managing passwords with a single master password.
You can log into Passwordr for Android with your Google, Facebook, or Twitter account, along with a master password. This password does not have to be the same as your Google, Facebook, or Twitter password.

Passwordr for Android is open source. Its code can be found [here](https://github.com/JTMaher2/Passwordr-Android).
Passwordr for Android uses the [javax.crypto library](https://docs.oracle.com/javase/7/docs/api/javax/crypto/Cipher.html) to securely encrypt all data. It stores everything in a [Cloud Firestore](https://firebase.google.com/docs/firestore/) database.
Passwordr for Android has been tested to work on devices 6.0 (Marshmallow) or later. If you have any feedback, feel free to open a new issue on Github.