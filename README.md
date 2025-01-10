import random
import sys
from enum import Enum


class RPS(Enum):
    Rock = 1
    Paper = 2
    Scissors = 3


player_input = input(
    "Let's play a game! Choose your option 1 for Ro1ck, 2 for Paper or 3 for Scissors:")
player = int(player_input)

if (player < 1 or player > 3):
    sys.exit("You must enter 1, 2 or 3")
print("")
print("You chose " + str(RPS(player)).replace("RPS.", "") + ".")

computer_input = random.choice("123")
computer = int(computer_input)
print("Computer chose " + str(RPS(computer)).replace("RPS.", "") + ".")

if (player == 1 and computer == 3):
    print("You win!")
elif (player == 2 and computer == 1):
    print("You win!")
elif (player == 3 and computer == 2):
    print("You win!")
elif (player == computer):
    print("It's a tie!")
else:
    print("Computer wins!")
