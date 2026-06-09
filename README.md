# 📊 AlgoViz Pro — DAA Visualization Studio

<div align="center">

**Interactive Design & Analysis of Algorithms Visualizer**

*Group Project — My Contribution: Graph Algorithms Section*

[![Live Demo](https://img.shields.io/badge/🚀%20Live%20Demo-gameofalgos.netlify.app-brightgreen?style=for-the-badge)](https://gameofalgos.netlify.app/)
[![HTML5](https://img.shields.io/badge/Built%20With-HTML5%20%2B%20JS-orange?style=for-the-badge&logo=html5)](.)
[![Algorithms](https://img.shields.io/badge/Algorithms-40%2B-blue?style=for-the-badge&logo=buffer)](.)
[![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-green?style=for-the-badge)](.)
### 🌐 [https://gameofalgos.netlify.app/](https://gameofalgos.netlify.app/)

</div>

---

## 📌 About

**AlgoViz Pro** is a fully interactive, browser-based visualizer for 40+ algorithms covered in Design and Analysis of Algorithms. Built as a group academic project, it allows students to step through algorithms with animated visualizations, view pseudocode, analyze time/space complexity, and compare approaches side by side.

Zero dependencies. Zero setup. Just open in a browser — or visit the live deployment at **[gameofalgos.netlify.app](https://gameofalgos.netlify.app/)**.

---

## 🧩 My Contribution — Graph Algorithms Section

I was solely responsible for designing, implementing, and animating the entire **Graph Algorithms** section of this project. This includes:

### Algorithms I Built

| Algorithm | Category | Time Complexity | Space |
|-----------|----------|----------------|-------|
| **BFS** (Breadth-First Search) | Graph Traversal | O(V + E) | O(V) |
| **DFS** (Depth-First Search) | Graph Traversal | O(V + E) | O(V) |
| **Dijkstra's Algorithm** | Shortest Path | O((V+E) log V) | O(V) |
| **Bellman-Ford** | Shortest Path | O(VE) | O(V) |
| **Floyd-Warshall** | All-Pairs Shortest Path | O(V³) | O(V²) |
| **Prim's Algorithm** | Minimum Spanning Tree | O(E log V) | O(V) |
| **Kruskal's Algorithm** | Minimum Spanning Tree | O(E log E) | O(V) |
| **Topological Sort** | DAG Ordering | O(V + E) | O(V) |

### What I Implemented for Each Algorithm

- **Interactive Canvas Visualization** — nodes, directed/undirected edges, weighted graph rendering using HTML5 Canvas
- **Step-by-step animation** — color-coded states (unvisited → visiting → visited → path found)
- **Live queue/stack display** — shows BFS queue and DFS stack updating in real time
- **Distance table** — for Dijkstra and Bellman-Ford, shows distance array updating at each step
- **MST highlighting** — for Prim's and Kruskal's, highlights selected edges as the spanning tree builds
- **Adjacency matrix view** — Floyd-Warshall shows the full V×V matrix updating across all iterations
- **Custom graph input** — users can add/remove nodes and edges, set weights, switch between directed and undirected
- **Pseudocode panel** — syntax-highlighted pseudocode with the active line highlighted during animation
- **Complexity card** — best/average/worst time and space complexity displayed per algorithm
- **Algorithm steps explanation** — plain-English walkthrough of each step

---

## 🗂 Full Algorithm Coverage

The complete project covers 8 categories:

| Category | Algorithms |
|----------|-----------|
| **Sorting** | Bubble, Selection, Insertion, Merge, Quick, Heap, Counting, Radix |
| **Searching** | Binary Search, Linear Search, Jump Search, Interpolation |
| **Graph** ⬅ *my section* | BFS, DFS, Dijkstra, Bellman-Ford, Floyd-Warshall, Prim's, Kruskal's, Topological Sort |
| **Dynamic Programming** | 0/1 Knapsack, LCS, LIS, Matrix Chain, Coin Change, Edit Distance |
| **Trees** | BST Insert/Delete/Search, AVL Rotations, Heap operations |
| **Greedy** | Activity Selection, Fractional Knapsack, Huffman Coding, Job Sequencing |
| **Divide & Conquer** | Merge Sort, Quick Sort, Strassen's, Max-Min, Binary Search |
| **Data Structures** | Linked List, Stack, Queue, Hash Table |

---

## 🚀 How to Run

### Option 1 — Live Demo (recommended)
Visit **[https://gameofalgos.netlify.app/](https://gameofalgos.netlify.app/)** — no setup needed.

### Option 2 — Run Locally
```bash
# Clone the repo
git clone https://github.com/SuryaSashank09/AlgoViz-Pro.git

# Just open in browser — no server or build step needed
# Double-click index.html or:
open index.html
```

Works in Chrome, Firefox, Edge, Safari.

---

## 🛠 Tech Stack

| Tech | Usage |
|------|-------|
| HTML5 Canvas | Graph node/edge rendering and animation |
| Vanilla JavaScript | All algorithm logic, animation engine, UI state |
| CSS3 | Layout, animations, responsive design |
| Three.js (r128) | 3D elements in select visualizations |
| Google Fonts | Space Grotesk + JetBrains Mono + Playfair Display |
| Netlify | Deployment and hosting |

No React. No npm. No build step. Pure browser-native code.

---

## 📐 Graph Section — Technical Details

### Canvas Rendering Engine

The graph section uses a custom canvas renderer built from scratch:

```javascript
// Node layout using circular positioning
function placeNodes(count) {
  const cx = canvas.width / 2, cy = canvas.height / 2, r = 130;
  return Array.from({ length: count }, (_, i) => ({
    x: cx + r * Math.cos((2 * Math.PI * i) / count),
    y: cy + r * Math.sin((2 * Math.PI * i) / count),
    id: i
  }));
}
```

### Frame-Based Animation System

Each algorithm generates a sequence of frames — snapshots of state — played back at adjustable speed:

```javascript
// BFS frame generation
function bfsFrames(graph, start) {
  const frames = [], visited = new Set(), queue = [start];
  while (queue.length) {
    const node = queue.shift();
    frames.push({ visited: new Set(visited), current: node, queue: [...queue] });
    for (const neighbor of graph[node]) {
      if (!visited.has(neighbor)) { visited.add(neighbor); queue.push(neighbor); }
    }
  }
  return frames;
}
```

---

## 👥 Team

| Section | Owner |
|---------|-------|
| Graph Algorithms | **Surya Sashank** (me) **Meher Kamal**|
| Sorting Algorithms | **K.Naveen** **P.Maheedhar** |
| Dynamic Programming | **S.Nikhil** |
| Greedy & Divide & Conquer | **Hujith Reddy**  **D.BALAJI**|

---
