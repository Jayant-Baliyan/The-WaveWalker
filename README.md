# The WaveWalker (BlackPearl)

Prototype web app built for **Smart India Hackathon (SIH) 2025** by **Team The WaveWalker**.  
The project focuses on **querying ARGO float / ocean (BGC) data using natural language**, visualizing marine trends, and exploring key parameters through an interactive UI.

> Entry point: `index.html`  
> Pages live in: `Code/`

---

## What’s inside this repository

This is a front-end–only project made with **HTML + TailwindCSS (CDN)** and Google fonts/icons.

### Main pages
- **Home / Landing:** `index.html`  
  Buttons/links:
  - `Code/working_sample.html` → **Search Data** (chat-style interface)
  - `Code/sample.html` → **View Sample** (static demo chat)
  - `Code/download.html` → **Download Data** (request form UI)
  - `Code/interactive.html` → **Ocean Data Explorer** (graphs + table)

### Visual assets (used by Ocean Data Explorer)
Located in `Code/`:
- `penninsular_india.png`
- `salinity_depth.jpg`
- `temperature.jpg`
- `oxygen.jpg`
- `ph.jpg`
- `nitrate.jpg`
- `pressure.jpg`

---

## Features

- **Landing page** with SIH project branding and quick navigation
- **Search Data (Chat UI)**: a chat-like interface that sends user queries to a configurable webhook
- **Sample Chat UI**: a static demonstration of what responses look like
- **Ocean Data Explorer**:
  - parameter switching (Salinity / Temperature / Oxygen / pH / Nitrate / Pressure)
  - graph image updates per parameter
  - example data table view
- **Download Data (UI)**:
  - a form to request access to oceanographic data (prototype form)

---

## How to run (local)

### Option 1: Open directly in browser
1. Download/clone this repo
2. Open `index.html` in your browser

### Option 2: Run using a local static server (recommended)
Using VS Code:
- Install **Live Server**
- Right click `index.html` → **Open with Live Server**

Or using Python:
```bash
python -m http.server 8000
```
Then open:
- http://localhost:8000/

---

## “Search Data” backend integration (N8N webhook)

`Code/working_sample.html` contains a configurable webhook URL:

- It currently uses:
  - `http://localhost:5678/webhook-test/7f74147d-cc07-4f9c-be64-c47d042ef8ab`

### To make chat work
1. Run an **n8n** workflow with a webhook trigger
2. Update the value of `N8N_WEBHOOK_URL` in `Code/working_sample.html`
3. Ensure your webhook returns JSON like:
```json
{ "response": "your reply text here" }
```

If the webhook is not running or not reachable, the UI will show a connection error message.

---

## Project structure

```text
.
├── index.html
├── README.md
└── Code/
    ├── working_sample.html
    ├── sample.html
    ├── download.html
    ├── interactive.html
    ├── penninsular_india.png
    ├── salinity_depth.jpg
    ├── temperature.jpg
    ├── oxygen.jpg
    ├── ph.jpg
    ├── nitrate.jpg
    ├── pressure.jpg
    └── temp
```

---

## Notes / Known gaps (prototype)
- Some links referenced by the landing page may not exist in the repo (for example, the landing page has a “Get API” card pointing to `Code/nlp.html`, but that file is not present).
- `Code/interactive.html` currently contains a **hardcoded local file path** for Home navigation (it points to a Windows `file:///D:/.../index.html`). You may want to change it to `../index.html` for portability.

---

## SIH Credits
- **Hackathon:** Smart India Hackathon (SIH) 2025  
- **Team:** The WaveWalker  
- **Prototype Name/UI Branding:** BlackPearl / BlackPearl AI

---
