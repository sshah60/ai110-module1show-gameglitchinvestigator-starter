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

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
