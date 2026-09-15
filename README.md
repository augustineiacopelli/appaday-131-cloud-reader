# Cloud Reader

**AppADay 131** | Category: Educational | AI-powered | Shipped 2026-09-15

**Live:** https://augustineiacopelli.github.io/appaday-131-cloud-reader/

Point your phone at the sky and Claude reads the deck overhead, naming the cloud type, grading its own confidence, and calling what the next one to three hours hold. A second segment pulls 48 hours of hourly model data for where you stand and narrates it as a broadcast outlook over a live trend strip.

## What it does

The app runs as a two segment weather broadcast. The Nowcast segment takes a photo straight from the rear camera, sends it to Claude as a vision call, and returns the dominant cloud type with its Latin classification, a confidence grade, a short read on the next one to three hours, and an explanation of the visual cues behind the call. Every read drops into a rundown of your last twenty sky checks, kept on the device.

The Outlook segment asks for your location, pulls 48 hours of hourly temperature, rain probability, and cloud cover from Open-Meteo, plots all three on a Chart.js trend strip, and hands a condensed version of the same data to Claude for a spoken forecast written in the voice of an anchor at the wall.

The background gradient is computed from your local hour, so the page shifts through dawn, midday, dusk, and night across the day. The tally light in the header burns red only while a call is in flight.

## Using it

Open the app, tap the key panel, and paste an Anthropic API key. The key is stored in this browser's local storage, is never committed anywhere, and travels only to Anthropic. The panel opens by itself on first run.

Tap the capture strip to shoot the sky or pick an existing photo. The read comes back in a few seconds.

Location is optional. Deny it and the Nowcast still works in full; the Outlook parks with a Locate me button you can tap whenever you want to try again.

## Built with

Vanilla HTML, CSS, and JavaScript in one self contained file, no build step. Barlow Condensed and Spectral from Google Fonts. Chart.js 4.4.1 from jsDelivr. The Anthropic Messages API with claude-sonnet-5 for both the vision read and the written outlook. Open-Meteo for the hourly forecast data, which needs no key.

## Notes

Rundown entries store the time, the cloud name, and the signal line only. Photos are never saved, since a handful of thumbnails would exhaust the local storage quota long before twenty entries.

Cloud identification from a single photo is a judgment call, which is why the app grades its own confidence out loud. Treat a low confidence read as a conversation starter rather than a verdict, and treat the whole thing as a curiosity tool rather than a safety instrument. For watches and warnings, go to the National Weather Service.

---

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete web app designed and shipped every single day.
