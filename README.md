# Site Daily Log – Android app

Daily construction activities and manpower for Project J237 (Makkah Seven).
The project builds a ready-to-install **SiteDailyLog.apk**.

## Get the APK with GitHub (free, nothing to install)

1. Sign in at https://github.com (create a free account if needed).
2. Click **+ → New repository**, name it `site-daily-log`, choose **Private**, and click **Create repository**.
3. On the new repository page click **uploading an existing file**.
4. Unzip `SiteDailyLog-Android.zip` on your computer. Open the `SiteDailyLog-Android` folder, select **everything inside it**, and drag it into the GitHub page. Then click **Commit changes**.
5. Check that the `.github` folder was uploaded. Some computers hide it, so it may have been left out.
   If it is missing, click **Add file → Create new file**, type the name `.github/workflows/build-apk.yml`,
   paste the contents of that file from the zip, and click **Commit changes**.
6. Open the **Actions** tab. A job called **Build APK** starts on its own. Wait about 5 minutes for the green tick.
7. Click the finished run. Under **Artifacts**, download **SiteDailyLog-APK**. Unzip it to get **SiteDailyLog.apk**.

## Install on the phone

1. Send `SiteDailyLog.apk` to the phone (WhatsApp, email, Google Drive or USB).
2. Tap the file. When Android asks, allow **Install unknown apps** for that app (WhatsApp, Files, Chrome…).
3. Tap **Install**, then **Open**.

## Updating later

Change any file in the repository, and GitHub builds a new APK automatically. Every build uses the same signing key
(`app/sitelog.jks`), so the new APK installs over the old one and **the phone keeps its reports**.
Keep the key file. If it is lost, future builds can't update the installed app.

## Good to know

- Reports are saved **on the phone**. Use **Team & project → Save backup** regularly, and keep the file in WhatsApp,
  email or Drive. **Restore backup** loads it on a new phone.
- **Excel report** builds the day's report in the same layout as the KSP daily report. You can then share it or open it,
  and on Android 10 and newer it is also saved to *Downloads › SiteDailyLog*.
- **Share summary** sends a text version of the day straight to WhatsApp or email.
- Works offline. The Excel engine is packed into the APK during the GitHub build.

## Android Studio (alternative)

Open this folder in Android Studio and choose **Build → Build APK(s)**.
For Excel export to work offline, first download
`https://cdnjs.cloudflare.com/ajax/libs/exceljs/4.4.0/exceljs.min.js` into `app/src/main/assets/`.
Without it, export still works whenever the phone has internet.
