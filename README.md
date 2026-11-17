# ♟️ The Inherited Crown

**A Java-based Chess Game demonstrating Object-Oriented Programming concepts through an interactive graphical interface and LAN multiplayer functionality.**

The Inherited Crown is a desktop chess application developed using Java. It provides an interactive chessboard, player customization, optional timers, and LAN-based multiplayer functionality.

The project focuses on applying core Object-Oriented Programming principles, modular software design, GUI development, and network communication.

---

## 📌 Project Overview

The application provides a graphical chess environment where players can configure their game settings, play chess, and connect with another player over a Local Area Network (LAN).

The project is organized into separate classes for chessboard management, graphical interface, game configuration, and network communication, promoting modularity and separation of responsibilities.

## ✨ Features

- **Interactive Chessboard:** Graphical 8×8 chessboard with recognizable chess pieces.
- **LAN Multiplayer:** Host or join a chess game using an IP address over the same local network.
- **Player Customization:** Configure names for White and Black players.
- **Timer System:** Optional countdown timer with configurable time per player.
- **Move Validation:** Validates basic movement rules for all six chess piece types.
- **Visual Feedback:**
  - Highlights the selected chess piece.
  - Highlights possible destinations.
  - Uses different colors for regular moves and captures.
  - Indicates the active player's turn.
- **Game Controls:** Start a new game or return to the main menu.

**Note:** The local two-player menu option is currently inactive. The available multiplayer mode uses LAN connectivity.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Java SE | Core programming language |
| Java Swing | Graphical User Interface |
| Java AWT | Graphics, layouts, colors and event handling |
| Java Sockets | LAN-based multiplayer communication |
| Multithreading | Handling network communication concurrently |
| Visual Studio Code | Development environment |

## 🧠 Object-Oriented Programming Concepts

This project demonstrates the following OOP concepts:

### 1. Classes and Objects

The application is divided into multiple classes, each representing a specific responsibility.

Examples:
- `ChessBoard` – Represents the chessboard and manages game state.
- `ChessGUI` – Represents the graphical game interface.
- `GameSettings` – Stores player and game configuration.
- `NetworkManager` – Handles network communication.

Objects of these classes interact to provide the complete application functionality.

### 2. Encapsulation

Encapsulation is implemented by restricting direct access to internal data using private attributes and providing controlled access through public methods.

Examples:
- `ChessBoard` encapsulates the board state and current player's turn.
- `GameSettings` encapsulates player names, timer settings, and game mode.
- Getter and setter methods provide controlled access to configuration data.

### 3. Abstraction

Abstraction is achieved by separating implementation details from the operations exposed to other classes.

Examples:
- `movePiece()` provides an interface for moving chess pieces without exposing the complete validation logic.
- `NetworkManager` hides socket communication details behind methods such as `sendMove()` and `close()`.
- Helper methods separate movement validation, board initialization, and GUI operations.

### 4. Inheritance

Inheritance is demonstrated through Java's built-in classes.

Examples:
- `MainMenu` extends `JFrame`.
- `ChessGUI` extends `JFrame`.
- `NetworkManager` extends `Thread`.

This allows the application to reuse existing functionality and extend the behavior of parent classes.

### 5. Polymorphism

Polymorphism is demonstrated through method overriding and interface-based event handling.

Examples:
- `NetworkManager` overrides the `run()` method inherited from `Thread`.
- Swing event listeners handle user interactions through callback implementations.

### 6. Constructors

Constructors initialize objects and establish their initial state.

Examples:
- `ChessBoard()` initializes the chessboard and player turn.
- `GameSettings()` initializes default game settings.
- `ChessGUI(GameSettings settings, String hostIp)` initializes the game interface and its associated components.
- `NetworkManager(boolean isHost, ChessGUI gui)` initializes network configuration.

### 7. Relationships Between Classes

The project demonstrates different object relationships:

- **Association:** `NetworkManager` maintains a reference to `ChessGUI` to communicate received moves.
- **Aggregation / Has-a relationship:** `ChessGUI` receives and maintains a reference to the externally created `GameSettings` object.
- **Composition-like ownership:** `ChessGUI` creates and maintains its own `ChessBoard` instance as part of the game interface lifecycle.

These relationships allow different components to collaborate while maintaining separate responsibilities.

---

## 🏗️ Class Structure

The project consists of the following Java classes:

| Class | Responsibility |
|---|---|
| `ChessGame.java` | Main entry point of the application. Initializes the GUI and launches the main menu. |
| `MainMenu.java` | Provides the welcome screen, player customization, timer configuration, and game mode selection. |
| `ChessGUI.java` | Manages the chessboard interface, player interactions, timers, and game controls. |
| `ChessBoard.java` | Maintains the chessboard state, validates piece movements, and manages turns. |
| `GameSettings.java` | Stores player names, timer preferences, and network game configuration. |
| `NetworkManager.java` | Manages LAN connections, sending and receiving moves, and network-related operations. |

## 🔗 Class Relationships and Modularity

The application follows a modular structure in which different classes collaborate to provide the complete functionality.

- **Game Initialization:** `ChessGame` launches `MainMenu`.
- **Configuration Management:** `MainMenu` creates and updates `GameSettings`.
- **Game Interface:** `ChessGUI` uses `GameSettings` and manages a `ChessBoard`.
- **Network Communication:** `ChessGUI` interacts with `NetworkManager` for LAN multiplayer.
- **Move Synchronization:** `NetworkManager` communicates moves between connected players.

This organization supports separation of concerns and makes individual components easier to understand and maintain.

## ♟️ Chess Piece Representation

The chessboard uses characters to represent chess pieces.

| Piece | White | Black |
|---|---|---|
| King | `K` | `k` |
| Queen | `Q` | `q` |
| Rook | `R` | `r` |
| Bishop | `B` | `b` |
| Knight | `N` | `n` |
| Pawn | `P` | `p` |
| Empty square | Space | Space |

Uppercase characters represent White pieces, while lowercase characters represent Black pieces.

## 🎮 Game Rules Implemented

The project implements basic movement validation for all six chess piece types.

- **Pawn:** Moves forward one square, or two squares from its initial position, and captures diagonally.
- **Rook:** Moves horizontally or vertically.
- **Knight:** Moves in an L-shaped pattern.
- **Bishop:** Moves diagonally.
- **Queen:** Combines the movement of a rook and bishop.
- **King:** Moves one square in any direction.

The application also prevents moving empty squares, moving the opponent's pieces out of turn, and capturing one's own pieces.

**Current Limitations:**

Advanced chess rules such as check, checkmate, castling, en passant, and promotion are not implemented. The king's safety is also not checked during move validation.

## ▶️ How to Compile and Run

### Prerequisites

- Java Development Kit (JDK) installed.
- Visual Studio Code or any Java-compatible IDE.
- Both computers connected to the same local network for LAN multiplayer.

### 1. Clone the Repository

```bash
git clone https://github.com/riyaghoshi/The-Inherited-Crown.git
```

### 2. Navigate to the Project Directory

```bash
cd The-Inherited-Crown
```

### 3. Compile the Java Files

```bash
javac *.java
```

### 4. Run the Application

```bash
java ChessGame
```

## 🕹️ How to Play

### LAN Multiplayer

**Host:**

1. Launch the application.
2. Enter player names.
3. Configure the optional timer.
4. Select `Host Online Game`.
5. Share the displayed IP address with the other player.
6. Wait for the opponent to connect.

**Join:**

1. Launch the application on another computer connected to the same LAN.
2. Enter player names and configure the timer.
3. Select `Join Online Game`.
4. Enter the host's IP address.
5. Once connected, start playing.

The host plays as White, while the joining player plays as Black. Moves are synchronized between the connected applications.

### Playing the Game

1. Select a chess piece.
2. View the highlighted possible destinations.
3. Select a destination to move the piece.
4. Take turns according to the active player's turn.
5. Use `New Game` to reset the board or `Main Menu` to return to the menu.

## 🧩 Object-Oriented Design Principles

The project applies several object-oriented design and software engineering principles:

- **Single Responsibility Principle (SRP):** Classes are organized around distinct responsibilities, such as board management, GUI handling, settings, and networking.
- **Encapsulation / Information Hiding:** Internal state is maintained using private attributes and controlled access methods.
- **Modularity:** Functionality is distributed across separate classes.
- **High Cohesion:** Related operations are grouped within their respective classes.
- **Separation of Concerns:** Game logic, user interface, configuration, and networking are handled separately.

These principles are applied to varying degrees; the project is not intended to represent a complete implementation of every SOLID principle.

## 🎨 Design Patterns and Programming Approaches

The application primarily uses an event-driven programming approach through Java Swing listeners and callbacks.

- **Event-Driven Programming:** User interactions such as button clicks and chessboard selections trigger corresponding operations.
- **Multithreading:** Network communication runs in a separate thread through `NetworkManager`, allowing the GUI to remain responsive.

No formal GoF design pattern is intentionally implemented as a separate architectural component.

## ⚠️ Exception Handling

Exception handling is used to manage runtime errors and improve application reliability.

Examples include:

- Handling `IOException` during network communication.
- Handling connection failures and socket timeouts.
- Handling network resource cleanup.
- Handling exceptions during system look-and-feel initialization.

## 🔮 Future Enhancements

- Implement complete chess rules, including check and checkmate detection.
- Add castling, en passant, and pawn promotion.
- Introduce a local two-player mode.
- Improve network validation and connection management.
- Add move history and undo functionality.
- Introduce an AI-powered chess opponent.
- Improve the overall graphical interface and user experience.

## 👩‍💻 Author

Created as an Object-Oriented Programming project demonstrating core OOP concepts in Java.

## 📄 License

This project is open source and available for educational purposes.

---

**The Inherited Crown — Every Move Has a Legacy. ♛**