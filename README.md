# ODE Solver: Euler & Improved Euler

This was made for MA331 class Differential Equations in Washburn University and is meant to work offline. A lightweight, single-file web app for solving first-order ODEs **dy/dx = f(x, y)** using **Euler’s method** and **Improved Euler (Heun’s method)**. No backend, no login, works offline.

## How to run

1. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
2. Enter your equation, initial conditions, step size, and final x.
3. Click **Solve**. View the table and graph; use **Export table as CSV** if needed.

## How to distribute to other people

You only need to share **`index.html`**. No server or install required.

**Option 1: Send the file**
- Email, USB, or file share (OneDrive, Google Drive, etc.) the `index.html` file.
- Recipients double‑click it (or right‑click → Open with → browser) to run it.
- **First run:** They need internet so the app can load math.js and Chart.js from the CDN. After that, the browser may cache them for offline use.

**Option 2: Put it online (share a link)**
- Upload `index.html` to any static host, for example:
  - **GitHub Pages:** Create a repo, push `index.html`, enable Pages in Settings. URL will be like `https://yourusername.github.io/repo-name/`.
  - **Netlify / Vercel:** Drag and drop the folder or connect a repo; they give you a URL.
- Share that URL; anyone can open it in a browser.

**Option 3: Zip the folder**
- Zip the folder that contains `index.html` (and optionally this README).
- Share the zip; others unzip and open `index.html` in a browser.

## Equation input

- **Format:** `dy/dx = f(x, y)`. Type only the right-hand side in the equation box.
- **Examples:**
  - `x - y`
  - `-(sqrt(y/x) + sin(x)) / (sqrt(x/y) + cos(y))`
  - `x^2 + y^2`
  - `exp(-x) * cos(y)`
- **Allowed:** `x`, `y`, `+`, `-`, `*`, `/`, `^`, `sqrt`, `sin`, `cos`, `tan`, `log`, `exp`, parentheses. Angles in **radians**.
- **Safety:** Only math expressions are evaluated; no code execution.

## Methods

- **Euler:** \( y_{n+1} = y_n + h\,f(x_n, y_n) \)
- **Improved Euler (Heun):** \( k_1 = f(x_n,y_n),\quad k_2 = f(x_n+h,\, y_n+h\,k_1),\quad y_{n+1} = y_n + \tfrac{h}{2}(k_1+k_2) \)

## Features

- Side-by-side table: **n | x | y (Euler) | y (Improved Euler)** with optional **k₁, k₂** columns.
- Final approximate values and optional **|Δy|** (difference between the two methods).
- Graph: both solutions on one plot; **scroll to zoom**, **drag to pan**, **double-click to reset**.
- **Export table as CSV**.
- **Dark/light theme** toggle (top-right); preference is saved in `localStorage`.

## Tech

- Pure HTML/CSS/JavaScript (single file).
- [math.js](https://mathjs.org/) for safe expression parsing.
- [Chart.js](https://www.chartjs.org/) + [chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/latest/) for the plot.

For full offline use, save the page and open from disk; for zoom/pan to work offline, the Chart.js and zoom plugin scripts must be loaded (e.g. from a local copy or cached after first load).
