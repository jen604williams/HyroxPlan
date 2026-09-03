# HYROX Training Planner

A static personal HYROX training planner. It needs no account, API, database or server: check-offs, notes, activities, and rescheduled sessions are saved in the browser using local storage.

## Run locally

Open `hyrox-readiness-dashboard.html` in a browser, or use VS Code’s Live Server extension.

## Publish on GitHub Pages

1. Create a GitHub repository and upload the contents of this folder (not the parent `outputs` folder).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, select **GitHub Actions**. The included workflow deploys the site when you push to `main`.
4. After the workflow completes, GitHub displays the public Pages address in **Settings → Pages**.

## Your data / “memory”

The app stores all check-ins, rescheduled sessions, notes and manual activity entries in your browser. This remains after reloads and when hosted on GitHub Pages, but it is browser/device-specific. Use **Export backup** regularly and **Import backup** on a new browser or device.

GitHub Pages is a static host: it cannot safely write personal notes to GitHub or synchronize them between devices. Cross-device automatic sync would require a separate authenticated database service.
