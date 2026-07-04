# Guessing_Game
import random

def play_guessing_game():
    print("Welcome to the Number Guessing Game!")
    print("I am thinking of a number between 1 and 100.")
    
    # Generate a secret random integer
    secret_number = random.randint(1, 100)
    attempts = 0
    
    while True:
        try:
            
            user_guess = int(input("\nEnter your guess (1-100): "))
            attempts += 1
            
            
            if user_guess < 1 or user_guess > 100:
                print("Out of bounds! Please guess a number from 1 to 100.")
                continue
                
            if user_guess < secret_number:
                print("📉 Too low! Try a higher number.")
            elif user_guess > secret_number:
                print("📈 Too high! Try a lower number.")
            else:
                print(f"🎉 Correct! You found the number {secret_number} in {attempts} attempts!")
                break
                
        except ValueError:
            print("❌ Invalid input! Please enter a valid whole number.")

if __name__ == "__main__":
    play_guessing_game()
