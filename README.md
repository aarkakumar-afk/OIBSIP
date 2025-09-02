# OIBSIP
Python Programming 1. Voice Assistant 2.BMI Calculator 3. Random Password Generator

#VOICE ASSISTANT

import datetime
import webbrowser

def run_assistant():
    print("Hello! I am your assistant. Type 'help' to see what I can do.")

    while True:
        command = input("\nEnter your command: ")

        if "hello" in command:
            print("Assistant: Hi there! How are you?")
        elif "help" in command:
            print("Assistant: How can I help you?")
        elif "time" in command:
            now = datetime.datetime.now().strftime("%H:%M")
            print("Assistant: The time is", now)

        elif "date" in command:
            today = datetime.date.today().strftime("%B %d, %Y")
            print("Assistant: Today's date is", today)

        elif "search" in command:
            query = input("What should I search for? ")
            webbrowser.open(f"https://www.google.com/search?q={query}")
            print("Assistant: Here are the results for", query)

        elif "help" in command:
            print("Assistant: I can respond to 'hello', 'help', tell the 'time', the 'date', 'search' the web, or 'exit'.")

        elif "exit" in command or "stop" in command:
            print("Assistant: Goodbye!")
            break

        else:
            print("Assistant: Sorry, I don't understand that. Try again!")


run_assistant()

__________________________________________________________________________________________________________________________________________

#BMI CALCULATOR

weight = float(input("Enter weight in kilograms: "))
height = float(input("Enter height in meters: "))

bmi = weight / (height ** 2)

if bmi < 18.5:
    category = "Underweight"
elif bmi < 24.9:
    category = "Normal weight"
elif bmi < 29.9:
    category = "Overweight"
else:
    category = "Obesity"

print("\nMy BMI is: {:.2f}".format(bmi))
print("I am classified as:", category)

___________________________________________________________________________________________________________________________________________

#RANDOM PASSWORD GENERATOR

import random
import string


length = int(input("How many characters should the password have? "))


use_letters = input("Do you want letters? (yes/no): ")
use_numbers = input("Do you want numbers? (yes/no): ")
use_symbols = input("Do you want symbols? (yes/no): ")

characters = ""

if use_letters:
    characters += string.ascii_letters
if use_numbers:
    characters += string.digits
if use_symbols:
    characters += string.punctuation


if characters == "":
    print("You must choose at least one option (letters, numbers, or symbols).")
else:

    password = ""
    for i in range(length):
        password += random.choice(characters)


    print("\nHere is your password:", password)



