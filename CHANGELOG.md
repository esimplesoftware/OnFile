# OnFile

# Changelog

All notable changes to Onfile are listed here.

## 1.1.0 – 2026-09-19

Public Preview. First build intended for other people to install.

### Added
- Onfile name, app icon, and tray icon
- Windows installer (per-user, optional desktop shortcut)
- File details strip under search results: modified time (with relative age), size, created
- Option to turn file details off (`show_file_details` in Options / ini)
- Ranked search so better name matches are not buried under a large C: drive
- Search filters:
  - `list D:` or `list D:\` — one volume
  - `list*` — name starts with
  - `*.txt` — extension
  - `list.*` — that name, any extension
  - `"exact name.txt"` — exact name
- Hint on the details strip when a search hits the result limit
- `candidate_limit` in the ini (how many hits are scored before the list is cut)
- Relative “ago” text on each volume’s last-update time
- End-user license agreement

### Changed
- Search no longer stops at the first 200 hits in disk order
- Minimum window size set so the layout stays usable
- Logging focused on app/service state instead of per-volume open/close noise

### Fixed
- USN helper service not stopping cleanly from Services
- Helper log path when running as Local System vs the logged-on user
- Tab between search box and results (and the beep)
- Details strip overlapping or smearing the status bar when resizing
- Details strip showing a file after clearing the search box

### Known issues
- Windows SmartScreen may warn; the preview is not Authenticode-signed yet
- Network shares have no live update; use Scan if a file is missing
- First-run helper install requires elevation

## 1.0.0

Internal builds: tray app, local/remote volumes, USN live update, SQLite index.
