# PokemonGame

PokemonGame is a C++ project designed to simulate simplified 1v1 Pokémon battles and analyze possible battle outcomes. The goal is to model battle states, evaluate type effectiveness, and explore how different moves can influence the result of a match.

## Project Overview

This project focuses on:

- simulating Pokémon battles between two active Pokémon;
- considering direct damage moves and the Recover action;
- using simplified rules for type effectiveness and damage calculation;
- exploring battle-state possibilities and outcomes.

## Requirements

Before running the project, make sure you have the following installed:

1. Visual Studio Code
2. VS Code extension: C/C++ by Microsoft
3. MinGW / GCC compiler
   - Install MinGW from [here](https://winlibs.com/)
   - Make sure the compiler is available in your PATH as `g++.exe`

## How to Run the Project

1. Open the project folder in Visual Studio Code.
2. Install the extension named "C/C++" by Microsoft.
3. Install MinGW and confirm that `g++.exe` is available in your terminal.
4. Open the file `main.cpp`.
5. In VS Code, choose the C/C++ compiler configuration when prompted, or use the Command Palette and select the appropriate C++ compiler option.
6. Build the project using:
   - Terminal > Run Build Task
   - or press Ctrl+Shift+B
   - choose "C/C++: g++.exe build active file"
7. After the build finishes, run the generated executable (`main.exe`) from the project folder.

## Notes

- The project is intended for educational and academic use.
- The current implementation uses simplified battle rules for analysis and simulation.

## License

This project is distributed under the LICENSE file included in the repository.
