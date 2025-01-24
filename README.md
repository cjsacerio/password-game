# password-game
import re

def check_password_strength(password):
    # Criteria for a secure password
    if len(password) < 8:
        return "Password is too short! Must be at least 8 characters long."
    if not re.search(r"[A-Z]", password):
        return "Password must contain at least one uppercase letter."
    if not re.search(r"[a-z]", password):
        return "Password must contain at least one lowercase letter."
    if not re.search(r"[0-9]", password):
        return "Password must contain at least one number."
    if not re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        return "Password must contain at least one special character."
    return "Password is secure!"

def main():
    print("Welcome to the Secure Password Game!")
    print("Your goal is to create a secure password that meets all of the following criteria:")
    print("1. At least 8 characters long")
    print("2. Contains at least one uppercase letter")
    print("3. Contains at least one lowercase letter")
    print("4. Contains at least one number")
    print("5. Contains at least one special character (e.g. !@#$%^&*)")

    while True:
        password = input("\nEnter your password: ")
        result = check_password_strength(password)
        print(result)
        if result == "Password is secure!":
            break

if __name__ == "__main__":
    main()
