## Table of Contents

- [Tasks](#Tasks)
  - [Lab 1 - Hello world Mason](#1-hello-world-Mason)
  - [Lab 2 - Nobody runs away from the military commissariat!](#2-Nobody-runs-away-from-the-military-commissariat)
  - [Lab 3 - Clever thoughts haunted him, but he did not write them down](#3-Clever-thoughts-haunted-him,-but-he-did-not-write-them-down)
  - [Lab 4 - Yet another feed blocked](#4-yet-another-feed-blocked)

## VCS
All work have to be performed inside a **git repository**. Each application can be developed in the separate branch, or in separate folder within one branch.

## Versioning
Every application should be 'equipped' with **basic versioning** implementation. Resulting application package should have proper `versionCode` and `versionName` (make sure to find out what are the differences between these values) according to SEMVER (Semantic Versioning). Version name should contain major, minor and patch version numbers. A version tracking should be performed by utilizing git tag feature. Each tag should be formatted as `MAJOR.MINOR` (e.g. 1.3), PATCH number represents a number of commits performed after latest release (latest tag) (all numbers are obtained via git shell commands).

## App signing
Resulting **release** APK should be signed with a personal certificate automatically during build. You have to understand why this action is important.


# Tasks

## 1. Hello world Mason

1. Create 'Calculator' app.
2. Application should have two modes: basic and scientific (see, well, any calculator for reference).
3. Modes can be toggled via interface button.
4. Each set of functions (numbers + basic functions and scientific functions) should be in separate fragments.
5. For landscape device orientation app should always be in scientific mode.
6. Create a 'demo' build flavor with only basic functions available for both screen orientations. User should be able to have both 'demo' and 'full' versions on device at the same time.

**Topics to cover:** android versions, gradle, git, permissions, google play app requirements, build variants, product flavors,  activities, fragments, views, controls, basic app architecture.

### Further reading:
- [Android app versioning](https://developer.android.com/studio/publish/versioning)
- [Tags in git](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
- [Git and gradle integration example](https://gist.github.com/erics/1c6e333b70508be01c884b7e54d8cfbf)
- [App signing](https://developer.android.com/studio/publish/app-signing)
- [Android Activities](https://developer.android.com/guide/components/activities/intro-activities)
- [Activity Lifecycle](https://developer.android.com/guide/components/activities/activity-lifecycle) / [Extended diagram](https://github.com/xxv/android-lifecycle)
- [Activity Fragments](https://developer.android.com/guide/components/fragments)
- [Layouts in Android](https://developer.android.com/guide/topics/ui/declaring-layout)
- [Android Architecture components](https://developer.android.com/topic/libraries/architecture) - a good way to implement MVVM and structure your app
   - [LiveData](https://developer.android.com/topic/libraries/architecture/livedata)
   - [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel)
- [Build variants](https://developer.android.com/studio/build/build-variants)


## 2. 'Nobody runs away from the military commissariat!'
A 'Tabata timer' application. ([Reference](https://play.google.com/store/apps/details?id=com.evgeniysharafan.tabatatimer&hl=ru))

1. A user can create different timer sequences and switch between them (use GSON or SQLite for data storage).
2. Home page - a list of sequences
   - CRUD for them
3. Sequence properties:
   - title
   - colour
4. Timer page:
   - remaining time of the current phase
   - list of upcoming phases
   - controls to pause, go back and forth through the sequence or to leave this page and cancel the timer
5. Edit page:
   - tweak duration of each phase (workout, rest, warm-up, cooldown)
   - change number of phase repetitions and rest periods between them
   - define sequence properties
6. While running, each phase switch should trigger a sound to warn user.
7. The timer should not stop when user leaves the app (see Services).
8. Settings page (implemented with AndroidX Preference library):
   - day / night theme
   - change app font size (without app reload)
   - a button to clear all stored data
   - switch app locale (a choice between two languages at least).
9. Application should have a splash screen with app name or artwork to entertain the user while the app is being loaded.

**Topics to cover:** data storage, app architecture, styling, services, preferences.

### Further reading:
- [Permissions](https://developer.android.com/guide/topics/permissions/overview)
- [Room Database](https://developer.android.com/training/data-storage/room) / [Data storage](https://developer.android.com/training/data-storage/app-specific)
- [Services](https://developer.android.com/guide/components/services)
- [Preferences](https://developer.android.com/guide/topics/ui/settings)
- [Style and theme](https://developer.android.com/guide/topics/ui/look-and-feel/themes)

## 3. Clever thoughts haunted him, but he did not write them down

1. Create 'Notes' application. (see Google Keep for reference).
2. App should show a list or a grid of created notes depending on screen orientation (list for portrait and grid for landscape).
3. Each note should consist of title, body and tag list. Title may not be empty. If user left it out empty, a current date should be used instead. Tag list may be empty.
4. List or grid may be sorted by date or note title. User can also browse notes by particular tag.
5. Any data storage option may be used. Note list should be persisted across app launches.

Try to use components from google material design. Take a look at android app architecture guides across internet to avoid common pitfalls.

**Topics to cover:** activity lifecycle, fragment lifecycle, data storage, app architecture.

### Further reading:
- [Firbase for Android](https://firebase.google.com/docs/android/setup)
- [Firestore](https://firebase.google.com/docs/firestore)
- [Fresco](https://frescolib.org/docs/index.html) / [Picasso](https://square.github.io/picasso/) - libraries to work with images
- [Volley overview](https://developer.android.com/training/volley) / [OkHTTP](https://square.github.io/okhttp/) - libraries for network operations

## 4. Yet another feed blocked

1. Create RSS reader application (see Flipboard for reference).
2. On first launch app asks user to type in RSS feed URL. This can be changed later.
3. RSS entities are displayed within list view. EAch entity should contain date, title, preview of content and an image (if provided by feed source).
4. When user taps on list item, a WebView with full entity should be displayed.
5. 10 recently fetched news should be cached and available to user even if no network is available.
6. App should track and display network state (icon, snackbar, etc). User should be aware when app goes offline and online.
7. All network operations should not block user interface and should have loading indicator if necessary.

**Topics to cover:** images, network, storage, network, async operations, advanced UI practices.
