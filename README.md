# Tactical Map Architect Pro v4.6.6

Architect Pro is a high-performance topological design suite built for competitive multiplayer level designers. By treating a level as a non-planar graph, the tool allows designers to solve flow and balance issues mathematically before a single piece of 3D geometry is ever placed.

Featuring an Iterative AI Search Engine, the tool simulates thousands of map variations per batch, discarding any layout that fails to meet strict professional Search Guards—including site-strict CT Advantage ratios and node-disjoint strategic entry lanes.

## Key Features

* AI Optimization Loop: Automated generation of thousands of permutations to find mathematically balanced ideal layouts.
* Tactical Entry Analysis: Implements node-disjoint pathfinding to ensure that lanes (A, B, and Mid) are truly unique and strategically separated by removing entry chokepoints during the search.
* The Golden Ratio Guard: Strict per-site validation ensuring defenders reach objectives 15-35% faster than attackers.
* Normalized Rotation Tension: A scale-independent metric for rotation timing, calculated as the ratio between site-to-site travel and average rush time.
* Recursive Pruning Engine: Automatically shaves dead-end branches back to the nearest junction to enforce circuit-based tactical flow.
* Real-Time Persistence: Move rooms in 3D space with integrated gizmos; the logic array and analysis dashboard update frame-by-frame with zero snap-back.
* Verticality Weighting: Configurable Z-axis penalties to simulate the physical slowdown of climbing ladders and stairs.

---

## The Search Guards

The engine uses a hierarchy of mathematical constraints to distinguish a competitive level from a random maze.

| Guard Name | Metric | Target Value |
| :--- | :--- | :--- |
| CT Advantage | T_ct / T_t | 0.70 to 0.85 |
| Rotation Tension | T_rot / T_rush | 120% to 180% |
| Lane Count | Node-Disjoint Entries | >= 3 Lanes |
| Connectivity | BFS / Union-Find | Fully Connected Graph |
| Pruning | Degree Check | 0 Dead-ends (Excluding Spawns) |

---

## Interaction Guide

### 1. Generation and Seeding
Set your Skeleton Density and Topological Bias. The engine uses an over-seeding algorithm to account for node loss during the pruning phase, ensuring your minimum complexity requirements are always met.

### 2. Manual Editing
* Click: Select an area or hallway to inspect metadata in the selection panel.
* 3D Gizmos: Drag the arrows to relocate rooms. Changes are saved instantly to the underlying simulation data.
* Shift + Click: Select a node, then shift-click another to toggle a connection.
* Alt + Click: Place a new node at the current cursor position on the tactical grid.

### 3. AI Optimization
Click Search for Ideal Maps. The AI will begin an iterative batch process. The analysis dashboard will update whenever a map with a higher fitness rank (0-100 score) is discovered.

---

## Technical Stack

* Engine: Three.js (WebGL)
* Pathfinding: Custom Dijkstra implementation with incursion penalties and site-influence weighting.
* Topology: Graph theory (node-disjoint paths and betweenness centrality).
* UI: CSS3 blur-filters and real-time DOM data-binding.

---

## Analysis Dashboard
The scrollable dashboard on the right provides a command center for your map. It compares your current actual values against your settings panel targets in real-time. If a manual edit breaks a search guard (such as making a rotation too fast or creating a dead-end), the dashboard metrics will instantly turn red.

---

"The goal of a tactical map isn't to look pretty—it's to be fair. Architect Pro ensures the math is right before the art begins."
