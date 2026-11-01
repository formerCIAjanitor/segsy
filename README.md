<h1 align="center" style="margin:0;">
<img src="./banner.png" alt="Segsy banner" width="800">
</h1>
<h3 align="center" style="margin: 0; margin-top: 0;">
Segsy — it's either that or using Excel after it finishes its 1.9 GB update
</h3>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#limitations">Limitations</a> •
<a href="#already-adopted-by-or-likely-soon-to-be-adopted-by">Adopted by</a> •
  <a href="#license">License</a>
</p>

## Overview

[Segsy](https://formerCIAjanitor.github.io/segsy/) is a simple, lightweight Gantt chart editor that runs entirely in the browser, with everything contained in a single HTML file that you can download and use completely offline.

<a href="https://formerCIAjanitor.github.io/segsy/">
  <img src="./screenshot.png" alt="Gantt chart screenshot" title="Launch Segsy!">
</a>

## Features

- **Drag to move, resize and reorder** — grab any bar and slide it left or right along the timeline, pull the left or right edge of a bar to change its start or end date or use the grip handle on the left to drag rows up or down
- **Rename tasks** — click any task name to edit it inline
- **Delete tasks** — right-click a task label and confirm
- **Split tasks** — double-click a bar to split it, an empty cell to add a segment, right-click a segment to remove it
- **Color picker** — click the color dot next to a task name to choose from 9 predefined named colors, or select any custom color
- **Zoom** — switch between day, week or month view, zoom in/out or fit-to-width
- **Task info on hover** — hover a task to see its start date, end date and duration below the chart
- **Current day indicator** — toggle a vertical line marking today on the chart
- **Auto-save** — every change is silently saved to your browser's local storage, so closing and reopening the tab restores your work
- **Export as a PNG or PDF** — save your Gantt chart as a high-resolution image
- **Share as a link** — export a Markdown link that encodes the whole chart in the URL
- **Save/Load** — save and share a chart as a single JSON file
- **Dark mode** — automatically follows your system preference
- **Certified Y2K compliant**

### Saving & sharing

| Action | How |
| --- | --- |
| **Auto-save** | Every change is silently saved to your browser's local storage. Closing and reopening the tab restores your work automatically. |
| **Save JSON** | Downloads a `gantt.json` file that can be used to save or share the Gantt chart. |
| **Load JSON** | Loads a previously saved `gantt.json` file, restoring the chart exactly. |
| **Export PNG** | Downloads a high-resolution PNG. |
| **Export PDF** | Downloads a single-page PDF. |
| **Export Markdown link** | Opens a window with the chart URL and a ready-to-paste Markdown link, `[gantt chart](https://...)`. |

### Sharing via link

**Export → Markdown link** encodes the chart in the URL fragment (`#d=...`).

- Opening a link displays the shared chart without touching the chart saved in your browser.
- Editing a shared chart keeps the address bar in sync with the edits, so the URL always matches the current chart.
- Loading a JSON file while viewing a shared chart leaves shared mode.
- Anyone with the link can read the chart. Do not put confidential information in a shared chart.

### JSON format

Saved charts are stored as plain JSON, making them easy to read, edit by hand or track with Git (although I am not sure why you would want to do that).

```json
{
  "version": 1,
  "baseDate": "2026-06-01",
  "days": 30,
  "cellW": 28,
  "tasks": [
    { "id": 1, "name": "Research", "start": 0, "dur": 5, "color": "#378ADD" },
    { "id": 2, "name": "Internship","start": 5, "dur": 7, "color": "#1D9E75" },
    { "id": 3, "name": "Write up", "start": 10, "dur": 14, "color": "#7F77DD" },
    { "id": 4, "name": "Review", "start": 26, "dur": 6, "color": "#D85A30",
      "segments": [ { "start": 26, "dur": 2 }, { "start": 30, "dur": 2 } ] }
  ]
}
```

`start` and `dur` are in days relative to `baseDate`. A split task also has a `segments` list of `start`/`dur` pairs (same unit); its `start` and `dur` cover the whole span from the first segment's start to the last segment's end. Files without `segments` load as before.

## Limitations

- No milestones
- No collaborative editing
- No task dependencies
- Shared links carry no view mode, zoom or today-line setting

## Already adopted by (or likely soon-to-be adopted by)

- Jackie Moon
- SpaceX (Planning Division)
- The Government of Paraguay
- The Czech Institute of Paleontology and Botany
- Michel from Bordeaux
- Some Microsoft employees (as an alternative to _Microsoft Project_)
- ...and more

Please open a PR if you would like your company to be included in this list.
