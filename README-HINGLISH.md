# Habit Tracker — Android project

This project wraps the current `Habit_Tracker_Updated.html` in an Android WebView so it can be built as an installable APK. The HTML asset includes My Habits, Pixel Dino Daily Tasks & Thoughts, Dino Growth/Rewards, XP/coins, Weekly Report, Graphic Data, Achievement Badges, calendar, and dark mode.

## Build an APK with Android Studio

1. Install Android Studio on a computer and open this `HabitTrackerAndroid` folder (the folder containing `settings.gradle`).
2. Let Gradle sync. If prompted, install Android SDK Platform 35 and a compatible JDK (JDK 17).
3. Choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
4. After the build finishes, use the notification's **locate** link. The debug APK is normally at `app/build/outputs/apk/debug/app-debug.apk`.
5. Copy the APK to your Android phone and install it. Android may ask you to allow installs from that file manager/browser.

## Build through GitHub Actions (optional)

Push this folder to a GitHub repository. The workflow at `.github/workflows/build-apk.yml` builds a debug APK. Open the repository's **Actions**, open the successful run, and download the `habit-tracker-debug-apk` artifact.

## Important notes

- This is an Android Studio project, **not a prebuilt APK**. It must be built with Android SDK/Gradle before installing.
- The app keeps data in its own WebView storage. Data already stored by the Netlify site or Chrome does not automatically migrate into the APK, because it is a separate app origin/storage area. Keep the old app until you have tested the APK.
- The current HTML's notification button only asks for browser notification permission; it does not schedule native Android reminders. That needs a separate native reminder implementation.
- This wrapper loads the bundled HTML locally and does not require a network connection for the main tracker.
