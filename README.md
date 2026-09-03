# Rubik's Cube Solver

A C++ project that models a Rubik's Cube and solves it using several search strategies, including depth-first search, breadth-first search, iterative deepening depth-first search, and IDA* with a corner pattern database.

## Overview

This repository explores multiple cube representations and solver approaches:

- 3D array cube representation
- 1D array cube representation
- Bitboard-based cube representation
- Search-based solvers in the `Solver` directory
- Pattern database generation utilities in `PatternDatabases`

The project is intended as a learning and experimentation codebase for cube solving algorithms, not as a polished production application.

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

- C++ compiler with C++14 support
- CMake 3.20 or newer
- Git Bash, PowerShell, or a terminal with access to the build tools

## Build

From the project root:

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

This produces an executable named `rubiks_cube_solver` (or a similar build artifact depending on the generator used).

## Run

From the build directory:

```bash
./rubiks_cube_solver
```

On Windows:

```powershell
.\rubiks_cube_solver.exe
```

## Important Note About the Database

The sample solver code in `main.cpp` contains a hard-coded database path:

```cpp
string fileName = "C:\\Users\\user\\CLionProjects\\rubiks-cube-solver\\Databases\\cornerDepth5V1.txt";
```

This path is machine-specific. To run the IDA* example successfully on your machine:

1. Update the value of `fileName` in `main.cpp` to point to a valid database file on your system.
2. If needed, generate or place a pattern database under `Databases/`.
3. Rebuild the project.

The repository contains a `Databases` folder, so a local path such as:

```cpp
string fileName = "Databases/cornerDepth5V1.txt";
```

may be more portable if you run from the project root.

## Solvers Included

- `DFSSolver` — depth-first search solver
- `BFSSolver` — breadth-first search solver
- `IDDFSSolver` — iterative deepening depth-first search
- `IDAstarSolver` — IDA* solver using a corner pattern database heuristic

## Example Usage

The `main.cpp` file contains commented examples for:

- testing cube transformations
- verifying equality and assignment semantics
- random shuffling
- BFS, DFS, IDDFS, and IDA* solving
- pattern database generation

These examples are useful as a reference for how the library is intended to be used.

## License

This project does not currently declare a license file. If you are using it in a repository or publishing code, check whether the original author requires attribution or publication constraints before distributing it.
