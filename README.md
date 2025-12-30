# 🏘️ GitVille - GitHub Stargazer City

[![GitVille Banner](https://placehold.co/1200x400/81c784/ffffff?text=GitVille+Isometric+World)](https://addressmehari.github.io/GitVille/)

> **⭐️ Star this repository to get your own house in the city!**
>
> GitVille is a creative visualization of this repo's stargazers. Every star automatically builds a unique house in an infinite, interactive isometric world.
>
> **[👉 Visit the Live City](https://addressmehari.github.io/GitVille/)**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![Website](https://img.shields.io/website?url=https%3A%2F%2Faddressmehari.github.io%2FGitVille%2F&label=Live%20Demo&up_message=online&style=flat-square)](https://addressmehari.github.io/GitVille/)

---

## 📖 Table of Contents
- [✨ Features](#-features)
- [📸 Gallery](#-gallery)
- [How It Works](#-how-it-works)
- [🚀 Quick Start](#-quick-start)
- [🎮 Controls](#-controls)
- [⚙️ Configuration](#-configuration)
- [🤖 Automations](#--automations)

---

## ✨ Features

- **Isometric Rendering**: A custom-built 2:1 isometric engine using HTML5 Canvas.
- **Dynamic World**: The city grows as the repository gets more stars.
- **Living Environment**:
  - 🌤️ **Day/Night Cycles**: Automatic transitions affecting lighting and shadows.
  - 🌧️ **Weather System**: Particle-based rain and environmental effects.
  - 💨 **Procedural Vegetation**: Grass, flowers, and trees that sway in the wind.
  - ☁️ **Cloud System**: Moving clouds casting shadows on the ground.
  - 🚶 **NPCs**: Tiny inhabitants wandering the streets.
- **Interactive**: Zoom, pan, and inspect houses.

---

## 📸 Gallery

<p align="center">
  <img src="images/1.jpeg" width="45%" />
  <img src="images/2.jpeg" width="45%" />
  <img src="images/3.jpeg" width="45%" />
  <img src="images/4.jpeg" width="45%" />
  <img src="images/5.png" width="45%" />
  <img src="images/6.png" width="45%" />
</p>

---

## 🔍 How It Works

GitVille bridges the gap between GitHub data and visual art. Here is the flow of data:

```mermaid
graph TD
    A[GitHub API] -->|Fetch Stargazers| B(fetch_stargazers.py)
    B -->|Generate Layout| C{Data Files}
    C -->|houses.json| D[Frontend App]
    C -->|roads.json| D
    E[world.py] -->|Update State| F[world.json]
    F --> D
    D -->|Render| G((Canvas))
```

1.  **Data Fetching**: The `fetch_stargazers.py` script pulls the latest stargazers.
2.  **Layout Generation**: It calculates grid positions, organizing houses into a city layout with roads.
3.  **State Management**: `world.py` manages environmental state (weather, time of day).
4.  **Rendering**: The browser loads the JSON data and `script.js` renders the isometric world.

---

## 🚀 Quick Start

<details>
<summary><strong>📦 Installation & Setup (Click to expand)</strong></summary>

1.  **Clone the repository**
    ```bash
    git clone https://github.com/Addressmehari/GitVille.git
    cd GitVille
    ```

2.  **Run the Frontend**
    Since this is a static site, you can use any static file server.
    ```bash
    # Using python
    python -m http.server 8000
    
    # OR using npx
    npx serve .
    ```
    Open `http://localhost:8000` in your browser.

</details>

<details>
<summary><strong>🐍 Python Backend Setup (Click to expand)</strong></summary>

If you want to regenerate the city data locally:

1.  **Install Dependencies**
    *(Make sure you have a `requirements.txt` or install manually)*
    ```bash
    pip install requests
    ```

2.  **Run the Generator**
    ```bash
    # Usage: python fetch_stargazers.py <owner/repo> <limit>
    python fetch_stargazers.py Addressmehari/GitVille 100
    ```

</details>

---

## 🎮 Controls

| Action | Mouse | Touch |
| :--- | :--- | :--- |
| **Pan** | Click & Drag | Swipe |
| **Zoom** | Scroll Wheel | Pinch |
| **Interact** | Left Click on House | Tap on House |

---

## ⚙️ Configuration

You can manually tweak the world state by editing `world.json` or using the helper script.

<details>
<summary><strong>🌍 World State Commands</strong></summary>

Use `world.py` to toggle environmental effects:

```bash
# Randomize Weather (Rain/Clear)
python world.py weather

# Toggle Day/Night
python world.py daynightcycle
```

The frontend will automatically reflect these changes on the next reload (or if configured to poll).

</details>

---

## 🤖 Automations

This repository includes GitHub Actions to keep the city alive:

- **Update Stargazers**: Runs regularly to fetch new stars and expand the city.
- **Weather Cycle**: Changes the weather periodically to keep the view dynamic.
- **Day/Night Cycle**: Synchronizes the visual theme with scheduled times.

---



<p align="center">
  Made with ❤️ for the Open Source Community
</p>
