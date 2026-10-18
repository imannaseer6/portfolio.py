
import random

# List of secret words
words = ["PYTHON", "COMPUTER", "HANGMAN", "SCIENCE", "PROGRAM"]

# ASCII art for each stage
stages = [
    """
     +---+
         |
         |
         |
        ===
    """,
    """
     +---+
     O   |
         |
         |
        ===
    """,
    """
     +---+
     O   |
     |   |
         |
        ===
    """,
    """
     +---+
     O   |
    /|   |
         |
        ===
    """,
    """
     +---+
     O   |
    /|\\  |
         |
        ===
    """,
    """
     +---+
     O   |
    /|\\  |
    /    |
        ===
    """,
    """
     +---+
     O   |
    /|\\  |
    / \\  |
        ===
    """
]

# Select a random word
secret_word = random.choice(words)
guessed_letters = set()
wrong_letters = set()
attempts = 6

print("===== WELCOME TO HANGMAN =====")

while attempts > 0:
    # Display the current hangman stage
    print(stages[6 - attempts])

    # Display the hidden word
    masked_word = " ".join(
        letter if letter in guessed_letters else "_"
        for letter in secret_word
    )
    print("Word:", masked_word)
    print("Wrong letters:", sorted(wrong_letters))
    print("Attempts left:", attempts)

    # Check whether the player has won
    if all(letter in guessed_letters for letter in secret_word):
        print("\nCongratulations! You guessed the word:", secret_word)
        break

    guess = input("Guess a letter: ").strip().upper()

    # Validate input
    if len(guess) != 1 or not guess.isalpha():
        print("Please enter one English letter.")
        continue

    # Prevent duplicate guesses
    if guess in guessed_letters or guess in wrong_letters:
        print("You already guessed that letter. Try another!")
        continue

    # Process the guess
    if guess in secret_word:
        guessed_letters.add(guess)
        print("Correct guess!")
    else:
        wrong_letters.add(guess)
        attempts -= 1
        print("Incorrect guess!")

else:
    print(stages[6])
    print("\nGame Over! The word was:", secret_word)

print("Thanks for playing!")
