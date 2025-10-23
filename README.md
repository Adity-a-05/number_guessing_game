# number_guessing_game
A Python number guessing game with levels and increasing difficulty.
# Number Guessing Game 🎮

import random

print("🎮 Welcome to the Number Guessing Game with Levels! 🎯")
print("You’ll start from Level 1 (1–10). Each level increases the range!\n")

level = 1
max_range = 10

while True:
    print(f"\n--- LEVEL {level} ---")
    print(f"Guess the number between 1 and {max_range}")

    secret = random.randint(1, max_range)
    attempts = 0

    while True:
        try:
            guess = int(input("Enter your guess: "))
        except ValueError:
            print("❌ Please enter a number!")
            continue

        attempts += 1

        if guess == secret:
            print(f"🎉 Correct! You guessed it in {attempts} attempts!")
            print(f"✅ Level {level} completed!\n")
            break
        elif guess < secret:
            print("Too low! ⬆️")
        else:
            print("Too high! ⬇️")

    next_level = input("Do you want to go to the next level? (yes/no): ").lower()
    if next_level == "yes":
        level += 1
        max_range += 10
    else:
        print("\n🏁 Game Over! You reached Level", level)
        print("Thanks for playing, legend! 💪")
        break
