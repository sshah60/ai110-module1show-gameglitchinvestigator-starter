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

- [ ] Describe the game's purpose.
- [ ] Detail which bugs you found.
- [ ] Explain what fixes you applied.

The purpose of the game is to guess a randomly generated number within a limited number of attempts while using higher/lower hints.

I found several bugs, including guesses outside the allowed range being accepted, incorrect higher/lower hints, and the attempt count behaving incorrectly.

I fixed the input validation so guesses outside the allowed range are rejected, corrected the higher/lower hint logic, and fixed the attempt counting so invalid guesses do not use attempts and the count does not go below zero. I also moved core logic into `logic_utils.py` and added pytest coverage for the fixes.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. The player starts a new game and is told to guess a number within the allowed range.
2. The player enters a guess that is too low, and the game tells them to go higher.
3. The player enters a guess that is too high, and the game tells them to go lower.
4. The player enters the correct number, and the game displays a winning message and final score.
5. Invalid guesses outside the allowed range are rejected instead of being counted as attempts.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```text
python -m pytest
4 passed


If you want to be a little safer/more complete, rerun:

```bash
python -m pytest

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
