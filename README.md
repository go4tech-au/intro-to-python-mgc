# intro-to-python [Turtle Race](http://projects.codeclubworld.org/en-GB/07_python_01/03/Turtle%20Race.html)
## Introduction to Python (1 hour version)

In this project you will learn programming concepts below:

- Importing libraries (Turtle & Random)
- **for** loops
- Object Oriented Programming concepts (Class, object)


#### Step 1  
  Open Visual Studio Code and ensure Python extension is installed

#### Step 2  
  Create a new folder and name it 'Tuttle_Race_Python'

#### Step 3 
  Add a new file to the folder and name it 'main.py'

#### Step 4  
  Time to start coding! Let's import Turtle library, so add the code below to 'main.py' file

 ``` from turtle import * ```

#### Step 5  
  Add the following code to draw first vertical line using the ‘turtle’:

 ```
    write(0)        # The turtle *write* function writes text to the screen
    right(90)       # The turtle *right* function rotates 90 degrees to the right
    forward(10)     # Move 10 steps to the direction of cursor
    pendown()      
    forward(150)    # Draw a vertical line for 150 steps
    penup()         # As you want to draw the next line, you need to go back to the starting point, so pen up
    backward(160)   # Move 150 + 10 steps backwars
    left(90)        # Need to move to the right side, so rotate 90 degrees to the left
    forward(20)     # Then move forward 20 steps
```

#### Step 6
You need to follow steps above for each line in the race track, so you can write the code 15 times, the only thing that changes is the number to write!!! 
Did you notice that your code is very repetitive? There’s a better way of doing this in Python. You can use a **for** loop.

```
for step in range(14):
    write(step)
    right(90)
    forward(10)
    pendown()
    forward(150)
    penup()
    backward(160)
    left(90)
    forward(20)
```

#### Step 6
The turtle starts at coordinates (0,0) in the middle of the screen. You can move the turtle to top left instead, add the following line before your for-loop:
  ``` goto(-140,140) ```

#### Step 7
  Oops, you’ll want to lift the pen up first! so add these 2 lines of code before your for-loop:
 ```
  penup()
  goto(-140,140)
```

#### Step 8
Run the project to see if you are building the racing track as expected.

#### Step 9
Lets move to the next step and add some racing turtle objects using 'Turtle'.

```
redTurtle = Turtle()      # Create a new turtle and name it 'redTurtle'
redTurtle.color('red')    # Set color propery to 'red'
redTurtle.shape('turtle') # Set shape property to 'turtle'

redTurtle.penup()         
redTurtle.goto(-160,100)   # Move red turtle to start point
redTurtle.pendown()
```

Run the project and see if everything looks right.

#### Step 10
You need to create more turtles, lets say 3;

```
yellowTurtle = Turtle()
yellowTurtle.color('yellow')
yellowTurtle.shape('turtle')

yellowTurtle.penup()
yellowTurtle.goto(-160,10)
yellowTurtle.pendown()

blueTurtle = Turtle()
blueTurtle.color('blue')
blueTurtle.shape('turtle')

blueTurtle.penup()
blueTurtle.goto(-160,70)
blueTurtle.pendown()

greenTurtle = Turtle()
greenTurtle.color('green')
greenTurtle.shape('turtle')

greenTurtle.penup()
greenTurtle.goto(-160,40)
greenTurtle.pendown()
```

##### Step 11  
Lets make the turtles move, you can use forward function to move each turtle: 
  
```
redTurtle.forward(5)  # 'redTurtle' will move 5 steps forward.
```

##### Step 12  
It would be really boring if the turtles did the same thing every time; so let's make them move random number of steps each turn. Winner is the turtle that gets the furthest in 100 turns. You’ll need the *randint* function from the python *Random* library. Add this import line to the top of your code:

```
from random import randint
```

The randint function returns a random integer (whole number) between the values chosen. The turtle will move forward 1, 2, 3, 4, or 5 steps at each turn.

```
for turn in range(100):
    redTurtle.forward(randint(1, 5))  
    greenTurtle.forward(randint(1, 5))
    blueTurtle.forward(randint(1, 5))
    yellowTurtle.forward(randint(1, 5))
   ```
   
Now you’re ready to race, run the project and see the result
    
### Challenge: Do a twirl
Can you use a for turn in range(): loop to make each turtle do a 360 degree twirl after they get to the starting line? You’ll need to make sure they are facing in the right direction at the start of the race!

red.right(36) will turn the red turtle right by 36 degrees.

Hint: A full turn is 360 degrees. A turtle could turn right 10 degrees 36 times. Or left 5 degrees 72 times. Or …