# Console Based Snake Game

This is a simple implementation of the classic Snake game in C++.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
- [How to Play](#how-to-play)
- [Code Explanation](#code-explanation)
- [Optimizations](#optimizations)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project is a basic console-based Snake game written in C++. The game is designed to be simple and easy to understand, making it a good starting point for beginners who want to learn C++ and game development basics.

## Features

- Classic Snake gameplay
- Console-based interface
- Simple controls using `W`, `A`, `S`, `D` keys
- Wrap-around screen
- Score tracking

## Getting Started

### Prerequisites

- A C++ compiler (GCC, Clang, MSVC, etc.)
- CMake (optional, for building the project)

### Building and Running

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/snake-game.git
    cd snake-game
    ```

2. Compile the code using your preferred C++ compiler:
    ```bash
    g++ -o snake_game snake_game.cpp
    ```

3. Run the executable:
    ```bash
    ./snake_game
    ```

## How to Play

- Use the `W`, `A`, `S`, `D` keys to move the snake:
  - `W`: Move up
  - `A`: Move left
  - `S`: Move down
  - `D`: Move right
- Press `X` to quit the game.
- The goal is to eat the fruit (`F`) that appears on the screen. Each fruit eaten increases your score by 10 points and the length of the snake's tail.
- The game ends if the snake collides with its tail.

## Code Explanation

### Global Variables

- `bool gameOver`: Controls the game loop.
- `const int width, height`: Dimensions of the game field.
- `int x, y, fruitX, fruitY, score`: Positions of the snake's head and the fruit, and the player's score.
- `std::vector<int> tailX, tailY`: Stores the coordinates of the snake's tail segments.
- `enum eDirection { STOP = 0, LEFT, RIGHT, UP, DOWN }`: Defines the possible directions for the snake's movement.
- `eDirection dir`: Stores the current direction of the snake.

### Functions

- `void setUp()`: Initializes the game state.
- `void draw()`: Renders the game field and objects.
- `void input()`: Handles user input for controlling the snake.
- `void logic()`: Updates the game logic, including movement and collision detection.

### Main Loop

```cpp
int main() {
    setUp();
    while (!gameOver) {
        draw();
        input();
        logic();
        Sleep(100); // Adjusted sleep time for better playability
    }
    return 0;
}
