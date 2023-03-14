# RaycastingJS
This project consists of raycasting demos in JavaScript. I've included a euclidean angles example and a vector based example. A debugging version showing the overhead 2D view along side the rendered raycaster is also included. These are meant to be a jumping off point for you to build a Wolfenstein 3D style raycasting game in the browser, or to learn about how raycasters work. In my opinion, the modern browser is a fantastic medium for this.
<img width="1141" alt="Screen Shot 2023-03-14 at 4 07 49 PM" src="https://user-images.githubusercontent.com/127203032/225161920-1e6db28e-7cec-4cd9-99fa-97b9c733933a.png">

I've set the maps to the same layout in both approaches for comparison. Both demos should look nearly identical when rendered. The vectors-based version uses less code and is a good choice for building off of, while the euclidean example uses angles intuitively and works in a similar way to many other raycasters.

## Euclidean Version
By "euclidean" it is simply meant that we are using a player angle, field of view (fov) and iterating through that fov at different ray angles calcuated based on the player angle, fov and current ray number. We then use a series of trigonometric calculations to cast rays and determine the ultimate line height for each ray. This version uses one of the most common techniques for raycasting and is relatively intuitive when programming game logic by thinking in terms of the player's xy position and angle. Like other examples that use this technique, "fisheye" correction is needed before rendering, though this only amounts to multiplying the calculated distance by the cosine of the playerAngle - rayAngle.

<img width="300" alt="Screen Shot 2023-03-14 at 4 18 54 PM" src="https://user-images.githubusercontent.com/127203032/225162175-167a8657-dc46-42a3-9cf5-3a794bdee912.png">&nbsp;&nbsp;&nbsp;&nbsp;<img width="535" alt="Screen Shot 2023-03-14 at 4 18 54 PM" src="https://user-images.githubusercontent.com/127203032/225163288-4d535a5b-3185-473a-92b8-33aa903b668b.png">

## Vectors Version
This version primarily uses vectors in XY space rather than doing a series of trigonometric calculations. Though initially thinking in terms of fov and player angle can be intuitive, ultimately the same calculations can be accomplished more efficiently and with less code using a vector based approach. This version is adapted from Lode Vandevenne's C++ tutorial into a JavaScript version. See his excellent tutorial here: https://lodev.org/cgtutor/raycasting.html

## 2D View and Debugging
It can both be informative in learning about how raycasters work, as well as extremely useful for debugging to see the overhead 2D view that the raycaster builds it's semi 3D graphics from. I've included a debugging version here to show the two side-by-side. This can be very helpful for designing levels and testing. Because more rendering is needed to show both, you'll probably want to run this at a lower frame rate which can easily be changed in the section toward the bottom of the code by changing the value of the FPS variable.

<img width="1141" alt="Screen Shot 2023-03-14 at 4 07 49 PM" src="https://user-images.githubusercontent.com/127203032/225161920-1e6db28e-7cec-4cd9-99fa-97b9c733933a.png">

## Texturing Walls, Adding Ceilings and Floors
These demos are meant as a jumping off point and include single color walls with some basic lighting. Using textured walls like in Wolfenstein 3D and other famous raycasters is fairly straightforward, as is creating ceilings and floors. For this, I'll point you to Lode Vandevenne's fantastic tutorial:

Adding Textures: https://lodev.org/cgtutor/raycasting.html#Textured_Raycaster   
Floors and Ceilings: https://lodev.org/cgtutor/raycasting2.html

<img width="396" alt="Screen Shot 2023-03-14 at 4 47 26 PM" src="https://user-images.githubusercontent.com/127203032/225166810-48ad1222-a084-4931-bed5-7b80cd8eb061.png">

## Sprites, Items, and Enemies
Sprites representing items and enemies can easily be added as well. Items/weapons can often be rendered as a simple overlay after walls have been rendered. For some really nice Wolfenstein-style sprite to play around with, checkout these sprites from a GZDoom mod by user itsmeveronica: https://www.moddb.com/mods/volkograd-3d/images/makarov-reload-animation#imagebox. You can right-click and save the images, and then load them into the canvas. For details on code implementation, see this tutorial: https://lodev.org/cgtutor/raycasting3.html 
![Super_Huge_41](https://user-images.githubusercontent.com/127203032/225162576-45fd076d-79c8-41ff-a202-dbc64724b406.gif)
![sprite](https://user-images.githubusercontent.com/127203032/225162328-24d32d4a-eedd-4c16-8559-53310f2cb512.gif)
