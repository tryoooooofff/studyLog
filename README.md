# StudyFlow
 
Single-file study planner (`index.html`). No build step, no dependencies.
 
## Run it
Just open `index.html` in a browser, or enable **GitHub Pages** for this repo
(Settings → Pages → Deploy from branch → `main` / root) to get a stable URL
you can open from any device.
 
## Cloud sync
Data lives in `localStorage` by default. To sync across devices, open the
account panel in the app and set up the **Cloud sync** section with a GitHub
Personal Access Token (`gist` scope only) — it stores your data in a private
Gist. See `.github/copilot-instructions.md` for how it's implemented.
