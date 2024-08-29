import random
import string


def generate_password(length=12):

    characters = string.ascii_letters + string.digits
    password = ''.join(random.choice(characters) for i in range(length))
    return password


if __name__ == "__main__":
    print("Welcome to Random Password Generator!")
    while True:
        password_length = int(input("Enter the length of the password (minimum 4): "))
        if password_length < 4:
            print("Password length should be at least 4 characters.")
            continue

        password = generate_password(password_length)
        print(f"Your random password is: {password}")

        try_again = input("Generate another password? (yes/no): ").lower()
        if try_again != 'yes':
            break

    print("Thank you for using the Random Password Generator!")
