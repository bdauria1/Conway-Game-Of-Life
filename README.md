# Conway's Game of Life

This project is an implementation of [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) using React. The Game of Life is a cellular automaton devised by mathematician John Conway. It is a zero-player game, meaning that its evolution is determined by its initial state, requiring no further input from human players.

## Features

- **Interactive Grid**: Users can click on individual cells to toggle their state (alive or dead) and watch the game evolve.
- **Customizable Speed**: Adjust the speed of each iteration (generation) with a simple input field.
- **Start/Stop Game**: Controls to start and stop the simulation.
- **Randomize Board**: Fill the board with random live cells.
- **Clear Board**: Reset the board to an empty (all cells dead) state.
- **Pattern Loading**: Load predefined patterns like the *glider* onto the board.

## Getting Started

### Prerequisites

Make sure you have Node.js and npm installed on your machine. You can download Node.js [here](https://nodejs.org/).

### Installation

1. Clone this repository:

```bash
git clone https://github.com/your-username/game-of-life.git
cd game-of-life
```

2. Install dependencies:

``` bash
npm installl
```

3. Start the development server:

```bash
npm start
```

## Usage

Once the app is running, you'll see a grid representing the game board. Each cell can either be alive (colored) or dead (empty). Below the grid, you will find controls for interacting with the game.

### Controls

### Game Rules

The game evolves according to the following rules:
1. Any live cell with fewer than two live neighbors dies (underpopulation).
2. Any live cell with two or three live neighbors lives on to the next generation.
3. Any live cell with more than three live neighbors dies (overpopulation).
4. Any dead cell with exactly three live neighbors becomes a live cell (reproduction).

### Components
Game.js
* __Board Setup__: The board is dynamically created based on the given width and height.
* __User Interaction__: Users can click cells to toggle their state.
* __Game Logic__: Handles running the game iteration, calculating neighbors, and applying the rules of Conway's Game of Life.
* __Pattern Loading__: Predefined patterns such as the glider can be loaded into the board.

Cell.js

A reusable React component that represents a single cell on the game board. The component takes its position (x, y) as props and is styled according to its state (alive or dead).

### CSS (Game.css)
Basic styling for the game board, cells, and controls. Includes hover effects and transitions for visual feedback.

## How to add New Patterns

You can add more patterns to the game by updating the loadPattern function in Game.js. Each pattern should be defined as an array of coordinates, where each coordinate corresponds to the position of a live cell.

Example of adding a Pulsar pattern:
```javascript
pulsar: [
    [2, 0], [3, 0], [4, 0], [8, 0], [9, 0], [10, 0],
    [0, 2], [5, 2], [7, 2], [12, 2], 
    // ... (add more coordinates)
]
```
After defining the pattern, add a new button in the render method:

```jsx
<button className="button" onClick={() => this.loadPattern('pulsar')}>Load Pulsar</button>
```