Day-7
# Hangman Game 🎮  

Welcome to the **Hangman Game**! This is a classic word-guessing game where you try to guess the hidden word letter by letter. You have limited attempts, so choose wisely!

## Project Description

The **Hangman Game** is a simple Python-based implementation that leverages ASCII art to display the game's current state visually. The game randomly selects a word from a predefined list, and the player needs to guess the word before running out of lives.

## Features

- **Random Word Selection**: The game picks a random word from a predefined list.
- **Interactive Gameplay**: Provides immediate feedback on each guess.
- **Visual Feedback**: Uses ASCII art to represent the hangman's current state.
- **User-Friendly**: Displays letters already guessed and the current progress of the word.

## How to Play

1. Run the Python script.
2. The game will display a logo and the current word progress as underscores (`_`).
3. You need to guess one letter at a time.
4. If the guessed letter is in the word, it will be revealed in its correct positions.
5. If the guessed letter is not in the word, you lose a life.
6. The game ends when you either guess all the letters correctly or run out of lives.

### Example

```
 _                                             
| |                                            
| |__   __ _ _ __   __ _ _ __ ___   __ _ _ __  
| '_ \ / _` | '_ \ / _` | '_ ` _ \ / _` | '_ \ 
| | | | (_| | | | | (_| | | | | | | (_| | | | |
|_| |_|\__,_|_| |_|\__, |_| |_| |_|\__,_|_| |_|
                   __/ |                      
                  |___/   

Guess a letter: a
_ a _ _ a _ 

Guess a letter: e
You guessed e, that's not in the word. You lose a life.
 _ a _ _ a _ 

Guess a letter: p
You win!
```

## Prerequisites

- Python 3.x installed on your system.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/aditya-kr86/Hangman.git
   ```

2. **Navigate to the project folder**:
   ```bash
   cd Hangman
   ```

3. **Run the script**:
   ```bash
   python hangman.py
   ```

## Project Files

The project includes the following files:

- **`hangman.py`**: The main game logic.
- **`hangman_words.py`**: A list of words used in the game.
- **`hangman_art.py`**: ASCII art used for the game's logo and hangman stages.

### ASCII Art

The game uses ASCII art to represent different stages of the hangman:

```python
stages = [
  '''
    +---+
    |   |
    O   |
   /|\  |
   / \  |
        |
  =========
  ''', 
  '''
    +---+
    |   |
    O   |
   /|\  |
   /    |
        |
  =========
  ''',
  '''
    +---+
    |   |
    O   |
   /|\  |
        |
        |
  =========
  ''',
  '''
    +---+
    |   |
    O   |
   /|   |
        |
        |
  =========
  ''',
  '''
    +---+
    |   |
    O   |
    |   |
        |
        |
  =========
  ''',
  '''
    +---+
    |   |
    O   |
        |
        |
        |
  =========
  ''',
  '''
    +---+
    |   |
        |
        |
        |
        |
  =========
  '''
]
```

## Code Explanation

1. **Random Word Selection**: The program imports a list of words from `hangman_words.py` and selects a random word using `random.choice()`.
2. **User Input and Feedback**: The player guesses letters one by one. The game checks if the letter is in the chosen word.
3. **Tracking Progress**: The player's current progress is stored in the `display` list.
4. **Lives Tracking**: The player starts with 6 lives, losing one for each incorrect guess.
5. **Game End**: The game ends when the player guesses the word or runs out of lives.

### Example Code Snippet

```python
chosen_word = random.choice(word_list)
display = ['_' for _ in range(len(chosen_word))]

while not end_of_game:
    guess = input("Guess a letter: ").lower()

    if guess in display:
        print(f"You've already guessed {guess}")

    for i, letter in enumerate(chosen_word):
        if letter == guess:
            display[i] = letter

    if guess not in chosen_word:
        lives -= 1
        if lives == 0:
            end_of_game = True
            print("You lose.")

    print(" ".join(display))
    if "_" not in display:
        print("You win!")
```

## Project Structure

```
Hangman/
├── README.md
├── hangman.py
├── hangman_words.py
└── hangman_art.py
```

## Contributing

Contributions are welcome! If you want to enhance the game or fix bugs, feel free to fork the repository and submit a pull request.

## Author

- [Aditya Kumar](https://github.com/aditya-kr86)

## License

This project is open-source and available under the MIT License.

## Feedback

For any feedback or suggestions, please reach out to me at [adityakumargupta082003@gmail.com](mailto:adityakumargupta082003@gmail.com).
