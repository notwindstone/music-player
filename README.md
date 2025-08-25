local-first app based on the webview

## tech stack

### desktop

- Wails
- TypeScript
- Svelte 5
- UnoCSS with presetWind3
- TypeBox
- https://github.com/kitschpatrol/svelte-tweakpane-ui

### mobile

Probably Jetpack Compose with the Kotlin, but... do we really need it? There is plenty of options there, maybe we can either fork some app or abandon an idea for making a mobile app

## plan

### yt-dlp

<details>

Add a way to download music from the YouTube

**Current implementation idea:** tbd

**Results:** tbd

</details>

### music formats and conversion

<details>

Try to support as many file formats as possible, like FLAC, WAV, M4A, MP3, etc.

Also implement a functionality to convert music formats locally

**Current implementation idea:** tbd

**Results:** tbd

</details>

### extensions

<details>

JS code can be dynamically fetched from somewhere and then executed with the `new Function(JS_CODE_AS_STRING)`. That is a key idea for implementing user plugin system. Plugins can communicate with the host app and each other through `window.postMessage`, and the variables can be shared using the `window` object. JS code can also handle applying CSS styles, adding DOM nodes, etc. Any fully CSR JS framework will work perfectly.

The biggest concern here is the security. Even if the `new Function` can't access local variables and runs in a different scope (unlike `eval`), it still has a lot (and I mean really a lot) of other security issues. Executing an unknown code (especially with the access to the filesystem) is a **horrible** thing

Unfortunately, if VSCode, Obsidian, Vencord and other apps can't implement a secure user plugin system, I won't be able to do it too. It's either functionality or security, not both

**Current implementation idea:** An extension repository that hosts moderated plugin versions. Moderation will require only a source code and, if differs from usual, build manual. Plugins will run only once on application load, without blocking the main thread

**Results:** custom elements, insane UI customization, etc.

</details>

## design

tbd

## testing

- vitest
- playwright
