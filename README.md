# The Locker Heist — Group 2

**Course:** CL1004 — Object Oriented Programming  
**Section:** CS 3A — Fall 2026  
**Members:** Ahsan (25F-0722), Farhan (25F-0804)  
**Instructor:** Zaynab Noor

## Project files

- `heist.h` — structures, enumerations, class declarations, and `DynamicArray<T>`.
- `heist.cpp` — class implementations and the complete game logic.
- `main.cpp` — driver for the singleton `GameEngine`.
- `clue.txt` — seven culprit roles and their two target words.
- `locations.txt` — seven location clues for every possible culprit profile.
- `characters.txt` — eight character profiles and their letter clues.
- `rules.txt` — game limits and penalties.
- `about.txt` — project and team information.
- `leader/scoreBoard.txt` — persistent game results.

## Build with Visual Studio

1. Open `TheLockerHeist.sln`.
2. Build the solution using **Build > Build Solution**.
3. Set the project's **Working Directory** to `$(ProjectDir)` so the text files are found.
4. Run the project.

If creating a project manually, add `main.cpp` and `heist.cpp` as source files and `heist.h` as a header file. Keep all `.txt` files and the `leader` folder beside the project file.

## Build with g++

From this folder:

```bash
g++ -std=c++11 -Wall -Wextra -pedantic main.cpp heist.cpp -o locker_heist
./locker_heist
```

On Windows PowerShell:

```powershell
g++ -std=c++11 -Wall -Wextra -pedantic main.cpp heist.cpp -o locker_heist.exe
.\locker_heist.exe
```

## How to play

1. Select **New Game** and enter a detective name without spaces. Use `_` or `.` instead of spaces.
2. Visit the seven cottage locations to collect the seven letters for Word 1.
3. Interview the eight people to collect the eight letters for Word 2. Some interviews require minimum credibility:
   - Victim: 80
   - Business partners: 50
   - PA: 35
   - Owner's child: 75
   - Cook, Guard, Servant: no minimum
4. View the Scrabble board at any time; viewing it does not use a turn.
5. When a row is complete, select **Form a Word** and enter the word in that row.
6. After both words are solved, accuse one of the seven suspects.
7. The game ends when the correct suspect is accused, credibility reaches zero, turns are exhausted, or the detective quits.

## OOP concepts represented

- Three-file structure, structures, and enumerations.
- Abstract `Character` base class and runtime polymorphism.
- Single, multilevel, and multiple inheritance.
- Virtual inheritance for the PA diamond.
- Dynamic memory allocation and deep-copy operations.
- Generic `DynamicArray<T>` template.
- Composition, aggregation-style location cache, and association with the leaderboard.
- Operator overloading (`==`, `<`, `+`, `<<`, `>>`).
- Friend function and `GameEngine` friend class.
- Singleton `GameEngine`.
- File handling and custom exceptions.

## Important project note

The course manual says submitted work must be the registered team's own work and that AI-generated code submitted without understanding may be treated as an academic-integrity violation. Use this package as a study/build reference: both members should review, test, adapt, and be able to explain every module before submission. Confirm the instructor's AI-use rules before submitting generated material.

## Known limitations / design notes

1. The game uses the sample character names and sample clue profiles from the provided project data.
2. The culprit is randomly selected each time a new game starts; the target words are loaded from `clue.txt`.
3. The game is a console application and does not include graphics or sound.
4. The project expects the text files and `leader` folder to remain in the working directory.
5. The sample words are kept exactly as supplied in the project sample, including `SPAGHETI`.
