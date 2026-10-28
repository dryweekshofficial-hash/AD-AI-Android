# API setup

1. Open Google AI Studio in your browser and create a Gemini API key for your own account.
2. Keep the key private. Never paste it into a public issue, repository, or chat.
3. Install AD AI, open the Gemini API settings, paste the key, and press **Key Save**.
4. Try a simple question first. If it fails, check the exact error message, internet connection, key permissions, model availability, and account quota.
5. Use the **Live web search** switch for questions about changing/current information. Search grounding depends on API availability; it may not provide sources for every request.

The app sends the key in the HTTPS `x-goog-api-key` request header, not in the URL. The key is stored locally using encrypted Android preferences. This is suitable for personal testing, not a substitute for a backend proxy in a public multi-user app.
