# Welcome to My Moving Box Realtime
***

## Task
To move the box to the bottomright(0,0) position but the challenge is that it should move diagonally through the screen and it should take 35 seconds to reach its destination.

## Description

HTML Structure:
The HTML code creates a <div> element with the ID my_box_realtime. This element serves as the container for the moving box.
html
Copy code
<div id="my_box_realtime" style="background-color: red; position: absolute; right: 70; bottom: 70; min-width: 100px; min-height: 100px"></div>
CSS Styling:

The inline style attribute in the HTML code sets the initial styling properties of the box. Notably, it gives the box a red background color and positions it absolutely on the webpage. The starting position is defined with right: 70 and bottom: 70. Minimum width and height are also specified.
JavaScript Logic:

The JavaScript code provides the real-time movement of the box. It starts by obtaining a reference to the <div> element using document.getElementById("my_box_realtime").
The num variable is initialized with the value 70. This variable is used to dynamically update the position of the box.
The move_box() function is defined to adjust the right and bottom properties of the box, creating a diagonal movement effect.
Finally, the setInterval() function is used to repeatedly call the move_box() function at intervals of 500 milliseconds (0.5 seconds), creating the appearance of real-time movement.
javascript
Copy code
let position = document.getElementById("my_box_realtime");
let num = 70;

function move_box() {
    position.style.right = num;
    position.style.bottom = num;
    num--;
}

setInterval(move_box, 500);
In summary, the problem is solved by combining HTML for creating the box, CSS for initial styling, and JavaScript for dynamic and real-time movement. The key logic lies in the move_box() function, which is called at regular intervals to update the box's position and create the desired effect. Users can further customize or integrate this code into larger projects based on their requirements.


## Installation
Since the project involves simple HTML and JavaScript, there might not be a need for complex build processes or package management like npm or make.

## Usage
HTML and JavaScript code creates a red box that moves diagonally on the screen in real-time. Let's break down how it works:

HTML Code:

The <div> element with the ID my_box_realtime represents the red box. Its initial position is set to right: 70 and bottom: 70 to start at a specific location on the screen.
The style attribute includes additional styling properties like min-width and min-height to define the minimum dimensions of the box.
JavaScript Code:

The JavaScript code starts by getting a reference to the <div> element with the ID my_box_realtime using document.getElementById("my_box_realtime").
The variable num is initialized with the value 70. This variable will be used to update the position of the box.
The move_box() function is defined, which updates the right and bottom CSS properties of the box. It effectively moves the box diagonally on the screen by decrementing the num variable.
The setInterval() function is used to repeatedly call the move_box() function at intervals of 500 milliseconds (0.5 seconds). This creates the real-time effect of the box moving.
In summary, the code creates a red box in the HTML, and the JavaScript function move_box() adjusts its position at regular intervals, giving the appearance of real-time movement. Users can customize the HTML and JavaScript code to fit their specific needs or integrate it into larger projects.

### The Core Team

<span><i>Made at <a href='https://qwasar.io'>Qwasar SV -- Software Engineering School</a></i></span>
<span><img alt='Qwasar SV -- Software Engineering School's Logo' src='https://storage.googleapis.com/qwasar-public/qwasar-logo_50x50.png' width='20px' /></span>
