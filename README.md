# BlueWave Chat

A native Android Bluetooth text-chat starter app built with Kotlin and Jetpack Compose.

## Features
- Direct offline text messaging over Bluetooth Classic (RFCOMM)
- Host mode: one phone waits for an incoming chat
- Find nearby Bluetooth devices and connect
- Paired-device list and connection status
- Modern dark interface, message bubbles, timestamps
- Clear local conversation and disconnect controls
- Runtime Bluetooth permissions for Android 12+

## Requirements
- Android Studio Ladybug or newer
- JDK 17
- Android SDK 35
- Two Android phones with Bluetooth Classic support
- Android 8.0 (API 26) or newer

## Build
1. Unzip the project.
2. Open the `BlueWaveChat` folder in Android Studio.
3. Allow Gradle sync and install any requested Android SDK components.
4. Connect an Android phone and press **Run**.
5. Install the same app on the second phone.

## First connection
1. Turn Bluetooth on on both phones.
2. Pair the phones in Android Settings > Bluetooth (recommended; Android may also prompt to pair).
3. Open BlueWave Chat on phone A and tap **Host chat**.
4. On phone B, tap **Find devices** and select phone A.
5. Accept any Android pairing/connection prompts.
6. Open the Messages tab on both phones and chat.

The host and client must use the same app UUID. The UUID is defined in `BluetoothChatManager.kt`.

## Important notes
- This is a Bluetooth Classic RFCOMM text-chat implementation, not Bluetooth Low Energy.
- The app does not use the internet or a server.
- Messages are not encrypted by this starter implementation. Do not use it for sensitive information.
- Android manufacturer settings and OS versions can affect discovery and pairing. Pairing first in system Bluetooth settings is the most reliable route.
- Bluetooth discovery is time-limited by Android. Tap Find devices again to scan again.
- The current version keeps messages in memory only; closing the app clears the local conversation.
- For production use, add authenticated/encrypted message framing, persistent storage, reconnection, foreground-service handling for long sessions, delivery acknowledgements, and stronger lifecycle management.
