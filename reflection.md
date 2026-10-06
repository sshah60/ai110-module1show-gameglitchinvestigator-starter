# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

When I first ran the game, it looked like a normal number guessing game where I had to guess a number between 1 and 100 within a limited number of attempts. However, I  noticed that the game accepted guesses outside of the intended range instead of rejecting them. I also noticed that the difficulty levels seemed to work backwards, making the easier setting harder and the harder setting easier. Finally, the game allowed the number of remaining attempts to go below zero instead of ending when no attempts were left.

**Bug Reproduction Log**

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Enter `34732849372` or `-3` as a guess | The game should reject the input because guesses must be between 1 and 100 | The game accepts the number and gives a normal "Go Higher" or "Go Lower" hint | No console error; incorrect behavior appears in the game UI |
| Select the Easy and Hard difficulty settings | Easy should make the game easier and Hard should make the game harder | The difficulty behavior appears reversed, with Easy behaving harder and Hard behaving easier | No console error; incorrect behavior appears in the game UI |
| Continue guessing after the remaining attempts reach `0` | The game should stop accepting guesses and end the round | The game continues accepting guesses and the remaining attempts become negative | No console error; attempts displayed below `0` |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

I used ChatGPT and Claude to help debug the game and think through possible fixes. One correct suggestion was to add range validation to `parse_guess()` and move the logic into `logic_utils.py`; I verified it with pytest and by testing invalid guesses in the Streamlit app. I did not follow an AI suggestion to focus on the difficulty bug because I could not reproduce its exact behavior reliably. Instead, I focused on the attempt-counting and hint bugs, which I verified through testing and the live game.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I considered a bug fixed only after it worked both in pytest and in the Streamlit game. I ran the full pytest suite and all 4 tests passed. I also manually tested invalid guesses, higher/lower hints, and the game-over behavior to make sure the fixes worked correctly. AI helped me create and understand the pytest test for out-of-range guesses.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

Streamlit reruns the app from top to bottom whenever the user interacts with it. Session state lets the app remember important values, such as the secret number, score, attempts, and game status, between those reruns. Without session state, those values could reset every time the page reruns.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to keep using is testing each bug separately before moving on to the next one. Next time I use AI for coding, I would give it smaller, more specific problems instead of asking for large changes at once. This project showed me that AI-generated code can be useful, but it still needs to be checked, tested, and understood before trusting it.
