# GAME-DEVELOPMENT-SNAKE-GAME


This C++ program is a classic implementation of the Snake game using the SFML (Simple and Fast Multimedia Library). The game operates in a window where a green snake moves around, consuming red food items to grow longer. As the snake eats food, the player’s score increases, and the game speed gradually accelerates, increasing difficulty. The player controls the snake using the arrow keys, and the game ends when the snake hits the walls or itself. Sound effects and background music enhance the gameplay experience.

Core Components
The game is structured around the SnakeGame class, which encapsulates all logic related to gameplay, input handling, rendering, and state management. The class maintains variables for the snake’s body, direction, food, game state (e.g., game over), score, and speed.

sf::RenderWindow window: Manages the game window.

std::vector<sf::Vector2f> snake: Stores the positions of each segment of the snake.

sf::Vector2f direction: Represents the movement direction of the snake.

sf::Vector2f foodPosition: Stores the current position of the food.

sf::Clock clock: Tracks time to control snake movement speed.

float speed: Determines how fast the snake moves.

bool isGameOver: Flags whether the game is over.

sf::Font and sf::Text: Used to display the score.

sf::SoundBuffer and sf::Sound: Handle sound effects for eating food and game over events.

sf::Music: Plays background music.

Game Initialization
The constructor initializes all game components:

Sets the window size and title.

Initializes the snake with a single segment centered in the window.

Sets the movement direction to the right.

Loads assets such as font, sound effects, and music from the assets directory.

Sets the initial position of the food randomly using std::rand.

Begins playing background music in a loop.

Game Loop
The game loop is defined in the run() method. It continuously:

Processes player input.

Updates the game state if enough time has passed.

Renders the updated game state to the screen.

This loop ensures consistent framerate-based logic independent of the actual frame rate.

Input Handling
Handled in processEvents(), player input allows control of the snake using arrow keys. The code prevents illegal 180-degree turns (e.g., moving directly from left to right). If the game is over, pressing the "R" key resets it.

Game State Update
In the update() method:

The snake’s head is moved in the current direction, and each segment follows the one in front.

The game checks for collisions using checkCollision():

Wall collision: If the snake's head moves beyond the window bounds.

Self collision: If the head touches any other segment of its body.

Food collision: If the head overlaps the food. In this case, the snake grows, a sound plays, the score increases, and new food is spawned.

The snake’s speed increases gradually with score, but is capped to prevent becoming too fast.

Rendering
In the render() method:

Clears the screen.

Draws each segment of the snake.

Draws the food and score.

If the game is over, displays a “Game Over” message.

Additional Features
Background music plays continuously.

Eating and game over sounds provide feedback.

Food is randomly placed but doesn’t check if it overlaps the snake (a potential bug).

Summary
This program is a complete and functional version of the Snake game using SFML. It demonstrates a well-structured game loop, clean object-oriented design, responsive input handling, basic collision detection, and multimedia integration. The game is also extendable, making it a good starting point for adding features like levels, menus, high scores, or animations.
