# StudyFlow
 
Single-file study planner (`index.html`). No build step, no dependencies.
 
## Run it
Just open `index.html` in a browser, or enable **GitHub Pages** for this repo
(Settings → Pages → Deploy from branch → `main` / root) to get a stable URL
you can open from any device.
 
## Cover plans
On the **Plan table** (or **Today**) page, use **Cover plan** to make a temporary
short-term plan of up to 30 days. Pick a goal, a start date and a number of days,
then type one task per line for each day (`Task | minutes` is optional). Inside
that date range the cover plan replaces the original plan's tasks in Today's view
and in the calendar — the original tasks are only hidden, never deleted, so they
reappear when you remove the cover plan or its days pass. Finished/removed cover
plans are kept under **Previous plans** in the account panel.

## Cloud sync
Data lives in `localStorage` by default. To sync across devices, open the
account panel in the app and set up the **Cloud sync** section with a GitHub
Personal Access Token (`gist` scope only) — it stores your data in a private
Gist. See `.github/copilot-instructions.md` for how it's implemented.
