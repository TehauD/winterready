# WinterReady

A winter storm and outage planner for households. It tells you how bad things are, what you need for your household, and what to do next. It runs entirely in your browser and keeps working offline.

> **WinterReady is general information, not professional advice.** Its numbers are estimates from simplified models. Follow your local officials and manufacturer instructions, and call 911 in an emergency. Read the full [disclaimer](DISCLAIMER.md).

## What it does

- **Status.** Pick a severity level: Normal, Watch, Prepare, Survive, or Recover. The interface changes with it. You see current conditions, your next three actions, your readiness percentage, what's missing, and Tonight's plan.
- **Emergency mode.** One button walks you through the first five minutes, one step at a time.
- **What's happening.** Eleven situation cards, each with ordered steps: power out, house getting cold, stranded in a car, heavy snow coming, pipes freezing, emergency heat, cell service down, can't leave home, someone injured, a pet in trouble, and feeling unsafe.
- **Outlook.** Pick a likely scenario (typical storm, major ice storm, extreme cold, long grid outage) to see its likelihood, a projected cooling curve for your house, how long your supplies last, a timeline of what fails when, what to buy now, and Plan A→D fallbacks for heat, water, power, shelter, and travel.
- **Help me decide.** Short decision trees for the most common calls: stay or go, should I drive, drip or drain pipes, is it carbon monoxide, and what to do as an outage drags on.
- **Personal protection (optional).** Home security during outages, verifying people at the door, scam awareness, protective gear, and safe firearm storage.
- **Planner.** Enter your household, home, warm room, and what you already have. It works out heat load and heater fuel, water, calories, power-station size, sanitation, and pet supplies. It also tells you what you can do with the gear you have.
- **Checklist.** A shopping list sized from the Planner, weighted by priority.
- **Family.** Add the people in your home and give everyone an age-appropriate job.
- **Guide.** Survival guidance with links to official sources.
- **Emergency sheet.** Contacts, shutoff locations, medical notes, and quick rules, laid out for printing.

### Hidden mode

There's an Armageddon mode for worst-case planning (months without utilities, radiological shelter-in-place, winter illness outbreaks). To unlock it, type `armageddon` in the command menu (`⌘K`), enter the Konami code, or tap the logo 7 times. You can turn it off from the banner or in Settings.

## How the advice is made

Tonight's plan, "What you can do," the Outlook, and the decision trees come from fixed rules and simple models applied to your profile and conditions. There's no AI in the app. Every recommendation shows why it was made and links to its source: Ready.gov, CDC, EPA, or the National Weather Service. Every calculator card has a **How this is estimated** section that lists its assumptions.

## Privacy

There are no accounts and no server. Everything you enter is saved in your browser's `localStorage` and stays on your device. If you choose **Get NWS forecast**, your approximate coordinates are sent to `api.weather.gov` to get the forecast. Nothing else leaves the browser.

## Run it

It's a static site with no build step.

- **GitHub Pages:** go to Settings → Pages and deploy from the `main` branch root.
- **Azure Static Web Apps or App Service:** deploy the folder as-is.
- **Locally:** run `npx serve .` or `python3 -m http.server`, then open `http://localhost:3000` or `http://localhost:8000`.

Offline support uses a service worker (`sw.js`), which needs HTTPS or `localhost`. After the first visit, the app shell is cached. The last forecast you pulled is kept in the browser.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app (HTML, CSS, JS) |
| `sw.js` | Service worker for offline use |
| `manifest.webmanifest` | Lets it install as an app |
| `icon.svg` | App icon |
| `DISCLAIMER.md` | Full disclaimer, also shown in the app |
| `LICENSE` | MIT License |

## Sources

- [Ready.gov: Winter Weather](https://www.ready.gov/winter-weather)
- [Ready.gov: Power Outages](https://www.ready.gov/power-outages)
- [Ready.gov: Water](https://www.ready.gov/water)
- [Ready.gov: Pets](https://www.ready.gov/pets)
- [EPA: Emergency Disinfection of Drinking Water](https://www.epa.gov/ground-water-and-drinking-water/emergency-disinfection-drinking-water)
- [CDC: Carbon Monoxide Poisoning](https://www.cdc.gov/carbon-monoxide/about/index.html)
- [CDC: Winter Weather](https://www.cdc.gov/winter-weather/about/index.html)
- [National Weather Service: Winter Safety](https://www.weather.gov/safety/winter)
- [FTC: Avoid weather-related utility scams](https://consumer.ftc.gov/consumer-alerts/2026/01/avoid-weather-related-utility-scams-after-recent-winter-storm)
- [CDC: Radiation emergencies, stay inside](https://www.cdc.gov/radiation-emergencies/response/stay-inside.html)

---

Made by Tehau DeBarthe · [veritas.azurewebsites.net](https://veritas.azurewebsites.net)

[MIT License](LICENSE). Provided as is, without warranty. See the [disclaimer](DISCLAIMER.md).
