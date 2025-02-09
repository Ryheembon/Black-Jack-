# Python Blackjack Game Documentation

## Overview
This Python implementation creates a text-based Blackjack game where players compete against a computer dealer. The game follows standard Blackjack rules, including special handling for Aces and dealer hit requirements.

## Features
- Text-based user interface
- Random card dealing
- Automatic score calculation
- Special handling for Aces (11/1 value)
- Dealer logic for hitting below 17
- Complete game loop with replay option

## Implementation Details

### Card Handling
The `deal_card()` function manages card distribution:
```python
def deal_card():
    cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    return random.choice(cards)
```
Cards are represented by their numerical values, with face cards (Jack, Queen, King) valued at 10 and Aces initially at 11.

### Score Calculation
The `Calculate_score()` function handles scoring logic, including special cases:
- Blackjack (21 with 2 cards) returns 0 as a special case
- Automatically adjusts Ace values from 11 to 1 when hand would bust
- Returns the sum of all cards in the hand

### Game Flow
1. Initial Setup:
   - Both player and dealer receive two cards
   - Player can see their cards and dealer's first card

2. Player's Turn:
   - Player decides to hit ('y') or stand ('n')
   - Game checks for bust or Blackjack after each hit
   - Turn ends when player stands or busts

3. Dealer's Turn:
   - Dealer must hit on hands below 17
   - Continues drawing until reaching 17 or higher
   - Dealer plays automatically after player stands

### Win Conditions
The `compare()` function determines the winner based on final scores:
- Blackjack beats regular 21
- Closer to 21 wins
- Going over 21 is an automatic loss
- Equal scores result in a draw

## Usage Instructions

1. Start the game by running the script
2. Respond to the initial prompt to play:
   ```
   Do you want to play a game of Blackjack? Type 'y' or 'n':
   ```

3. During each round:
   - View your cards and current score
   - Decide whether to hit or stand
   - See the final results and winner

4. Choose to play again or exit after each round

## Dependencies
- Python 3.x
- Random module (standard library)
- Art module (for logo display)

## Code Structure
The code follows a modular design with clear separation of concerns:
- Card dealing logic
- Score calculation
- Game state management
- Win condition evaluation
- Main game loop

## Error Handling
The implementation includes several safeguards:
- Ace value adjustment to prevent unintended busts
- Input validation for player decisions
- Clear game state management to prevent invalid plays

