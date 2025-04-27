# Hungary regions guessing game

An interactive web game that challenges you to identify geographic areas on a map.  
Players can switch between two modes—guessing Budapest’s districts or Hungary’s regions—and even toggle a “blank map” (no labels) for extra difficulty.

Live demo: https://a1mirr.github.io/BudapestDistrictsGame

---

## Features

- Two game modes
  - **Budapest Districts**  
  - **Hungary Regions**
- “Blank Map” option (no labels) via base‐layer switcher
- 3 attempts per round
- On‐map feedback: wrong guesses turn red, correct one turns green
- Pure HTML/CSS/JavaScript; no backend required

---

## Repository Structure

```
.
├── index.html
├── Budapest_districts.json
├── Hungary_regions.json
└── README.md
```

- **index.html**  
  Main game page. Contains the map setup, UI controls, and game logic.
- **Budapest_districts.json**  
  GeoJSON file with Budapest district polygons and a `name` property.
- **Hungary_regions.json**  
  GeoJSON file with Hungary region polygons and a `name` property.
- **README.md**  
  Project overview, setup, and usage instructions.

---

## Getting Started

### Prerequisites

- A modern browser (Chrome, Firefox, Edge, Safari, etc.)
- No additional libraries or server required beyond what’s in this repo

### Running Locally

1. Clone the repo:  
   ```
   git clone https://github.com/a1mirr/BudapestDistrictsGame.git
   cd BudapestDistrictsGame
   ```
2. Open **index.html** in your browser:  
   - Double-click the file  
   - Or run a simple local HTTP server, e.g.:  
     ```
     npx http-server . -c-1
     ```
     Then browse to http://localhost:8080
---

## How It Works

1. **Map Initialization**  
   - Uses Leaflet to render an OpenStreetMap tile layer by default.
   - Adds a layer‐switcher control for “With Labels” vs. “Blank Map” (CartoDB's `light_nolabels`).

2. **Game Logic**  
   - Loads the selected GeoJSON (Budapest districts or Hungary regions).
   - Randomly picks one feature’s `name` (or `region_name`) as the **target**.
   - User has 3 attempts:
     - Clicking a polygon:  
       • Correct → highlight green + win message  
       • Incorrect → highlight red + remaining attempts  
   - On 0 attempts, highlights the correct polygon in green.

3. **Controls**  
   - **Mode Selector**: choose between districts or regions  
   - **Next**: start a new round with a new random target  
   - **Map Layer Switcher**: toggle base maps (labels vs. blank)
  
  ## License

[![License: CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/)

This work is licensed under a Creative Commons Attribution-NonCommercial 4.0 International License.  
You are free to:

• Share — copy and redistribute the material in any medium or format  
• Adapt — remix, transform, and build upon the material  

Under the following terms:

• Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made.  
• NonCommercial — You may not use the material for commercial purposes.  

No additional restrictions.  
See the full license text in [LICENSE](./LICENSE) or at  
https://creativecommons.org/licenses/by-nc/4.0/
