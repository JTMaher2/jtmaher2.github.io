Title: New DNN Password Manager Module
Published: 2023-12-16
Category: news
---
There is now a Stencil.js version of the DNN password manager module that uses cool new things like Typescript and Web Components. It can be found at [https://github.com/JTMaher2/JTM2_PasswordManager/releases/tag/alpha2](https://github.com/JTMaher2/JTM2_PasswordManager/releases/tag/alpha2).
Known Issues:
1) There is some sort of race condition where, sometimes when you update or create a password, it will not get re-drawn on the page. Instead, you must
manually refresh the page to see the updated version.
2) Sometimes, when you insert a new item in an empty grid, it will say "Showing 0 of 1 items."
3) When you load the module, it will let you continue to the index view, even if an invalid master password was provided.

Please let me know what you think about this module, and how it can be improved.