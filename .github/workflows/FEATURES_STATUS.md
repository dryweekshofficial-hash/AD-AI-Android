# AD AI feature status

| Feature | Status |
|---|---|
| Native Android UI (Kotlin + Jetpack Compose) | Implemented in source; not device-tested here |
| Gemini 2.5 Flash text chat | Implemented in source; needs a valid key and runtime test |
| API key entry and encrypted local preferences | Implemented in source; needs runtime test |
| Hindi speech input | Android speech recognizer; device/provider dependent |
| Spoken answers | Android TextToSpeech; Hindi voice availability depends on the device |
| Multi-turn chat context | Implemented using user/model roles; needs API runtime test |
| Google Search grounding toggle | Implemented in request; provider/model/account availability and source extraction need runtime test |
| Source URLs from grounding metadata | Implemented when Gemini returns web grounding chunks; needs runtime test |
| Open YouTube, Android Settings, alarm screen, web search | Basic Android intent handlers implemented |
| Flashlight toggle | Implemented with camera permission request; device test needed |
| Clear current chat on screen | Implemented; chat history is not persisted between app launches |
| Gemini Live bidirectional audio streaming | Not implemented |
| Always-on wake word/background listening | Not implemented |
| Full unrestricted phone control | Not possible for a normal app; only permitted Android APIs and user-enabled services |
| Live weather/news/sports APIs as separate integrations | Not implemented; optional Google Search grounding may answer some current-information queries |
| Release signing | Not configured |
| APK build | Not built in this environment because Android SDK and Gradle are unavailable |
