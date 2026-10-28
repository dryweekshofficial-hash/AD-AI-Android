# Build AD AI using only an Android phone

This project includes a GitHub Actions workflow at `.github/workflows/android-apk.yml`. GitHub's cloud runner builds the APK, so Android Studio is not required on your phone.

## If you can upload the extracted project files to a GitHub repository

1. Create a **private** repository on GitHub.
2. Upload the project contents (the `app`, `.github`, and Gradle files) to the repository root. Do not upload only the ZIP if you want the included workflow to run directly.
3. Open the repository's **Actions** tab.
4. Select **Build AD AI Android APK** and tap **Run workflow**. If the workflow does not appear, confirm `.github/workflows/android-apk.yml` is committed on the default branch.
5. Wait for the workflow to finish. A green check means the build job completed.
6. Open the completed run, scroll to **Artifacts**, and download `AD-AI-debug-APK`.
7. Extract the downloaded artifact ZIP, then install `app-debug.apk` on your Android phone. Android may ask you to allow installs from the browser or file manager you used.

## If GitHub mobile upload makes folders difficult

You may upload `AD-AI-Android-Source.zip` to the repository, but GitHub Actions will not automatically execute a workflow stored inside that ZIP. In that case, create `.github/workflows/android-apk.yml` in the repository and use a workflow that first extracts the ZIP. The build workflow in this project assumes the project files are already at the repository root.

## Important

- The APK is a **debug APK**, suitable for personal testing. A signed release APK needs a release-signing configuration.
- The first build may fail if a dependency or API changes. Read the Actions build log for the exact error.
- The API key is entered inside the installed app; never commit it to GitHub.
- GitHub Actions usage limits and availability depend on your GitHub plan and repository settings.
