# AI Game Referee – Rock–Paper–Scissors–Plus

## Overview
This project implements a minimal conversational AI referee for a Rock–Paper–Scissors–Plus game. The referee manages a complete best-of-three game between a user and a bot by enforcing rules, tracking state across turns, validating inputs, and providing clear round-by-round explanations.  
The solution is designed as a simple CLI/chat-style interaction, focusing on correctness, state modeling, and clean separation of responsibilities.

---

## Game Rules
- The game is **best of 3 rounds**
- Valid moves: `rock`, `paper`, `scissors`, `bomb`
- Each player may use **bomb only once per game**
- Bomb beats all other moves
- Bomb vs bomb results in a draw
- Invalid input wastes the round
- The game ends automatically after 3 rounds

---

## State Model
Game state is maintained in a persistent Python dictionary that lives outside the prompt and survives across turns.  
The state tracks:
- Current round number
- Maximum rounds (3)
- User and bot scores
- Bomb usage status for both players
- History of all completed rounds

This explicit state model ensures rule enforcement, prevents invalid actions, and guarantees automatic game termination.

Agent and Tool Design
The system follows a clear separation of concerns:
 I.Intent Understanding  
  User input is first interpreted to determine whether it represents a valid move or an invalid action.
 II.Game Logic (Tools)*  
  Dedicated tools handle:
  - Move validation (including bomb usage constraints)
  - Bot move selection
  - Round resolution based on game rules
  - Game state mutation and history tracking

 III.Response Generation  
  The agent orchestrates tool calls and generates user-facing explanations, including round number, moves played, round outcome, and current score.
All rule enforcement and state updates occur inside tools rather than in prompt text.

Tradeoffs
- The bot uses a random move selection strategy to keep the focus on rule enforcement, state management, and agent–tool separation rather than gameplay optimization.
- A CLI-based interaction is used instead of a UI to maintain simplicity and comply with technical constraints.

Future Improvements
With additional time, the system could be extended to include:
- Smarter or adaptive bot strategies
- Structured JSON outputs for easier integration
- Replay or summary views of past games
- Multi-agent extensions for more complex interactions

How to Run
bash
python game_referee.py
