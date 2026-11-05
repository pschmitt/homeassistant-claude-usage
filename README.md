<p align="center">
  <a href="https://my.home-assistant.io/redirect/marketplace_repository/?owner=pschmitt&amp;repository=homeassistant-claude-usage&amp;category=integration"><img src="https://my.home-assistant.io/badges/marketplace_repository.svg" alt="Open this integration in Home Assistant Marketplace"></a>
</p>

<h1 align="center">Claude Usage for Home Assistant</h1>

<p align="center">Monitor Anthropic subscription usage, reset times and extra-usage credits in Home Assistant.</p>

![Claude Usage screenshot](screenshot.jpg)

## Features

- **Usage sensors:** Track five-hour and seven-day utilization, reset times and extra-usage credits.
- **Dynamic limits:** Create a sensor for each quota bucket returned by the usage API. See [Sensors and dashboard](docs/sensors-and-dashboard.md).
- **OAuth sign-in:** Authorize the integration through Anthropic's browser flow and enter the returned code in Home Assistant.
- **Polling controls:** Set an update interval from 60 to 3600 seconds in the integration options.

## Install

Use the Marketplace badge above on Home Assistant 2026.11 or later to add this
repository as a custom integration. On older versions, add it as a HACS
custom repository of type **Integration**. Install and restart Home Assistant.
The badge does not imply a public catalog listing. For manual installation,
copy `custom_components/hass_claude_usage/` into Home Assistant's
`custom_components/` directory and restart.

## Quick start

1. Add **Claude Usage** under **Settings → Devices & services → Add integration**.
2. Open the authorization URL, sign in, then copy the returned code into the Home Assistant flow.
3. Inspect the usage sensors or import the sample dashboard linked below.

## Documentation

| Topic | Description |
|-------|-------------|
| [Sensors and dashboard](docs/sensors-and-dashboard.md) | Available metrics, sample dashboard, and polling guidance |

## License

[MIT](LICENSE).
