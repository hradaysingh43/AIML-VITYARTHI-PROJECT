# AIML-VITYARTHI-PROJECT
Project Bermuda: Intelligent Route Optimization System

A logic-driven pathfinding system designed to compute the most efficient tactical routes across a simulated and dynamically changing Bermuda map environment.

This project was developed as part of the Bring Your Own Project (BYOP) component for the Fundamentals of Artificial Intelligence and Machine Learning course. It combines symbolic reasoning (Prolog) with procedural scripting (Python) to demonstrate adaptive decision-making, constraint handling, and search-based optimization.

 AI Principles Implemented

The system is built to reflect core Artificial Intelligence concepts:

Knowledge Representation:
Instead of conventional Python data structures, the map is represented using First-Order Predicate Logic in SWI-Prolog. Nodes and connections are defined as static facts, while dynamic conditions such as threats are modeled using runtime rules.
Search & Intelligent Behavior:
The agent functions as a goal-based problem solver. It performs a complete Depth-First Search (DFS) over the state space, evaluates path costs, and applies an optimization layer to determine the most efficient route.
 System Design Overview

The project follows a modular architecture with clear separation of responsibilities:

Knowledge Engine (map_kb.pl)
Contains the logical representation of the environment and recursive rules for path exploration. Acts as the inference core.
Execution Layer (tactical_route.py)
A Python-based CLI that accepts user input and communicates with Prolog using the pyswip interface.
Dynamic Constraint Handling
Runtime conditions (e.g., enemy zones or blocked areas) are injected into the Prolog knowledge base using assertz. The system instantly updates its reasoning and recalculates a valid route avoiding those constraints.
 Installation Guide
Requirements:
Python 3.8 or above
SWI-Prolog (latest stable version)

Download from:
SWI-Prolog Official Site  SWI-Prolog Official.

 Important for Windows Users:
Ensure that the option "Add swipl to system PATH" is enabled during installation, otherwise Python-Prolog integration will fail.

Setup Steps:

1. Clone the Repository
```bash
git clone https://github.com/anuragtiwari8006-dev/Anurag-Tiwari-AI-ML-Vityarthi-Project/tree/main
cd Anurag-Tiwari-AI-ML-Vityarthi-Project
```

2. Install Dependencies
```bash
pip install -r requirements.txt
 Running the System
```
The application is entirely CLI-based and requires no graphical interface.

 Case 1: Basic Route Calculation

Finds the shortest route between two points without obstacles:
```bash
python tactical_route.py --start "Clock Tower" --end "Peak"
```
Output Example:
```bash

[>] Computing optimal route from 'Clock Tower' to 'Peak'...

[+] ROUTE FOUND
    Path: Clock Tower -> Peak
    Total Distance: 150 units
```
 Case 2: Route with Dynamic Constraints

Simulates obstacles such as enemy presence and restricted zones:
```bash
python tactical_route.py --start "Rim Nam Village" --end "Peak" --enemy "Clock Tower" --red_zone "Factory"
```
Output Example:
```bash
[!] Avoiding restricted area: Factory
[!] Enemy detected at: Clock Tower

[>] Computing optimal route from 'Rim Nam Village' to 'Peak'...

[+] ROUTE FOUND
    Path: Rim Nam Village -> Hangar -> Katulistiwa -> Bimasakti Strip -> Peak
    Total Distance: 825 units
    ```
 Project Structure
tactical_route.py — Handles user interaction and Prolog communication
map_kb.pl — Logical knowledge base and search rules
requirements.txt — Required Python packages (pyswip)
.gitignore — Excludes unnecessary files
project_report.md — Complete documentation and analysis
bermuda_map.png — Graphical representation of the map
 Developer

Created by: Hraday Singh Bisen
