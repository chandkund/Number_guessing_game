import random
import math
start_range = int(input("Enter start range"))
end_range = int(input("Enter start range "))

randomly_selection = random.randint(start_range,end_range)
print(randomly_selection)

print("you have only",
      round(math.log(end_range-start_range+1,2)),
      "Chances to guess the integer !")
count= 0
while(count<math.log(end_range-start_range+1,2)):
    count+=1
    guess = int(input("guess a number"))

    if(guess == randomly_selection):
        print("congratulations")
    elif(guess > randomly_selection):
        print("Try again! You guessed too high")
    elif(guess < randomly_selection):
        print("Try Again ! you guessed too small")

if (count>= math.log(end_range-start_range+1,2)):
    print("\n The number is %d" % randomly_selection)
    print("Better Luck Next Time")
