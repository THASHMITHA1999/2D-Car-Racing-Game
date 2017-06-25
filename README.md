# 2D-Car-Racing-Game
A 2D car racing game in C using openGL interface, basic graphic functions.

Using various basic graphics functions to establish our goal to implement a visual appealing ,single player simple 2D game, a car racing game, developed using openGL. In this game, there is a car and which moves forward in a road using up arrow key. The sides of the road on which the car is moving can be changed using keyboard side arrow keys and its speed can be decreased using down arrow key. The score keeps on increasing till the car moves forward. When the car encounters other obstacles present in the road, the game ends. At the end the score is displayed.

This graphics is developed as a model which shows how to combine color, lighting effects, transformations of an object, viewing, increasing and decreasing the objects in real time with OpenGL.

## Methodology

The methodology of this project includes all the user defined functions used in the code for creating the vehicles and movement of these vehicles. These are:
#### 1.drawText():
This function has three arguments which are score stored in an array, x co-ordinate position and y co-ordinate position where the function should be displayed. It displays the text for score using glRasterPos2f( xpos , ypos) function.
#### 2. drawRoad():
This function draws a black colored rectangle of 200x500 dimension which displays the road. The road contains the dividers, the racing car and opponent cars.
#### 3. drawDivider():
This function when called draws 10 white colored 10x36 rectangles using translation at the middle of road which represents the divider of road.
#### 4. drawVehicle():
This function is used to draw the vehicle which has four parts : tires, middle body , upper body and lower body. Tires are the points and the body parts are quadrilaterals of different shapes and sizes. The middle body is 50x40 while upper and lower body are trapezium of (46,38)x20.
#### 5. drawOVehicle():
This function draws the opponent vehicles and detects the collision. The opponent vehicle has same appearance as the racing car only differs in color.
It detects the collision when racing car and opponent vehicle has same x co-ordinate (horizontal colliding) . At the same time when racing car collides opponent vehicles from behind or when opponent vehicle collides with the racing car.
If the collision is not detected then more opponent cars are drawn otherwise collision value is returned true.
#### 6. ovpos():
This function returns the position for the opponent vehicles which is random.
#### 7. specialKey():
This function is used to enable navigation keys for movement of car. The left and right keys are used for left and right movement of the car respectively. While up and down navigation keys are used for the acceleration and deceleration of the racing car respectively.
#### 8. display():
This is the main display function where all the other functions are called. The score value is increased by one until the car has not collided. If the collision has return value true then exit status is returned.

## Works done

Basically it is based on the logic that the y co-ordinates of opponent cars are decreased constantly and we can change the x co-ordinate of racing car using left and right navigation keys.

The acceleration of the racing car is shown by moving the dividers backward (decreasing y co-ordinates) constantly. Similarly, deceleration of the car is shown by constantly moving the dividers in positive y direction.

The left and right movement of car is achieved using specialKey() function. When left key is pressed then the x co-ordinate of car changes to 200 i.e left of divider and when right key is pressed then the x co-ordinate of car changes to 300 i.e right of divider.

The movement of the cars is shown by changing the y co-ordinates of dividers constantly which is achieved using glutPostReDisplay and gutIdleFunc.
The game is over when any type of collision occurs.
