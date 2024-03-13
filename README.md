Pong is a two-dimensional sports game that simulates table tennis. The player controls an in-game paddle by moving it vertically across the left or right side of the screen. Players use the paddles to hit a ball back and forth. The goal is for each player to reach eleven points before the opponent; points are earned when one fails to return the ball to the other. Let’s build a PONG game with basic knowledge of Python.

About the Pong Game Project using Python
The objective of the project is to develop a Pong Game game using the turtle module in python. In this game we have two players that will move two paddles up and down and a ball. The goal is to defeat your opponent by being the first one to gain 10 points, a player gets a point once the opponent misses a ball. The game can be played with two human players, or one player against a computer controlled paddle.

Project Prerequisites
To develop this game we need a basic knowledge of this game and models like turtle.

turtle – is a Python module that provides a drawing board-like feature, which enables users to create pictures and shapes.
Download Python Pong Game Source Code
Please download the full source code of python pong game: Pong Game Source Code

Steps to Build Pong Game in Python
Let’s see the step to create python PONG Game


First import turtle model.
Create a display window for PONG Game.
Create a left and right paddle, adjust its position and then create the ball and adjust the position of the ball.
Now create functions to control the paddles and ball.
Project File Structure
Importing modules
Creating display function
Define Function
Creating main function
1. Importing Modules
We first import all the necessary libraries required for this project.

# ==== Importing all necessary libraries
import turtle as tl
2. Create Display Window
We will create a main class which is named PONG, where we create an initiator function in which we pass all the functions to display over the screen. Now, we set the title, geometry and background color for the interface.

class PONG:
   def __init__(self):
       self.create_window()
       self.leftpaddle()
       self.rightpaddle()
       self.create_ball()
       self.keys()
       self.game()
   def create_window(self):
       self.root = tl.Screen()
       self.root.title("PONG GAME by PythonGeeks")
       self.root.bgcolor("yellow")
       self.root.setup(width=600, height=400)
       self.root.tracer(0)
3. Define functions
Now, let’s create different functions which are going to be used in this project.


i. leftpaddle() – this function will create a left paddle by giving its shape, color and shape size.

def leftpaddle(self):
    self.left_paddle = tl.Turtle()
    self.left_paddle.speed(0)
    self.left_paddle.shape('square')
    self.left_paddle.color('red')
    self.left_paddle.shapesize(stretch_wid=7, stretch_len=1.2)
    self.left_paddle.penup()
    self.left_paddle.goto(-280, 0)
ii. rightpaddle() – this function will create a right paddle by giving its shape, color and shape size.

def rightpaddle(self):
    self.right_paddle = tl.Turtle()
    self.right_paddle.speed(0)
    self.right_paddle.shape('square')
    self.right_paddle.color('white')
    self.right_paddle.shapesize(stretch_wid=7, stretch_len=1.2)
    self.right_paddle.penup()
    self.right_paddle.goto(280, 0)
iii. create_ball() – this function will create a ball by giving its shape, color, ball direction on x and y axis and shape size.


def create_ball(self):
      self.ball = tl.Turtle()
      self.ball.speed(0)
      self.ball.shape('circle')
      self.ball.color('green')
      self.ball.penup()
      self.ball.goto(5,5)
      self.ball_direction_x = 0.2
      self.ball_direction_y = 0.2
iv. left_paddle_up() – this function will help to move the left paddle in upward direction.

def left_paddle_up(self):
    y = self.left_paddle.ycor()
    y = y + 20
    self.left_paddle.sety(y)
v. left_paddle_down() – this function will help to move the left paddle in downward direction.

def left_paddle_down(self):
      y = self.left_paddle.ycor()
      y = y - 20
      self.left_paddle.sety(y)
vi. right_paddle_up() – this function will help to move the right paddle in upward direction.

def left_paddle_down(self):
      y = self.left_paddle.ycor()
      y = y - 20
      self.left_paddle.sety(y)
vii. right_paddle_down() – this function will help to move the right paddle in downward direction.

def right_paddle_down(self):
      y = self.right_paddle.ycor()
      y = y - 20
      self.right_paddle.sety(y)
viii. keys() – this function will accept the key values and pass it to the function.

def keys(self):
    self.root.listen()
    self.root.onkeypress(self.left_paddle_up, "w")
    self.root.onkeypress(self.left_paddle_down, "s")
    self.root.onkeypress(self.right_paddle_up, "Up")
    self.root.onkeypress(self.right_paddle_down, "Down")
ix. game() – this is the main game function in which all the required methods are passed to run the game.


def game(self):
    while True:
        self.root.update()
        self.ball.setx(self.ball.xcor() + self.ball_direction_x)
        self.ball.sety(self.ball.ycor() + self.ball_direction_y)
        if self.ball.ycor() > 190:
            self.ball.sety(190)
            self.ball_direction_y *= -1
        if self.ball.ycor() < -190:
            self.ball.sety(-190)
            self.ball_direction_y *= -1
        if self.ball.xcor() > 260:
            self.ball.goto(0, 0)
            self.ball_direction_x *= -1
        if self.ball.xcor() < -260:
            self.ball.goto(0, 0)
            self.ball_direction_x *= -1
        if (self.ball.xcor() > 210) and (self.ball.xcor() < 220) and (
                self.ball.ycor() < self.right_paddle.ycor() + 40 and self.ball.ycor() > self.right_paddle.ycor() - 40):
            self.ball.setx(210)
            self.ball_direction_x *= -1
        if (self.ball.xcor() < -210) and (self.ball.xcor() > -220) and (
                self.ball.ycor() < self.left_paddle.ycor() + 40 and self.ball.ycor() > self.left_paddle.ycor() - 40):
            self.ball.setx(-210)
            self.ball_direction_x *= -1
4. Creating main function
In the main function, the main window of the turtle is made and the creation of objects for the main class is done.

def main():
   PONG()
if __name__ == '__main__':
   main()
Python Pong Game Output
python pong game output

Summary
YAY!! We have successfully developed the PONG game project in python. We learned different modules of python in this project like turtle. You can add more features as much as you can to perform more tasks.
