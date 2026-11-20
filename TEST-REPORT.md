# Test report

## Actually executed here (all passed)
| Check | Result |
|---|---|
| NLU: 73 Hindi / English / Hinglish / Devanagari phrases -> correct intent | 73/73 |
| Number parsing: digits, English words, "twenty six fifty", Hindi words, decimals | pass |
| Engine + dialog tests with mock journal (stats, trade creation, correction, edit, delete x2 confirm, noise not approval, modes, language switch, rapid/duplicate commands, unknown = no action, restore touch-only, registry integrity) | 179/179 |
| Real `index.html` in Chromium, mocked Android plugins: touch nav still works, voice nav, stats from stored data, full trade dialog on the real form, real `saveTrade`, correction, edit-in-place, delete needs 2 confirmations, existing trades untouched, Hindi reply spoken as hi-IN, two recognition result styles, never 2 recognition sessions, text-only silent, prefs + trades survive reload, permission denied, nothing heard, TTS unavailable, dark mode, restore blocked, settings panel, zero page errors | 41/41 |
| JS syntax of all files and the inline app script | pass |
| AndroidManifest patch script on a standard Capacitor 6 manifest (idempotent, valid XML) | pass |

## NOT possible here - needs your phone or the first GitHub run
- Gradle/APK build (no Android SDK or network here). The workflow also runs the tests first.
- `@capacitor-community/text-to-speech@^6.0.0`: version could not be checked offline. If `npm install` fails, send me the log.
- Real Hindi/English recognition accuracy, real Android TTS voices (female availability), offline recognition,
  microphone permission dialog, Android 11+ speech-service visibility, behaviour when app goes to background.
