Sea Battle Game

This is a console-based implementation of the classic Sea Battle (Battleship) game written in C++. The game supports both manual and automatic ship placement and allows players to battle against a computer opponent. The game is controlled using arrow keys for navigation and the Enter key for actions like shooting or placing ships.

Features:
- Two game modes: manual or automatic ship placement.
- Two 10x10 grids: one for the player's ships and one for the enemy's ships.
- Supports ships of different sizes (1 to 4 decks).
- Visual representation of the game board using colored console output.
- Turn-based gameplay with feedback messages for hits, misses, and game outcomes.

Requirements:
- C++ compiler (e.g., g++ or MSVC).
- Windows operating system (uses windows.h for console manipulation).
- Standard C++ libraries: iostream, time.h, conio.h.
- Windows.h for console color and cursor control.

Setup:
1. Ensure you have a C++ compiler installed (e.g., MinGW for Windows).
2. Save the code in a file (e.g., seabattle.cpp).
3. Compile and run the code using a command like:
   g++ seabattle.cpp -o seabattle
   ./seabattle
   (For MSVC, use the appropriate build tools.)

Gameplay Instructions:
1. Start Screen:
   - The game begins with a "Sea Battle" title screen.
   - After a brief pause, you are prompted to choose ship placement mode.

2. Ship Placement:
   - Choose between:
     - Automatic Placement: Ships are randomly placed on the player's grid.
     - Manual Placement: Use arrow keys to move, 'Q' to rotate ships, and Enter to place each ship.
   - The player places 10 ships (1 four-deck, 2 three-deck, 3 two-deck, 4 one-deck).
   - Enemy ships are always placed automatically.

3. Battle Phase:
   - Use arrow keys to move the cursor on the enemy's grid (right side).
   - Press Enter to fire at the selected position.
   - The game alternates between the player's and computer's turns.
   - Feedback messages indicate hits, misses, or destroyed ships.
   - The game ends when either all player or enemy ships are destroyed.

Controls:
- Arrow Keys: Move the cursor (up, down, left, right).
- Q: Rotate ship orientation (horizontal/vertical) during manual placement.
- Enter: Place a ship (manual placement) or fire at a position (battle phase).

Code Structure:
- main(): Initializes the game, handles menu selection, and controls the game loop.
- Ships: Struct defining ship properties (deck count, orientation, position, alive status).
- auto_arrangement(): Randomly places ships for automatic mode or enemy.
- PaintPos(): Renders the game grid with ships, hits, and misses.
- explosion(): Checks for destroyed ships and updates the game state.
- CreatField(): Draws the game board with borders and labels.
- Meny(): Displays in-game messages (e.g., hit, miss, victory).
- SetCursor() and setColor(): Handle console cursor positioning and text coloring.

Notes:
- The game uses a 12x24 array to represent the grid, with extra space for borders and ship "padding."
- Ship positions are marked as:
  - 0: Empty space.
  - 1: Buffer zone around ships.
  - 2: Miss (shot but no ship).
  - 3: Hit (shot hit a ship).
  - 4-13: Ship identifiers (unique for each ship).
- The game uses console colors (e.g., Black for player ships, White for enemy ships, LightGray for misses, LightMagenta for hits).
- The computer's attacks are random, with no advanced strategy.

Limitations:
- Designed for Windows due to windows.h and conio.h dependencies.
- No error handling for invalid console settings or window sizes.
- The computer's AI is basic (random shots only).
- No option to restart the game without rerunning the program.

Future Improvements:
- Add cross-platform support (e.g., using ncurses for Linux/macOS).
- Implement a smarter AI for the computer opponent.
- Add a restart or main menu option.
- Include sound effects for hits, misses, and game events.
- Support saving/loading game states.
