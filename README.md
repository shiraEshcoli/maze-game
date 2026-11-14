# Maze Game Application

A full-stack desktop application built in Java, featuring a core library for maze generation, advanced pathfinding algorithms, a multithreaded client-server architecture, and a rich JavaFX graphical interface.

**Developed by Shira Eshcoli** — Information Systems Engineering Student at Ben-Gurion University of the Negev. 
*(Originally built as a comprehensive project for the Advanced Software Systems Development course).*

## My Core Contributions & Focus Areas

*   **Multithreaded Client-Server Architecture:** Designed and implemented a robust server layer utilizing thread pools to handle concurrent client requests for maze generation and solving. Engineered a caching mechanism to save solved mazes to disk, significantly reducing redundant computations.
*   **Algorithmic Pathfinding & Generation:** Developed custom thread-safe algorithms for maze generation. Implemented a highly optimized `BestFirstSearch` algorithm utilizing a priority queue for cost-effective pathfinding (including diagonal movements), alongside standard `BFS` and `DFS` using the **Strategy** pattern.
*   **Data Compression:** Built a custom Run-Length Encoding (RLE) compression algorithm using the **Decorator pattern** (`MyCompressorOutputStream` / `MyDecompressorInputStream`) to shrink maze data, optimizing network transmission and file storage.
*   **Frontend & MVVM Architecture:** Built the interactive desktop GUI in **JavaFX** implementing a strict **MVVM (Model-View-ViewModel)** architecture. Developed a custom reusable maze board widget (`Canvas` extension) completely decoupled from the backend logic, driven by data-binding.
*   **Software Engineering Principles:** Enforced strict **SOLID** principles and integrated structural design patterns (Strategy, Adapter, Decorator) to ensure a highly scalable and maintainable object-oriented codebase.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Java 15+** | Core language & Multithreading |
| **JavaFX** | Desktop GUI (Part C) |
| **Maven** | Dependency management |
| **Log4j2** | Server-side logging |
| **JUnit 5** | Unit testing |
| **Design Patterns**| Strategy, Adapter, Decorator, MVVM |

---

## Repository Structure

This repository contains two interconnected modules, organized for clean separation of concerns:
maze-game/
├── part-a-b/       Core backend library: algorithms, RLE compression, client-server networking
└── part-c-javafx/  Frontend desktop game: JavaFX GUI built on MVVM architecture (Maven)
> **IDE Setup Note:** For optimal configuration, open each part as its **own** project in IntelliJ (`File → Open` on `part-a-b` or `part-c-javafx`) rather than opening the root folder. 

## Features in Action

- **Custom Generation:** Generate mazes with user-chosen dimensions (optimized to build a 1000×1000 maze in under a minute).
- **Gameplay:** Play the maze manually using the keyboard (including diagonal movements) or drag the character with the mouse.
- **Real-Time Solving:** Request a solution that is dynamically drawn over the maze while you keep playing.
- **State Management:** Save the current maze state to disk and load saved mazes losslessly.
- **UI/UX:** Zooming controls (`Ctrl + scroll`), background music during play and solving phases, and a fully resizable window handling concurrent server activity logged via Log4j2.

## How to Run

1. Open `part-a-b` and `part-c-javafx` as separate projects in your IDE.
2. In `part-a-b`, navigate to the `test` package and run `RunCommunicateWithServers` to start the backend threading servers.
3. In `part-c-javafx` (Maven project), run the JavaFX application's main class (`HelloApplication`) to launch the GUI.
