# StudyFlow — instructions for AI coding assistants
 
Single-file app: everything (HTML/CSS/JS) lives in `index.html`. No build step,
no framework, no dependencies. Keep it that way unless explicitly asked to split
it up.
 
## State
- Single global `S` object holds all app data (blocks, plans, todos, timer,
  theme, etc.). `defaultState()` defines its shape.
- `save()` persists `S` to `localStorage` (key `studyflow_v2`) **and** triggers
  a debounced push to cloud sync (`cloudSync()`). Always call `save()` after
  mutating `S` — never write to `S` without saving afterward.
- Re-render with `renderAll()` (or the specific `render*()` for the active
  view) after state changes that affect the UI.
## Event handling
- All clicks are delegated through one listener matching `[data-action]`.
  To add a new interactive control: add `data-action="my-action"` (plus
  `data-id`/other data-* as needed) to the markup, then add a `case
  'my-action':` in the big switch near the bottom of the script.
- Forms are handled the same way via a delegated `submit` listener, matched by
  form `id`.
- Inputs with `data-draft` / `data-manual` / `data-manual-row` auto-sync into
  `S` on the `input` event — reuse this pattern for new plain-text/number
  fields, don't hand-wire new listeners per field.
## Cloud sync (GitHub Gist backend)
- `CLOUD` (`{token, gistId}`) is stored separately in `localStorage`
  (`studyflow_cloud_cfg`) — never merge it into `S` or push it to the gist.
- `cloudSync()` is debounced (2s) and only fires if `cloudConfigured()`.
- `cloudLoad()` / `cloudSaveNow()` / `cloudCreateGist()` talk directly to
  `api.github.com` from the browser using a PAT with only the `gist` scope.
  There is no backend server — do not introduce one for this feature.
- Sync is last-write-wins, no merge logic. Don't add conflict resolution
  unless asked; keep this feature minimal.
- UI for it lives in `renderAccount()` (the account side panel).
## Style
- Minimal diffs, no reformatting of unrelated code, no introducing a bundler,
  framework, or external JS dependency. Vanilla JS + the existing CSS
  variable system (`:root` / `[data-theme="dark"]`) only.
- Keep everything in `index.html` unless told to split files.
