# assign3
'''
You must use Python 3.x to implement these programs.
Your grade will be based on functionality (does the program do what it is suppose to do) and understandability (are the literals meaningful and is the code modular and well documented with appropriate comments).
Deliverables:

You should submit one doc (or docx or pdf) file named assign3.doc (or .docx or .pdf). This file should contain your python code for the program(s) in the assignment along with the screen shot(s) of your program's sample runs (with output). Make sure to put your python code correctly in this file (with correct indentation). If you have any text for the grader to read before grading, you can include it at the top of this file. 
You should also submit a python file named assign3.py. This file should contain your python code for the program(s) in the assignment. If needed, the code in this file will be executed to confirm the output presented in the word file.
____________________________________________________________________________________________________

Part - I (5 points)

In this Assignment you are going to program a number guessing game. Using a loop is not necessary to complete the assignment, however it can make the code much easier to read rather than using nested IF statements.

Using the nested IF statements approach, the following steps need to be performed:

Initialize a variable called number with a value of 10 and a variable called numAttempts with a value of 0
Ask the user for their name
Ask the user to guess a number between 1 and 20 and store that in a variable guess, increment the numAttempts variable
If guess is same as number then say your guess is correct and you guessed it in n attempt(s), where n is the value of numAttempts variable and your program ends.
If guess is lower than number then print "Your guess is too low". If numAttempts variable < 3, the goto step #7 else goto step #8.
If guess is higher than number then print "Your guess is too high". If numAttempts variable < 3, the goto step #7 else goto step #8
Repeat step #3 - #6.
If the user does not guess the number even after three attempts then print “Your three guesses are over, the number I was thinking of was 10”
Sample 1

Hello! What is your name?
Albert
Well, Albert, I am thinking of a number between 1 and 20.
Take a guess.
15
Your guess is too high.
Take a guess.
4
Your guess is too low.
Take a guess.
12
Your guess is too high. Your three guesses are over. The number I was thinking of was 10

Sample 2

Hello! What is your name?
Albert
Well, Albert, I am thinking of a number between 1 and 20.
Take a guess.
8
Your guess is too low.
Take a guess.
12
Your guess is too high.
Take a guess.
10
Good job, Albert! You guessed my number in 3 guesses!

Optional: Instead of fixing the number to be guessed to 10, you can initialize 'number' variable with a random number between 1 and 20 that you generate using the functions in the random module. This way every time you re run the program, it is a different number to be guessed.

____________________________________________________________________________________________________

Part - II (5 points)

Rock, Paper, Scissor:

Write a program to simulate the paper-rock-scissor game. Each of the two players type in P, R, or S. The program then announces the winner based on the rule: Paper covers Rock, Rock breaks Scissors, Scissors cut Paper, or Nobody wins. Be sure to allow the players to use lowercase as well as uppercase letters.

You MUST implement a function that takes the choices that both the players made and returns 1 if the player 1 won and 2 if the player 2 won and 0 if it is a tie. So the logic of deciding who won based on the rock, paper, scissor rule must be programmed inside this function.

You MUST call this function to decide who won and you must display the result of the game based on the return value of the function.

Sample run:

Player 1: Please enter either (R)ock, (P)aper, or (S)cissors: P

Player 2: Please enter either (R)ock, (P)aper, or (S)cissors: s

Player 2 wins.

Optional: Your program can allow the users to play repeatedly say 5 times. Your program should then keep a score for each player and display that after each play.

Sample run (with optional part):

Player 1: Please enter either (R)ock, (P)aper, or (S)cissors: P

Player 2: Please enter either (R)ock, (P)aper, or (S)cissors: s

Player 2 wins.

Scores after this play:

Player 1: 0

Player 2: 1 

Thanks!!  '''


# Anthony Tolbert - Assignment 3
# Part 1

import random  #import random module

number = random.randint(1,20)    #generate random number between 1 and 20
numAttempts = 0
name = input("What is your name? ")

print("Well, " +name+ " I am thinking a number between 1 and 20.")


while numAttempts < 3:
    guess = int(input("Take a guess: \n"))         #get input from user
    numAttempts +=1                             #increment numAttempts variable

    if (guess < number):
        print("Your guess is too low." )
    elif (guess > number):
        print("Your guess is too high.")
    elif guess == number:
        break                               #break out of loop if guess matches number

if numAttempts == 3 and guess != number:
    print("Your three guesses are over! The number I was thinking was",number)
if guess == number:
    print("Good Job " +name+ " You guessed the number I was thinking in", numAttempts,"guess.")



# Anthony Tolbert Assignment 3
# Part 2

def game(player1, player2):
    """Creation of the game function"""
    if player1 == "P" and player2 == "R":
        return 1
    elif player1 == "S" and player2 == "P":
        return 1
    elif player1 == "R" and player2 == "S":
        return 1
    elif player1 == "P" and player2 == "S":
        return 2
    elif player1 == "R" and player2 == "P":
        return 2
    elif player1 == "S" and player2 == "R":
        return 2

    elif player1 == player2:
        return 0
    else:
        exit() #exit out of program

for i in range(5):          #create for loop so that game runs 5 times
    player1 = input("Player 1: Please enter either (R)ock, (P)aper, or (S)cissors: ")  #choice from player 1
    player2 = input("Player 2: Please enter either (R)ock, (P)aper, or (S)cissors: ")  #choice from player 2
    winner = game(player1.capitalize(),player2.capitalize()) #calling the game function
    print("Player " + str(winner) + " wins")        #display winner to console








