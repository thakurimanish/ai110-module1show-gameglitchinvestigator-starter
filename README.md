# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

Game Purpose:
The purpose of this game is to let the user guess a randomly generated secret number within a limited number of attempts. The game provides hints after each guess and keeps track of the player's score and progress until the game is won or lost.

Bugs Found:
When I first ran the game, I noticed several problems. The New Game button did not fully reset the game state, causing previous values to remain. I also encountered a TypeError because the secret number was being treated as a string while the guess was an integer. In addition, the game logic was stored directly in app.py, which made the code difficult to test and maintain.

Fixes Applied:
I fixed the New Game functionality so that it correctly resets the score, attempts, history, status, and secret number. I also corrected the guess comparison logic so that both values are treated as integers, preventing TypeErrors. To improve the structure of the project, I moved the game logic functions into logic_utils.py and updated app.py to import those functions. Finally, I added pytest tests to verify that the game correctly handles winning, high, and low guesses.
## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. Start the game on Normal difficulty.
2.Enter a guess of 40.
3. The game returns "Too Low".
4.Enter a guess of 70.
5. The game returns "Too High".
6.Continue guessing until the correct number is entered.
7.The game displays a winning message and final score.
8.Click "New Game" to start a fresh game with a new secret number.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

===================================================================== test session starts ======================================================================
platform darwin -- Python 3.12.4, pytest-9.0.3, pluggy-1.6.0
rootdir: /Users/manish/Desktop/codepath/ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.13.0
collected 3 items                                                                                                                                              

tests/test_game_logic.py ...                                                                                                                             [100%]

====================================================================== 3 passed in 0.01s =======================================================================

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
