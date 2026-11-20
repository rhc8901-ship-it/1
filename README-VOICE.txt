RC Trading Journal - Voice Assistant (Hindi + English) - APK rebuild

KYA BADLA
- Naye files: va-nlu.js, va-io.js, va-app.js, va-core.js, va-ui.js, scripts/patch-android-manifest.js, tests/
- Badle hue files: index.html (sirf 3 chhote hook), package.json (+text-to-speech plugin),
  voice-bridge-entry.js, sw.js, .github/workflows/build-apk.yml
- Wahi rahe: app ID com.rohanchauhan.tradesjournal, app name, manifest.json, icons, trade data keys
  (gj_t, gj_s, ...). Voice settings alag key "gj_voice" mein save hoti hain.

GITHUB PAR UPLOAD (phone ke browser se bhi ho jata hai)
1. Repo ke ROOT mein in files ko upload/replace karo:
   index.html, package.json, capacitor.config.json (dot wala naam!), voice-bridge-entry.js, sw.js,
   va-nlu.js, va-io.js, va-app.js, va-core.js, va-ui.js
2. Folder "scripts" ke andar patch-android-manifest.js upload karo.
3. Folder "tests" ke andar nlu-quick.js aur va-tests.js upload karo (build in tests ko chalata hai).
4. .github/workflows/build-apk.yml replace karo.
5. Apne purane manifest.json, sw.js ke alawa icon-192.png, icon-512.png, assets/icon.png repo mein rehne do.

APK BANANA
GitHub > Actions > "Build RC Android APK" > Run workflow. Khatam hone par artifact
"RC-Trading-Journal-APK" download karo, zip kholo, app-debug.apk install karo.
Purani app pehle uninstall karo (har build ki debug signing key alag hoti hai, aapne data save
karne ko mana kiya hai isliye yeh theek hai).

PEHLI BAAR PHONE PAR
- Mic button dabao > Microphone permission Allow karo.
- Hindi/English awaaz ke liye phone mein Google "Speech Services" aur Text-to-speech voices hone chahiye.
  Panel ki gear (settings) mein "Install voices" button hai. Wahan voice chuno (female pehle dikhti hain)
  aur "Test voice" dabao.

KAISE CHALAYEN
- Mic dabao aur bolo. Mic ko dabaye rakho (long-press) to panel khulta hai aur command type kar sakte ho.
- Mic ko upar/neeche drag kar sakte ho taaki kuch na chhupe.
- Misaal: "Naya trade add karo", "Gold", "Buy", "2650", "2660", "Haan" |
  "Aaj ka profit kitna hai?" | "Is mahine ka win rate" | "Sabse accha pair kaun sa hai?" |
  "Aakhri trade dikhao" | "Aakhri trade delete karo" (do baar confirm) | "Ab Hindi mein baat karo" |
  "Switch to English" | "Voice replies mute karo" | "Aur dheere bolo" | "Dobara bolo" | "Help"

SAFETY
- Trade save/edit/export: pehle preview aur "haan/yes".
- Delete: do baar confirm. Restore/Reset/Saara data delete: voice se nahi hota, sirf touch se.
- Samajh na aaye, shor ya chuppi = kabhi "haan" nahi maana jata. Kuch nahi hota.
- Mic sirf tab chalta hai jab aap dabao (ya sawal ke jawab ke intezaar mein, aur tab icon dikhta hai).
- AI coach ko sawal bhejna default BAND hai (gear > "Anjaan sawal AI coach ko bhejo").

TEST COMMANDS (computer par, optional)
  npm test          # NLU + engine tests (CI mein bhi chalte hain)
  python3 tests/e2e-browser.py   # real index.html par browser test (Playwright chahiye)
