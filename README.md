# FHEM Command Assistants

A single-page web app that provides guided form builders for common [FHEM](https://fhem.de/) commands. Fill in the fields, see a live preview, and send commands directly to your FHEM server.

## Features

Four tab-based assistants:

| Tab | Purpose |
|-----|---------|
| **at** | Build `at` timer definitions (fixed time, relative, sunrise/sunset, date/time, at_ultimo, custom Perl) |
| **IF** | Build conditional `IF` commands |
| **DOIF** | Build event-driven `DOIF` automations (FHEM and Perl mode) |
| **define** | Create general device definitions with `define` / `defmod` |

### define tab — supported device types

`dummy`, `notify`, `watchdog`, `FileLog`, `readingsProxy`, `structure`, `MQTT2_DEVICE`, `Tasmota`, and a free-form custom type option.

### Common capabilities

- Live preview with syntax highlighting
- Copy to clipboard
- Send commands directly to FHEM (with CSRF token and Basic Auth support)
- Device and reading autocomplete from your FHEM server
- Collapsible attribute sections per tab

## Usage

1. Open `index.html` in a browser — no build step or dependencies required.
2. (Optional) Click the connection icon to connect to your FHEM server for autocomplete and direct command sending.
3. Select a tab, fill in the form, and use **Copy** or **Send**.

## FHEM Server Connection

The app connects to FHEM via its built-in web interface (FHEMWEB):

- **URL** — e.g. `http://192.168.1.10:8083`
- **Authentication** — HTTP Basic Auth (if configured)
- **CSRF** — automatically fetched from the `X-FHEM-csrfToken` header

## License

MIT
