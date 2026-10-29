# SakhiAI - Raat ki Saathi

An AI-powered women safety app concept. SakhiAI talks to you on a late-night journey, watches for danger signals, and escalates to family, helplines and police when you can't ask for help yourself.

> **Prototype status:** this repo is a working web demo of the core flow. Alerts to police, family and helplines are **simulated**. No real SMS, call or location is sent.

## The problem
Most safety apps help only after the user presses an SOS button. In real danger, unlocking a phone and asking for help is often impossible.

## What the prototype demonstrates
- **AI companion chat:** Sakhi checks in and replies in Hinglish. Optional Hindi voice.
- **Live risk score (0-100):** built from signals (route change, scream, phone drop, long stop, no reply to a check-in).
- **4-level escalation:** Normal, Suspicious, Danger, Emergency.
- **10-second cancel PIN** before an alert goes out, to limit false alarms.
- **Duress PIN:** looks like "cancelled" to anyone watching, but sends a silent alert.
- **Coded conversation:** Sakhi asks a normal question ("Mummy ko call kiya?"). Replying with your pre-set code word sends a silent alert while the chat looks normal.
- **Safe-haven guidance:** points to the nearest safe place (demo data).
- **Auto evidence report:** timeline, location trail and chat transcript, ready to copy for a complaint.
- **Fake call** to leave an uncomfortable situation.
- **Family and police feed** that shows what the contacts would see.

## Run locally
No build step. Open `index.html` in a browser.

## Deploy (free)
- **Netlify:** go to app.netlify.com/drop and drag this folder in.
- **Vercel:** import the GitHub repo, framework preset "Other", no build command.
- **GitHub Pages:** Settings > Pages > deploy from the `main` branch, root folder.

## Demo script (for the YouTube video, about 2 minutes)
1. Show the home screen and the "simulated" badge.
2. Chat with Sakhi. Type "dar lag raha hai" and show the risk rise.
3. Tap **Sakhi check-in**, then reply with the code word (default `chai`). Show the silent alert in the feed while the chat looks normal.
4. Tap **Reset demo**. Tap **Route change** then **Scream detected** to reach Level 3. Show the countdown and cancel with PIN `1234`.
5. Trigger Level 3 again and let the timer run out. Show the Emergency alert.
6. Open **Report** and show the evidence report.
7. Try the duress PIN `9999` on another run.

Default settings: code word `chai`, cancel PIN `1234`, duress PIN `9999`. Change them in Settings.

## Planned architecture (full product)
| Layer | Technology |
|---|---|
| Mobile app | Flutter or React Native (Android first) |
| AI conversation | LLM API with Hindi speech-to-text and text-to-speech |
| Danger detection | On-device ML (TensorFlow Lite) for sound and motion |
| Backend | Firebase or Node.js with encrypted storage |
| Alerts | SMS/call provider, then official 112 integration |

## Privacy principles
Consent-first permissions, audio analysed on the device, encrypted data, auto-delete within 24-48 hours, no data selling.

## Limitations
- This is a safety aid, not a guarantee. Always call 112 directly in an emergency.
- iPhone restricts background microphone and location, so the full product starts on Android.
- Police integration in the full product starts with SMS/call to 112, then an official partnership.

## Team
AUREX
