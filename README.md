# Sandworm
A quick and easy Python script  for complicating the monitoring of your network traffic by third parties.

## Description

A small macOS app that sends randomised background HTTP requests to a list of
sites you choose, masking your real traffic patterns from network-level
observers. Requests go out as a system Python process — not your browser.

## Install

1. Download most recent version as ZIP in the Releases panel. Double-click **Sandworm.pkg**.
2. Follow the installer. The app is placed in **/Applications**.
3. Open **Sandworm** from Applications (or Launchpad).

> **First-open Gatekeeper note:** this package is not signed with an Apple
> Developer ID, so macOS may say it's from an *"unidentified developer."*
> If that happens:
> - **Right-click** the `.pkg` → **Open** → **Open** again, **or**
> - System Settings → Privacy & Security → scroll down → **Open Anyway**.

## Requirements

Sandworm uses Python 3 with Tk (`tkinter`), which it locates automatically.
macOS does not always ship a working one, so if the app reports that no usable
Python was found, install either:

- **python.org** build (recommended): https://www.python.org/downloads/macos/  — includes a working Tk, or
- **Homebrew:** `brew install python-tk`

Then reopen the app.

## Usage

- **Start / Stop** — begin or pause sending decoy requests.
- **Target sites** — edit the four URLs (one per row). Click **Save sites**.
- **Delay slider** — sets the max gap between requests; the min is one-third of it.
- **Activity log** — live request results; **Save log** writes to your Desktop.
- Stats cards show totals, successes, failures, and success rate.

Settings persist in `~/.sandworm_config.json`.

## Uninstall

1. Quit the app.
2. Delete `/Applications/Sandworm.app`.
3. (Optional) Delete `~/.sandworm_config.json`.

## Privacy

- No data is collected or sent anywhere except the target sites you choose.
- User-Agent is a generic `Mozilla/5.0 (compatible; …)` string.
- All configuration is stored locally
