# Game-of-Adventure
def play_game():
    # Welcome message for the player
    print(" Welcome to The Adventure Game!")

    # Ask the player for their name (string input)
    name = input("Enter your name, brave adventurer: ")

    # Dictionary to store locations and short outcome messages
    locations = {
        "forest": "You enter a dark forest and find a mysterious chest.",
        "cave": "You step into a cave... suddenly a wild bear appears!",
        "river": "You approach a fast-flowing river. A boat is nearby."
    }

    # Ask the player to choose a location
    print("\nChoose your path: forest / cave / river")
    choice = input("Where do you want to go? ").lower()  # convert input to lowercase

    # Check if the choice is valid
    if choice not in locations:
        print("❌ Invalid choice! Please restart the game and choose a valid location.")
        return  # exit the function if invalid

    # Show the location message
    print(f"\n{name}, {locations[choice]}")

    # If the player chooses the forest, they get another decision
    if choice == "forest":
        # List of valid actions
        valid_actions = ["open", "ignore"]

        # Ask the player what they want to do with the chest
        action = input("Do you want to 'open' the chest or 'ignore' it? ").lower()

        # Validate the action
        if action not in valid_actions:
            print("❌ Invalid action. The adventure ends abruptly...")
            outcome = "Unknown fate"
        elif action == "open":
            print("✨ You opened the chest and found GOLD!")
            outcome = "Found treasure"
        else:
            print("😊 You ignored the chest and walked away safely.")
            outcome = "Walked away safely"

    # If the player chooses the cave
    elif choice == "cave":
        print("😱 The bear attacks! You barely escape with your life.")
        outcome = "Attacked by a bear"

    # If the player chooses the river
    else:  
        print("⛵ You use the boat to escape safely downstream.")
        outcome = "Escaped on a boat"

    # Store the summary in a tuple (immutable data type)
    summary = (name, choice, outcome)

    # Display the adventure summary
    print("\n📜 Adventure Summary:")
    print(f"Player: {summary[0]}")
    print(f"Location chosen: {summary[1]}")
    print(f"Final outcome: {summary[2]}")


# Run the game by calling the function
if __name__ == "__main__":
    play_game()
