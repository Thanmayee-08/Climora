# CLIMORA Sustainability Website

A responsive, multi-page-style campus sustainability dashboard built with **HTML, CSS and vanilla JavaScript**. It follows the uploaded CLIMORA logo and dashboard reference, using a dark teal sidebar, green accents, white cards, KPI rings, charts, sample alerts and a stylised campus digital twin.

## Run it

1. Extract `climora-website.zip` to a folder.
2. Open `index.html` in a modern browser.
3. Sign in using the demo values shown on the login screen:
   - Email: `admin@climora.demo`
   - Password: `climora123`
4. Use the left navigation to move between Dashboard, Campus Map, Energy, Water, Environment, Buildings, Alerts, Reports and Recommendations.

No build step or package installation is required. For a local development server, you can use VS Code's Live Server extension or run `python -m http.server 8000` in this folder and visit `http://localhost:8000`.

## Included interactions

- Responsive navigation and demo sign-in/sign-out
- KPI dashboard and SVG-generated energy/water charts
- Search/filter building directory and map-pin detail panel
- Alert filtering and mark-as-reviewed actions
- Water-conservation checklist
- Recommendation completion buttons
- CSV downloads for sample resource readings and alerts

## Important: demo data vs real deployment

All measurements are illustrative sample data. The login is **not real authentication** and does not secure the site. Do not use it to protect private information or deploy as-is for production.

## Connecting physical sensors later

Keep the UI separate from the data source. When your hardware/API is ready, replace the sample arrays in `app.js` with calls to your backend. A typical flow is:

`IoT sensors → gateway/MQTT or HTTP → backend API/database → CLIMORA frontend`

Suggested API shape:

- `GET /api/campus/summary`
- `GET /api/buildings`
- `GET /api/readings?type=energy&range=7d`
- `GET /api/alerts`
- `POST /api/alerts/:id/acknowledge`

Never put device secrets, database credentials or private API keys in browser JavaScript. Add server-side authentication and authorisation before using real campus data.
