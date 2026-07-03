# rubiks-cube-solver
# Rubik's Cube Solver

A high-performance Rubik's Cube solver implemented in **C++**, featuring multiple cube representations, classical search algorithms, heuristic-based optimization using Pattern Databases, and webcam-based cube scanning with OpenCV.

The project was built to explore algorithm design, state-space search, optimization techniques, and computer vision while solving one of the most well-known combinatorial search problems.

---

## Features

- Multiple Rubik's Cube representations
  - 3D Array
  - 1D Array
  - Bitboard Representation

- Multiple solving algorithms
  - Breadth First Search (BFS)
  - Depth First Search (DFS)
  - Iterative Deepening DFS (IDDFS)
  - Iterative Deepening A* (IDA*)

- Pattern Database heuristic for faster search

- Efficient bit-level cube manipulation using bitboards

- Webcam-based cube scanner using OpenCV

- Modular and extensible architecture

---

## Project Structure

```
.
├── Databases/
│   └── Corner Pattern Database
│
├── Model/
│   ├── Cube Representations
│   ├── Move Logic
│   └── Pattern Database Interface
│
├── PatternDatabases/
│   ├── Corner Pattern Database
│   ├── Database Generator
│   ├── Nibble Array
│   └── Permutation Indexer
│
├── Scanner/
│   └── OpenCV Cube Scanner
│
├── Solver/
│   ├── BFS Solver
│   ├── DFS Solver
│   ├── IDDFS Solver
│   └── IDA* Solver
│
└── main.cpp
```

---

## Algorithms Implemented

### Breadth First Search (BFS)

Explores states level-by-level and guarantees an optimal solution for small search depths.

### Depth First Search (DFS)

Recursive depth-first exploration used primarily for experimentation and comparison.

### Iterative Deepening DFS (IDDFS)

Combines DFS memory efficiency with BFS completeness by repeatedly increasing search depth.

### Iterative Deepening A* (IDA*)

The primary solving algorithm.

IDA* combines:

- heuristic search
- iterative deepening
- low memory usage

to efficiently solve the Rubik's Cube search space.

---

## Pattern Database Heuristic

The solver uses a **Corner Pattern Database** as an admissible heuristic for IDA*.

The database stores precomputed distances for corner configurations, significantly reducing the number of explored states during search.

Advantages include:

- Faster solving
- Reduced search depth
- Admissible heuristic for optimal search
- Better scalability than uninformed search

---

## Cube Representations

The project implements multiple internal cube representations for comparison and optimization.

### 3D Array

A straightforward representation useful for visualization and debugging.

### 1D Array

A compact representation that simplifies move execution.

### Bitboard

A memory-efficient representation using 64-bit integers to encode cube state.

Benefits include:

- Reduced memory usage
- Fast bitwise operations
- Efficient state comparison
- Optimized hashing

---

## Cube Scanner

The project includes an OpenCV-based cube scanner that captures cube faces from a webcam.

The scanner:

- Opens a webcam feed
- Samples sticker colors
- Converts BGR to HSV
- Classifies sticker colors
- Builds the cube state for the solver

---

## Technologies Used

- C++
- STL
- CMake
- OpenCV
- Graph Search Algorithms
- Pattern Databases
- Bit Manipulation

---

## Building

### Prerequisites

- C++14 or later
- CMake
- OpenCV

### Build

```bash
mkdir build
cd build

cmake ..
make
```

Run:

```bash
./rubiks_cube_solver
```

---

## Learning Outcomes

This project provided hands-on experience with:

- Graph search algorithms
- Heuristic search (IDA*)
- Pattern Database optimization
- Bitboard data structures
- State-space modeling
- Object-oriented design in C++
- Computer vision using OpenCV
- Performance-oriented algorithm implementation

---

## Future Improvements

Possible future enhancements include:

- Full edge pattern database
- Two-phase solving algorithm
- Improved color calibration
- GUI visualization
- Move animation
- Performance benchmarking dashboard
- Parallel search implementation

---
