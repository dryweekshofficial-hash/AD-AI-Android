# AD AI — Android Assistant

This is a first native Android port of the supplied Jarvis Python project. The original ZIP is a Python desktop microphone/speaker app using Gemini Live; it is not itself an Android APK. This project keeps the Hindi-first assistant identity and implements a native Android UI, Gemini text chat, Android speech recognition, Android text-to-speech, encrypted local API-key preferences, basic Android intents, flashlight control, and an optional Google Search grounding request for current information.

## Features implemented in source

- Native Kotlin + Jetpack Compose Android app.
- Gemini API key entry and local encrypted preferences backed by Android Keystore.
- Gemini `gemini-2.5-flash` text conversation with user/model roles for recent context.
- Optional Google Search grounding toggle. When the API returns grounding source URLs, the app appends them to the answer. Availability depends on the API/model/account and must be tested with a valid key.
- Hindi speech-to-text using Android's installed speech recognition provider.
- Hindi text-to-speech using Android TTS; the installed language pack determines voice availability.
- Open YouTube, Android Settings, alarm-setting screen, web search, and flashlight toggle.
- Status messages and clear-current-chat control.
- GitHub Actions workflow to build a debug APK in the cloud, useful when working from a phone without a computer.

## Not implemented / limitations

- Gemini Live bidirectional audio streaming.
- Always-on wake word or background listening.
- Arbitrary control of all apps or unrestricted system-wide access.
- Dedicated weather/news/sports API integrations. Google Search grounding may retrieve some current information, but it is not a guarantee for every query.
- Persistent conversation history, calendar/email integrations, backend API proxy, release signing, and device-specific testing.

## Build in Android Studio

Use a recent Android Studio installation with Android SDK Platform 35 and Java 17. Sync Gradle, then choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**. Expected output after a successful build: `app/build/outputs/apk/debug/app-debug.apk`.

The project uses Android Gradle Plugin 8.9.2 and works with Gradle 8.11.1. A GitHub Actions workflow is provided at `.github/workflows/android-apk.yml` to build the debug APK in a cloud runner. See `BUILD_ON_PHONE.md` for phone-only instructions.

## API setup

1. Create a Gemini API key using Google AI Studio.
2. Install and open AD AI.
3. Enter the key in the Gemini API settings and tap **Key Save**.
4. Turn on Live web search if you want to request Google Search grounding for changing facts.

The API key is sent to Google's API over HTTPS in the `x-goog-api-key` header. It is stored locally using encrypted preferences. Do not share it or commit it to source control. Chat text is processed by Google's service. API availability, model access, quota, and search grounding depend on your account and the provider's current terms.

## Permissions

- Microphone: requested when the user taps the voice input button.
- Camera: requested for the flashlight control on Android versions that require it.
- Internet: used for Gemini API requests.

## Security note

This starter app stores a user-supplied key locally. For a public production app used by multiple people, prefer a secure server-side API proxy and a security review. Android permission prompts and app sandbox limits cannot be bypassed by a normal app.
