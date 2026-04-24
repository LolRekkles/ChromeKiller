# ChromeKiller

A one-click `.bat` script that force-closes Google Chrome on Windows, including
any background processes it leaves behind after you close the window.

No installer, no dependencies — just a single batch file.

---

## Why?

Chrome has a habit of lingering in the background long after you've closed every
window, eating RAM and battery. Opening Task Manager to hunt down a dozen
`chrome.exe` processes gets old fast.

Double-click `KillChrome.bat` and they're all gone.

## What it does

The entire script is one line:

```bat
taskkill /F /IM chrome.exe /T
```

| Flag | Meaning |
|------|---------|
| `/F` | Forcefully terminate the process |
| `/IM chrome.exe` | Target any process named `chrome.exe` |
| `/T` | Also kill child processes (tabs, extensions, GPU process, etc.) |

## Usage

1. Download [`KillChrome.bat`](KillChrome.bat).
2. Double-click it.
3. Chrome is closed.

### Optional: pin it somewhere useful

- **Taskbar / Start menu** — right-click the file → *Pin to Start* (or create a
  shortcut and pin that to the taskbar).
- **Desktop shortcut** — right-click → *Send to* → *Desktop (create shortcut)*.
  You can change the icon via *Properties → Change Icon* if you want it to look
  less like a plain batch file.
- **Keyboard shortcut** — right-click the shortcut → *Properties* → *Shortcut
  key*, then press something like `Ctrl+Alt+K`.

## Requirements

- Windows (any modern version — `taskkill` has shipped with Windows since XP).
- That's it.

## Heads up

This is a **force kill**. Any unsaved work in Chrome — open forms, draft
emails, unsaved documents in web apps — will be lost. Chrome's "Restore tabs"
on next launch usually brings back your windows, but don't rely on it for
anything important.

## License

[MIT](LICENSE) — do whatever you want with it.
