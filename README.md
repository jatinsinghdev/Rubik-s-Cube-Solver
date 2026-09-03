# Rubik's Cube Solver

A C++ project that models a Rubik's Cube and solves it using multiple search strategies, including **DFS, BFS, IDDFS, and IDA*** with a **corner pattern database heuristic**.

## Overview

This repository explores different approaches to representing and solving a Rubik's Cube:

* 3D array cube representation
* 1D array cube representation
* Bitboard-based cube representation
* Multiple search-based solvers in the `Solver` directory
* Corner pattern database generation and heuristic utilities in `PatternDatabases`

The project is primarily intended for learning and experimentation with **search algorithms, cube representations, and heuristic-based optimization**.

## Tech Stack

* **Language:** C++
* **Build System:** CMake
* **Standard:** C++14
* **Algorithms:** DFS, BFS, IDDFS, IDA*
* **Heuristics:** Corner Pattern Database

## Project Structure

```text
.
├── CMakeLists.txt
├── main.cpp
├── Databases/
├── Model/
│   ├── RubiksCube.cpp
│   ├── RubiksCube.h
│   ├── RubiksCube1dArray.cpp
│   ├── RubiksCube3dArray.cpp
│   ├── RubiksCubeBitboard.cpp
│   └── PatternDatabase/
├── PatternDatabases/
│   ├── CornerDBMaker.cpp
│   ├── CornerDBMaker.h
│   ├── CornerPatternDatabase.cpp
│   ├── CornerPatternDatabase.h
│   ├── NibbleArray.cpp
│   ├── PatternDatabase.cpp
│   └── ...
├── Solver/
│   ├── BFSSolver.h
│   ├── DFSSolver.h
│   ├── IDAstarSolver.h
│   └── IDDFSSolver.h
└── README.md
```

## Requirements

* C++ compiler with C++14 support
* CMake 3.20 or newer
* Git Bash, PowerShell, or another terminal with access to the build tools

## Build

From the project root:

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

This builds the Rubik's Cube solver executable.

## Solvers Included

* `DFSSolver` — Depth-First Search solver
* `BFSSolver` — Breadth-First Search solver
* `IDDFSSolver` — Iterative Deepening Depth-First Search solver
* `IDAstarSolver` — IDA* solver using a corner pattern database heuristic

## Example Usage

The `main.cpp` file contains commented examples for:

* testing cube transformations
* verifying equality and assignment semantics
* randomly shuffling the cube
* solving using BFS, DFS, IDDFS, and IDA*
* generating the corner pattern database

These examples provide a reference for using the cube models and solver implementations.

## Purpose

This project was developed to explore how **different state representations, search strategies, and heuristics** affect Rubik's Cube solving performance.



