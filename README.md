# UNITY-FLAPPY-BIRD
This project is a Flappy Bird clone created with Unity. The player controls a bird by pressing the space bar or up arrow key to navigate through pipes. The game features a scoring system, a game over screen, and options to restart or exit.

# Flappy Bird Clone

This is a simple Flappy Bird clone implemented using Unity. The game involves a bird that the player must navigate through pipes by pressing the space bar or the up arrow key to flap the bird's wings.

## Contents

- [Installation](#installation)
- [Gameplay](#gameplay)
- [Scripts](#scripts)
  - [LogicScript](#logicscript)
  - [PipeMiddleScript](#pipemiddlescript)
  - [PipeMoveScript](#pipemovescript)
  - [PipeSpawnerScript](#pipespawner-script)
  - [BirdScript](#birdscript)
- [License](#license)

## Installation

1. Clone or download this repository.
2. Open the project in Unity.
3. Ensure all dependencies are resolved.
4. Open the main scene (e.g., `MainScene.unity`) in Unity.
5. Press the play button to start the game.

## Gameplay

- **Controls**:
  - Press `Space` or `Up Arrow` to make the bird flap its wings.
  - Press `Enter` to restart the game if the bird collides with a pipe and the game is over.
  - Press `Escape` to quit the game when the game over screen is displayed.

- **Objective**:
  - Navigate the bird through the pipes without colliding.
  - The score increases by 1 for each set of pipes the bird successfully passes through.

## Scripts

### LogicScript

This script manages the main game logic, including the score, game over state, and restarting the game.

- **Variables**:
  - `playerScore`: Keeps track of the player's score.
  - `scoreText`: Displays the player's score.
  - `gameOverScreen`: The screen that appears when the game is over.

- **Methods**:
  - `Update()`: Checks for key presses to restart or exit the game.
  - `addScore(int scoreToAdd)`: Adds to the player's score and updates the score display.
  - `restartGame()`: Restarts the current scene.
  - `gameOver()`: Activates the game over screen.
  - `ExitGame()`: Quits the application.

### PipeMiddleScript

This script manages the logic for when the bird passes through the middle of the pipes to increase the score.

- **Variables**:
  - `logic`: Reference to the `LogicScript` to update the score.

- **Methods**:
  - `Start()`: Initializes the reference to `LogicScript`.
  - `OnTriggerEnter2D(Collider2D collision)`: Checks for collisions with the bird to increase the score.

### PipeMoveScript

This script handles the movement of the pipes and their destruction once they move off-screen.

- **Variables**:
  - `moveSpeed`: Speed at which the pipes move.
  - `deadZone`: The x-coordinate at which the pipes are destroyed.

- **Methods**:
  - `Update()`: Moves the pipes to the left and destroys them when they reach the dead zone.

### PipeSpawnerScript

This script spawns the pipes at regular intervals with a random vertical position.

- **Variables**:
  - `pipe`: The pipe GameObject to spawn.
  - `spawnRate`: The time interval between pipe spawns.
  - `timer`: Tracks time to manage spawning.
  - `heightOffset`: The vertical range within which pipes are spawned.

- **Methods**:
  - `Start()`: Spawns the first pipe.
  - `Update()`: Manages the timer and spawns pipes at regular intervals.
  - `spawnPipe()`: Spawns a pipe at a random vertical position within the specified range.

### BirdScript

This script controls the bird's movement and checks for collisions.

- **Variables**:
  - `myRigidbody`: The Rigidbody2D component attached to the bird.
  - `flapStrength`: The force applied to the bird when it flaps.
  - `logic`: Reference to the `LogicScript`.
  - `birdIsAlive`: Boolean indicating whether the bird is alive.

- **Methods**:
  - `Start()`: Initializes references to components.
  - `Update()`: Checks for key presses to make the bird flap its wings.
  - `OnCollisionEnter2D(Collision2D collision)`: Handles the bird's collision with pipes or the ground, triggering game over.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
