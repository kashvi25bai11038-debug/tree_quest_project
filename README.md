# Tree Quest — BFS & DFS Algorithm Visualizer

> An interactive, browser-based visualizer that brings Breadth-First Search and Depth-First Search to life — step by step, node by node.


## What Is This?

**Tree Quest** is a zero-dependency, single-file web app that lets you watch BFS and DFS traversal algorithms execute on a 13-node binary tree — in real time, with full visual feedback.

Instead of staring at pseudocode or static diagrams, you can:

- **Watch** each node change state as the algorithm processes it
- **Track** the queue (BFS) or stack (DFS) live as it grows and shrinks
- **Step through** the algorithm one node at a time at your own pace
- **Compare** BFS and DFS side-by-side on the same tree

Built with a retro gaming aesthetic — glowing nodes, starfield background, arcade fonts, and particle effects — to make algorithm learning actually enjoyable.

---

## Features

| Feature | Description |
|---|---|
| **BFS Mode** | Breadth-First Search using a Queue (FIFO) — explores level by level |
| **DFS Mode** | Depth-First Search using a Stack (LIFO) — dives deep before backtracking |
| **Auto-Play** | Runs the full traversal automatically |
| **Step Mode** | Advance one node at a time for deliberate learning |
| **Speed Control** | Adjust playback speed from 100ms to 1200ms per step |
| **Live Queue/Stack** | See exactly what's in the frontier at every step |
| **Visited Order** | Track the traversal sequence as it builds |
| **Live Stats** | Step count, nodes visited, and queue size at a glance |
| **Particle Effects** | Visual burst when a node is activated |
| **Starfield Background** | Animated canvas starfield with CRT scanline overlay |
| **Responsive** | Works on desktop and mobile screens |

---

## Demo

### Node States

| Colour | Meaning |
|---|---|
| Dark / Dim border | **Unvisited** — not yet discovered |
| Cyan border + blue tint | **Queued / In Stack** — discovered, waiting to be processed |
| Yellow glow | **Active** — currently being processed |
| Green fill | **Visited** — fully explored |

### BFS vs DFS on the same tree

```
Traversal order — BFS:   A → B → C → D → E → F → G → H → I → J → K → L → M
Traversal order — DFS:   A → B → D → H → I → E → J → C → F → K → G → L → M
```

---

## Getting Started

### Requirements

- Any modern web browser (Chrome, Firefox, Edge, Safari)
- **No installation. No server. No dependencies.**

### Run it

**Option 1 — Download and open**
1. Download `index.html` (or clone this repo)
2. Double-click the file
3. It opens directly in your browser — that's it

**Option 2 — Clone the repo**
```bash
git clone file:///C:/Users/Gaurav/Desktop/AI%20ML/tree_quest.html
cd tree-quest
# Open index.html in your browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

**Option 3 — VS Code Live Server**
1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code
2. Right-click `index.html` → **Open with Live Server**
3. Auto-reloads whenever you save changes

> No `npm install`, no build step, no config files needed.

---

## How to Use

```
1. Open index.html in your browser
2. Select an algorithm — BFS or DFS — using the toggle buttons
3. Click PLAY to run automatically, or STEP to advance one node at a time
4. Watch the tree, queue panel, and visited order update in real time
5. Use the speed slider to slow down or speed up the animation
6. Click RESET to start over — then try the other algorithm!
```

### Controls

| Button | Action |
|---|---|
| `BFS` / `DFS` | Switch between algorithms (resets state) |
| `▶ PLAY` | Run the full traversal automatically |
| `⏭ STEP` | Process one node manually |
| `↺ RESET` | Reset all nodes to unvisited state |
| Speed Slider | Control auto-play delay (left = fast, right = slow) |

---

## Project Structure

```
tree-quest/
└── index.html        # The entire application — HTML, CSS, and JS in one file
```

That's the whole project. Everything lives in `index.html`:

- **HTML** — layout structure (canvas, sidebar, controls)
- **CSS** — all styling, animations, and the retro theme (CSS variables, keyframes)
- **JavaScript** — tree layout algorithm, BFS/DFS logic, Canvas rendering, particle system, starfield

---

## How It Works (Technical Overview)

### The Tree
A fixed 13-node binary tree (nodes A–M, 4 levels deep) is defined as a nested JavaScript object. A recursive layout algorithm computes display coordinates: leaf nodes are assigned sequential x-positions, and each internal node is centred over its children.

### BFS vs DFS — One Line of Difference
Both algorithms share the same `stepOnce()` function. The only difference is how the frontier is accessed:

```js
// BFS — Queue (FIFO): process the oldest item first
current = queue.shift();

// DFS — Stack (LIFO): process the newest item first
current = queue.pop();
```

### Rendering
The tree is drawn on an HTML5 `<canvas>` element. Each animation frame redraws all edges and nodes based on the current state object. Node glow effects use `ctx.shadowBlur` and `ctx.shadowColor`. A separate canvas renders the animated starfield via `requestAnimationFrame`.

### Node States
Each node holds one of four states: `idle → queued → active → visited`. These map directly to distinct visual styles applied during each canvas redraw.

---

## Concepts Demonstrated

- **Breadth-First Search (BFS)** — Queue data structure, FIFO, level-order traversal
- **Depth-First Search (DFS)** — Stack data structure, LIFO, pre-order traversal
- **Tree traversal** and the difference in resulting node visit orders
- **State machines** — each node transitions through defined states
- **Canvas API** — 2D drawing, glow effects, DPI scaling, animation loops

---


## Contributing

Contributions, suggestions, and improvements are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-idea`
3. Make your changes in `index.html`
4. Open a pull request with a clear description of what you changed and why

**Ideas for future improvements:**
- Let users build their own custom tree
- Add pre-order / in-order / post-order DFS variants
- Add a quiz mode (predict the next node before stepping)
- Show time and space complexity annotations
- Add sound effects for a full retro arcade experience

---

<p align="center"></p>
