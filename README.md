Simple Password Strength Checker

def check_password_strength(password):
    score = 0

    # Check length
    if len(password) >= 8:
        score += 1

    # Check for uppercase letters
    if any(char.isupper() for char in password):
        score += 1

    # Check for lowercase letters
    if any(char.islower() for char in password):
        score += 1

    # Check for numbers
    if any(char.isdigit() for char in password):
        score += 1

    # Check for special characters
    if any(char in "!@#$%^&*()-_+=<>?/{}[]|\\:;.,~" for char in password):
        score += 1

    # Determine strength
    if score <= 2:
        return "Weak Password"
    elif score == 3 or score == 4:
        return "Medium Password"
    else:
        return "Strong Password"


# Main Program
print("=== Simple Password Strength Checker ===")
user_password = input("Enter your password: ")

result = check_password_strength(user_password)
print("Password Strength:", resul
