# Password-Generator
import random
import string

def generate_password(length, use_uppercase=True, use_digits=True, use_special=True):
    if length < 1:
        raise ValueError("Password length must be at least 1.")
    
    characters = string.ascii_lowercase
    if use_uppercase:
        characters += string.ascii_uppercase
    if use_digits:
        characters += string.digits
    if use_special:
        characters += string.punctuation

    password = ''.join(random.choice(characters) for _ in range(length))
    return password

if __name__ == "__main__":
    try:
        length = int(input("Enter the desired length of the password: "))
        generated_password = generate_password(length)
        print(f"Generated Password: {generated_password}")
    except ValueError as e:
        print(f"Error: {e}")
