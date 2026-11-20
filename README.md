# Orbit

Orbit is an installable planner for tasks, habits, goals and reflections. It stores activity in the browser and supports optional cross-device sync through Supabase. A habit can track both completion and a measured quantity, such as minutes practiced or pages read.

## Run locally

With Node.js 18 or later, run `npm start` from the repository root and open `http://localhost:8080`. The development server uses Node's built-in modules. In a supported browser, use the install option to open Orbit as a standalone app.

## Calendar and analytics

- Schedule one-time or recurring items. Monthly items scheduled on the 31st fall on the last day of shorter months.
- Log a daily quantity independently of the completion checkbox. In analytics, a recorded zero appears as a value and a missing entry appears as a gap.
- Pin an item to revisit its activity by week, month or year. Orbit calculates history for the selected items and refreshes it when the underlying activity changes.

## Storage and sync

Local profiles persist in the current browser. Use **Settings → Export backup** before clearing browser data or moving a local profile. With Supabase configured, Orbit saves changes locally first and syncs the profile to the signed-in account. The repository includes the database schema and configuration steps. [Cloud setup guide](docs/CLOUD_SETUP.md)

## Development and deployment

| Command | Result |
| --- | --- |
| `npm run check` | Check JavaScript syntax. |
| `npm test` | Run calendar, analytics and startup tests, including session restoration. |
| `npm run build` | Generate the static site in `dist/`. |

For Cloudflare Pages, use `main` as the production branch, `npm run build` as the build command and `dist` as the output directory. The Workers configuration also supports `npm run deploy` after the build. Publish only the generated `dist/` directory.
