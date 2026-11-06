# Neon Snake

Neon Snake is a small, single-player Snake game that runs in a web browser. It is implemented as a self-contained HTML page with inline CSS and JavaScript; it does not require a framework, package installation, or a build step.

## Features

- A 25 × 25 grid drawn on an HTML canvas, with a responsive neon-style interface.
- Collect glowing orbs to grow the snake and earn one point per orb.
- A best-score display saved in the browser's local storage when storage is available.
- Increasing movement speed as the score rises, up to 1.9× the starting speed.
- The game ends when the snake hits a wall or its own body; the board does not wrap.
- Pause and resume controls, keyboard controls, and on-screen directional buttons on narrow screens.
- Light- and dark-color-scheme styling and reduced-motion preferences.

## Controls

| Action | Control |
| --- | --- |
| Start or play again | Select **Start game** / **Play again**, or press **Space** |
| Move | Arrow keys or **W**, **A**, **S**, **D** |
| Pause or resume | **Space**, **Escape**, or the in-game button |
| Move on a narrow screen | Tap the on-screen arrow buttons |

The snake cannot immediately reverse into the direction it is currently moving. The game starts when you select the start button, press Space, or use a direction key/button.

## Run locally

No dependencies need to be installed. Clone or download the repository, then serve its root directory with any static file server. For example, if Python is installed:

```sh
python -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) in a browser. The game page is `index.html`. Opening that file directly may also work, but using a local server provides a consistent browser origin for saving the best score.

## Requirements and storage

Use a modern browser with support for the HTML canvas 2D API (including `roundRect`), `requestAnimationFrame`, and JavaScript. No server-side component is used by the game. The best score is stored in browser local storage under the key `neon-snake-best`; it is local to the browser and site origin, is not synchronized between devices, and may not persist when storage is unavailable or cleared.

## Project structure

```text
.
├── index.html   # Game markup, styles, and gameplay logic
└── README.md    # Project documentation
```

## Gameplay notes

- The board is 25 cells wide and high. The snake starts with three segments.
- Each orb adds one point and increases the snake's length.
- Speed increases by 0.12× for each five points, starting at 1× and capped at 1.9×.
- Food is placed at a randomly selected unoccupied cell.

The game has no sound, network features, user accounts, or server-side score storage. There is no touch-swipe steering; use the on-screen buttons instead. The current implementation also has no special win state for filling the entire board.
