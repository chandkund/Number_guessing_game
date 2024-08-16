# Number Guessing Game

This is a simple number guessing game implemented in Python. The game generates a random number within a specified range and prompts the user to guess the number. The user has a limited number of attempts to guess the correct number, which is calculated based on the range.

## Project Overview

In this game:
- The user is asked to input the start and end range for the random number.
- A random number is generated within the specified range.
- The user is given a limited number of attempts to guess the correct number.
- Feedback is provided after each guess to guide the user.
- If the user fails to guess correctly within the allowed attempts, the correct number is revealed.

## Table of Contents

- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)

## Installation

To run this game, you'll need Python installed on your system. No additional libraries are required beyond the standard library.

## Usage

1. **Run the Script:**
   
   Save the code in a file, e.g., `number_guessing_game.py`, and run it using Python:

    ```bash
    python number_guessing_game.py
    ```

2. **Provide Input:**

   - Enter the start range and end range when prompted.
   - Make guesses within the allowed number of attempts.

## Code Explanation

- **Import Libraries:**

    ```python
    import random
    import math
    ```

- **Input Range:**

    ```python
    start_range = int(input("Enter start range: "))
    end_range = int(input("Enter end range: "))
    ```

- **Generate Random Number:**

    ```python
    randomly_selection = random.randint(start_range, end_range)
    ```

- **Calculate Number of Attempts:**

    ```python
    print("You have only", round(math.log(end_range - start_range + 1, 2)), "chances to guess the integer!")
    ```

- **Game Loop:**

    ```python
    count = 0
    while count < math.log(end_range - start_range + 1, 2):
        count += 1
        guess = int(input("Guess a number: "))
    
        if guess == randomly_selection:
            print("Congratulations! You guessed the correct number.")
            break
        elif guess > randomly_selection:
            print("Try again! You guessed too high.")
        elif guess < randomly_selection:
            print("Try again! You guessed too low.")
    
    if count >= math.log(end_range - start_range + 1, 2):
        print("\nThe number was %d" % randomly_selection)
        print("Better luck next time!")
    ```


