# Guess-Word
# Guess The Word Game

A simple word-guessing game written in Python. The player is shown a hidden word as blanks, and one extra letter is revealed after each wrong guess. Guess the full word before all letters are revealed to score points.

## How to Play

1. Run the script.
2. At the menu, enter `1` to start a round or `2` to exit.
3. A random word is picked from the word list and shown as blanked-out letters, e.g.:
   ```
   [=___=][=___=][=___=][=___=][=___=]
   ```
4. Type your guess for the full word.
5. If you're wrong, one more letter is revealed and you're asked to guess again.
6. This continues until you guess correctly (you score points) or till u lose (Game Over).
7. After win or lose a round , you'll be asked whether you want to play again.

## Scoring

Points are awarded based on how early you guess correctly — the fewer letters revealed, the more points you earn:

| Guess attempt        | Points |
|-----------------------|--------|
| 1st guess (no hints)   | 10     |
| 2nd guess              | 8      |
| 3rd guess              | 6      |
| 4th guess              | 5      |
| 5th guess              | 4      |
| 6th guess              | 3      |
| 7th guess              | 2      |

Your total score carries over across rounds within the same session.

## Word List

```python
words = ("apple", "orange", "banana", "pineapple")
```

You can add your own words to this tuple. Note: words of different lengths reveal letters at different points, since the game reveals specific letter positions (index 0, 2, 3, 5, 7, 8) rather than random ones.

## Requirements

- Python 3
- No external libraries — uses only the built-in `random` module

## Running It

```bash
python "hangman game.py"
```

## Functions

- **`rng()`** — builds the initial list of blanked-out letters (`"___"`) matching the length of the chosen word.
- **`win(point)`** — prints the "you got it right" message along with the current score.
- **`ask_continue()`** — asks the player if they want to play another round; returns `True` to continue or `False` to exit.

## Known Limitations

- Letter reveal positions are hardcoded (`cd[0]`, `cd[2]`, `cd[3]`, etc.), so they only make sense for the specific word lengths in the current word list (5, 6, and 9 letters). Adding a word of a different length may cause uneven or missing hints.
- Guessing is by full word, not by individual letter.
