# HYROX Training Planner

A static personal HYROX training planner. It needs no account, API, database or server: check-offs, notes, activities, and rescheduled sessions are saved in the browser using local storage.

## Run locally
Open `hyrox-readiness-dashboard.html` in a browser, or serve the folder locally so the page can fetch `Hyrox program.txt`.

Quick local servers:

- Python 3 (built-in, recommended):

```powershell

python -m http.server 8000
# then open http://localhost:8000/hyrox-readiness-dashboard.html
```

- Node (http-server):

```bash

npx http-server -p 8000
# then open http://localhost:8000/hyrox-readiness-dashboard.html
```

- VS Code Live Server: right-click `hyrox-readiness-dashboard.html` → "Open with Live Server".

Notes:
- Serving over HTTP is required if you want the page to fetch the local `Hyrox program.txt` file. Opening the file via `file://` may block that fetch in some browsers.
- If you make edits to the HTML/JS, refresh the browser to reload.

## Publish on GitHub Pages

1. Create a GitHub repository and upload the contents of this folder (not the parent `outputs` folder).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, select **GitHub Actions**. The included workflow deploys the site when you push to `main`.
4. After the workflow completes, GitHub displays the public Pages address in **Settings → Pages**.

## Your data / “memory”

The app stores all check-ins, rescheduled sessions, notes and manual activity entries in your browser. This remains after reloads and when hosted on GitHub Pages, but it is browser/device-specific. Use **Export backup** regularly and **Import backup** on a new browser or device.

GitHub Pages is a static host: it cannot safely write personal notes to GitHub or synchronize them between devices. Cross-device automatic sync would require a separate authenticated database service.

## Testing checklist

- Verify the external program parser: place `Hyrox program.txt` beside the HTML file and open the dashboard; the page will attempt to load and parse the file and replace the built-in 13-week plan if successful. Check the browser console for "Loaded Hyrox program.txt" or errors.
- Add a session: use the **+ Session** button on the dashboard or the program tab to add a custom session for the current week; it is saved to localStorage.
- Delete a session: swipe left (touch or click/drag) on a session to reveal the delete button, then click ×. Official sessions are hidden; custom sessions are removed from storage.
- Export/import: use the **Export backup** and **Import backup** controls on the Log tab to save/restore your data.

## Troubleshooting

- If the parser doesn't appear to load the external file, confirm the server is running and that `Hyrox program.txt` exists next to `hyrox-readiness-dashboard.html`.
- If you see CORS or fetch errors when opening via `file://`, use one of the local server options above.

If you'd like, I can add a small automated test script (Playwright) to exercise add/delete/import flows.
