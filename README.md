# Conway's Game of Life

A lightweight, browser-based implementation of [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) — no dependencies, no build step, just a single HTML file.

![Game of Life](https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif)

---

## What is Conway's Game of Life?

Conway's Game of Life is a classic **cellular automaton** devised by mathematician John Horton Conway in 1970. It's a zero-player game — you set up an initial state and watch it evolve according to four simple rules:

1. A live cell with **fewer than 2** live neighbours dies (underpopulation)
2. A live cell with **2 or 3** live neighbours survives
3. A live cell with **more than 3** live neighbours dies (overpopulation)
4. A dead cell with **exactly 3** live neighbours becomes alive (reproduction)

These rules produce surprisingly complex and beautiful emergent behaviour from almost any starting configuration.

---

## Features

- 🎨 **Colour-coded cells** — cells are coloured based on their grid position for easy visual tracking
- ⚡ **Timestamp-based simulation speed** — smooth, consistent evolution at all speeds and grid sizes
- 🎲 **Random spawn** — populate the grid instantly with a configurable number of random cells
- 📐 **Multiple grid sizes** — choose between 20×20, 30×30, 40×40, and 50×50
- 📊 **Live stats** — tracks current generation count and number of live cells
- 🔁 **Wrapping grid** — the edges wrap around, so cells on one side interact with cells on the other

---

## Getting Started

No installation or setup required.

1. Download or clone this repository
2. Open `index.html` in any modern browser
3. Click **Random Spawn** to place cells, then **Start** to watch them evolve

```bash
git clone https://github.com/your-username/game-of-life.git
cd game-of-life
open index.html
```

---

## Controls

| Control | Description |
|---|---|
| **Grid Size** | Sets the number of columns (20, 30, 40, or 50) |
| **Speed** | Adjusts simulation speed from slow (1) to fast (10) |
| **Random Cells** | Number of cells to place on the next random spawn |
| **Random Spawn** | Clears the grid and places cells randomly |
| **Start / Pause** | Starts or pauses the simulation |
| **Reset** | Stops the simulation and clears the grid |

---

## How It Works

The simulation runs inside a `requestAnimationFrame` loop. Rather than tying step frequency to the frame counter (which caused inconsistent behaviour across grid sizes), evolution is driven by **elapsed time** — a step only fires once a minimum interval has passed based on the current speed setting. This keeps the simulation smooth and predictable at any grid size.

The grid wraps at its edges using modulo arithmetic, so the world is effectively a torus.

---

## Browser Support

Works in any modern browser that supports the Canvas API and `requestAnimationFrame` — Chrome, Firefox, Safari, and Edge.

---

## License

MIT
