# UNIBOssfight

UNIBOssfight is a 2D platform shooter inspired by the classic arcade game *Metal Slug*, reimagined in the context of a university campus. The game aims to simulate a student's journey to graduation by overcoming exam-themed levels filled with enemies and bosses.

## 🎮 Gameplay Overview

Players must progress through a series of platform levels, defeating enemies (representing challenges) and ultimately facing professors as final bosses. The performance in the game, including defeated enemies and collected "CFU coins," determines the player's final grade.

## 🧱 Features

### Functional Requirements
- **Main Menu**: Navigate through the game, choose levels, view controls, start new games, and exit.
- **Simultaneous Input Handling**: Move and shoot independently using keyboard and mouse.
- **Enemy Movement**: Basic AI-controlled enemy behaviors.
- **Automatic Weapon**: Player's weapon targets based on the mouse pointer.
- **Score System**: Final grade calculated from defeated enemies and collected coins.

### Non-Functional Requirements
- **Performance**: Smooth gameplay with a minimum of 30 FPS.
- **Low Latency**: Fast and responsive controls.

## 🧩 Architecture

UNIBOssfight is built using the **Entity Component System (ECS)** architecture:

- **Entity**: Generic game object (e.g., player, enemies, items).
- **Component**: Encapsulates a single behavior or property (e.g., position, rendering, collision).
- **System**: Modifies entities via their components (e.g., rendering engine, collision detection, behavior control).

This design enables modular and scalable code, ideal for a game with diverse entities and complex interactions.

## ⚙️ Technologies Used

- **Language**: Java
- **UI Framework**: JavaFX
- **Serialization**: GSON (Google's JSON library)
- **Testing**: JUnit
- **Version Control**: Git (with GitFlow branching model)

## 👥 Team and Responsibilities

- **Livia Cardaccia**:
  - Main Menu and scene management
  - Obstacles (Walls, Platforms, Coins)
  - `Behaviour` component and `BehaviourBuilder`

- **Denise Nanni**:
  - Collision management and direction handling
  - Custom `Logger` (Singleton pattern)
  - Scoring system

- **Giovanni Prete**:
  - `Renderer` and `Transform` components
  - Game input handling
  - Serialization / deserialization via `DataManager`

- **Matteo Sartini**:
  - Weapon and shooting system
  - Boss level implementation
  - Utility classes (e.g., angle calculation, acceleration)

## 🧪 Testing

- `TestEntity`: Verifies collision and damage logic.
- `TestFinalGrade`: Verifies correct final grade computation.

## 🧠 How to Play

1. **Controls**:
   - `A` / `D`: Move left/right
   - `Space`: Jump
   - `Mouse`: Aim
   - `Click`: Shoot

2. **Menu Options**:
   - **Play**: Start a new game
   - **Level**: Choose one of the available levels
   - **Help**: View control instructions
   - **Score**: View game statistics and final grade

3. **Goal**: Complete all levels by defeating enemies and bosses to "graduate" with the highest possible score.

## 🛠 Development Notes

- Designed with flexibility in mind: easy to add new behaviors, enemies, and levels.
- Assets sourced from [Pngegg](https://www.pngegg.com/) and [CraftPix](https://craftpix.net/).
- Code integrates JavaFX event handling and functional programming patterns (e.g., lambda expressions, `BiConsumer`).

## 📦 Project Structure

```plaintext
UNIBOssfight/
├── src/
│   ├── app/core/           # ECS core (Entity, Component, System)
│   ├── app/impl/           # Implementations of components and systems
│   ├── app/ui/             # JavaFX-based UI components
│   ├── app/game/           # Main game logic and levels
│   └── app/util/           # Utilities (DataManager, Logger, etc.)
├── assets/                 # Images, fonts, and other game resources
├── test/                   # JUnit test cases
└── README.md               # This file
