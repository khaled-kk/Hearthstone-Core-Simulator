# 🎴 Hearthstone Core Simulator

[![Tech: [Insert, e.g., Java/C#]](https://img.shields.io/badge/Tech-OOP--Logic-blue.svg)]()
[![UI: [Insert, e.g., Swing/Unity/JavaFX]](https://img.shields.io/badge/UI-Interactive--GUI-orange.svg)]()
[![Status: Functional](https://img.shields.io/badge/Status-Complete-success.svg)]()

**Hearthstone Core Simulator** is a high-fidelity recreation of the popular Collectible Card Game (CCG) mechanics. This project focuses on the complex interplay between game state, user input, and automated game logic, all managed within a custom-built Graphical User Interface.

## 🕹️ Core Mechanics
*   **Turn-Based Logic:** Implements a robust state machine to manage Draw, Play, Attack, and End-Turn phases.
*   **Mana System:** Dynamic resource management that scales per turn.
*   **Card Interaction Engine:** Handles complex interactions between "Minions" (Attack/Health) and "Spells" (Targeted/AoE).
*   **Health & Combat System:** Logic-driven damage calculation including taunts and hero power activations.

## 🛠️ Technical Architecture
The project is built using a strict **Object-Oriented (OOP)** approach to ensure scalability:
*   **Card Hierarchy:** Abstract base classes for cards with specific inherited behaviors for different card types.
*   **Event Handling:** Decoupled UI and Logic—actions on the board trigger backend state updates which then reflect in the GUI.
*   **Board State Management:** A centralized controller tracks the status of both players, the deck, the hand, and the battlefield.



## 🎨 UI/UX Features
*   **Interactive Battlefield:** Drag-and-drop or click-based interactions for playing cards and targeting enemies.
*   **Real-Time Feedback:** Visual indicators for health changes, mana availability, and turn indicators.
*   **Dynamic Hand Display:** Automatically adjusts as cards are drawn from the deck.

## 🚀 Getting Started
1. **Clone the repo:**
   ```bash
   git clone [https://github.com/khaled-kk/Hearthstone-Core-Simulator.git](https://github.com/khaled-kk/Hearthstone-Core-Simulator.git)

2. **Build & Run:**

* Open the project in [Insert IDE, e.g., IntelliJ/Visual Studio].
* Run Main.[extension] to launch the GUI.

---
*Developed by Khaled Walid*
