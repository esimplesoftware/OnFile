# Onfile user manual

Onfile is a Windows tray app that finds files by name on local drives and on network shares you add. It keeps an index on your PC. 
Local NTFS volumes can stay current automatically; network shares update when you scan.

Version 1.1.0 Public Preview. Windows 10/11 64-bit.

## Install

1. Download **Onfile-1.1.0-Setup.exe** from [Releases](https://github.com/esimplesoftware/onfile/releases/latest).
2. Run the installer. Windows may show **SmartScreen** (“Windows protected your PC”). Choose **More info** → **Run anyway**. 
   The preview is not code-signed yet.
3. Accept the EULA. Install is per-user (`%LOCALAPPDATA%\Onfile`).
4. Optionally create a desktop shortcut.
5. On first run, Onfile may ask for **administrator** permission so it can install the **USN helper** service. That service reads local 
   disk change journals so C: and D: stay up to date. Network shares do not use it.

To remove Onfile: Settings → Apps → Onfile → Uninstall. That stops the helper and can remove Onfile settings folders.

## Start and tray

- Start **Onfile** from the desktop shortcut or `%LOCALAPPDATA%\Onfile\findex-ui.exe`.
- Closing the window hides it to the tray; it does not exit.
- Tray icon: left-click shows the window; right-click → Show or Exit.
- Default hotkey: **Ctrl+Shift+F** .
- Only one copy runs at a time. Starting a second copy focuses the first.

## Add volumes

**Volumes** menu or the list at the top of the window.

- **Add local** — a drive or folder on this PC (for example `C:\`, `D:\`).
- **Add remote** — a UNC path (for example `\\server\share\`).
- **Scan now** — rebuild the index for that volume.
- **Pause / Resume** — stop or start using that volume.
- **Index filters** — include/exclude patterns for that volume.
- **Remove volume** — drop it from the index (does not delete your files).

Status on each row: Added, Loading, Indexing, Synced, Catching up, Stale, Error.  
**Journal = Current** means live update is running on that local volume. Remote rows show **—**.

## Search

Type in the box under the volume list (at least 2 characters by default). Results appear below.

Columns: name, path, volume. Select a row for details under the list (modified, how long ago, size, created) if that option is on.

Open a result:

- **Enter** — open the file
- **Ctrl+Enter** — open the folder
- **Ctrl+Shift+Enter** — open a command prompt in that folder
- Right-click for the same commands, plus copy path / copy name

### Narrow a search

If you see a note that the list is capped (default 200 rows), tighten the query:

| You type | Meaning |
|---|---|
| `list` | name or path contains “list”, better name matches first |
| `list D:` or `list D:\` | only that drive |
| `list \\server\share\` | only that share |
| `list*` | name **starts with** list |
| `*.txt` | name ends with `.txt` |
| `list.*` | `list` plus any extension |
| `"budget 2026.xlsx"` | exact file name |

You can combine a pattern and a volume: `list* D:`.


## Where files live

| What | Typical location |
|---|---|
| Program | `%LOCALAPPDATA%\Onfile\` |
| Settings, database, app log | `%APPDATA%\Findex\` |
| Helper log | `%LOCALAPPDATA%\Findex\usn-helper.log` |


## Helper service

Windows name: **FindexUsn** (or similar). It must be running for live update on local NTFS.

If live update stays off: start Onfile so it can install/start the helper, or use an elevated prompt:

Do not delete the service unless you are uninstalling. After uninstall the service should be gone; if it is not, reboot and uninstall again 
or use Services.msc.  If you have problems removing the helper use an elevated powershell session and type : sc.exe delete FindexUsn [enter] 
this should reply back "DeleteService SUCCESS".  

##Network shares

There is no live update on remotes. If a result is gone or new files are missing: select the volume → Scan now. The details strip may say Not 
found — Scan this volume to refresh or Volume unavailable.

##Logging and support

Logs start with the version (Onfile 1.1.0). Send that line plus a short description.
Email: esimplesoftware@gmail.com
Please include:

Windows version
Onfile version from the log
findex.log and, if live update is the issue, usn-helper.log

Do not send findex.db unless asked.
##Uninstall / leftover data

The installer can remove %APPDATA%\Findex and %LOCALAPPDATA%\Findex. If a folder remains, you can delete it after Exit from the tray.

##Known preview limits

SmartScreen warning until the installer is signed
Helper install needs elevation
Shares need a manual scan
One user on the PC is the supported case