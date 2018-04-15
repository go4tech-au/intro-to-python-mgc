# intro-to-python [Turtle Race](http://projects.codeclubworld.org/en-GB/07_python_01/03/Turtle%20Race.html)
Introduction to Python (1 hour version)

In this project you will be familiar with programming concepts below:

- Importing libraries, importing Turtle and Random libraries
- For loops
- Object Oriented Programming concepts (Class, object)


#### Step 1  
  Open Visual studio code and ensure Python Extension is installed
#### Step 2  
  Create a new folder and name it 'Tuttle_Race_Python'
#### step 3 
  add a new file to the folder and name it 'main.py'

#### step 4  
  time to start coding! Lets import Turtle library, so add the code below to 'main.py' file

 ``` from turtle import * ```

#### Step 5  
  Add the following code to draw first vertical line using the ‘turtle’:

 ```
    write(0)        // The turtle write function writes text to the screen
    right(90)       // The turtle right function rotate 90 degree to the right
    forward(10)     // move 10 steps to the direction of casor
    pendown()      
    forward(150)    // draw a vertical line for 150 steps
    penup()         // as you want to draw the next line, you need to go back to the start point, so pen up
    backward(160)   // move 150 + 10 steps backwars
    left(90)        // need to move to the right side, so rotate 90 degree to the left
    forward(20)     // then move forward for 20 steps
```


you need to follw steps above for each line in the race track, so you can write the code 15 times, the only thing that changes is the number to write.!!! 
Did you notice that your code is very repetitive? There’s a better way of doing this in Python. You can use a for loop.

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

** The turtle starts at coordinates (0,0) in the middle of the screen. you can move the turtle to the top left instead, add the code before your for-loop:
  ``` goto(-140,140) ```
  
  oops, you’ll want to lift the pen up first! so add thses 2 lines of code before your for-loop:
 ```
  penup()
  goto(-140,140)
```

run the project to see if you are building the racing track as expected.

#### step 6  
  lets move to the next step and add some racing turtle objects using 'Turtle'.

```
redTurtle = Turtle()      // create a new turtle and name it 'redTurtle'
redTurtle.color('red')    // set color propery to 'red'
redTurtle.shape('turtle') // set shape property to 'turtle'

redTurtle.penup()         
redTurtle.goto(-160,100)   // move redTurtle to start point
redTurtle.pendown()
```

run the project and see if everything look right.

you need to create more turtles, lets say 3;

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

##### step 7  
  lets make the turtles move, you can use forward function to move each turtle: 
  
```
redTurtle.forward(5)  // 'redTurtle' will move 5 steps forward.
```

It would be really boring if the turtles did the same thing every time so they will move a random number of steps each turn. The winner is the turtle that gets the furthest in 100 turns. You’ll need the randint function from the Python random library. Add this import line to the top of your code:

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