# PROJECT DESCRIPTION

This project works with the mousemove event and css properties to simulate the moving of some text.

We have a div (hero) containing a h1 (text).
The function shadow uses destructuring to extract the width and height of hero and gets the cursor position inside the element (offsetX and offsetY).

We have to normalize the coordinates, so if the event target is not hero itself (we moved over h1 inside it), we have to adjust the coordinates.

We use walk = 500 to set how far the shadow can move. To calculate hor far to "walk", we use x/width which gives the horizontal percentage of the cursor position across the container and we multiply that by walk, then substract half so the shadow can move both left/right and up/down from the center.

Then we set the textShadow by creating 3 shadows in different directions and colors.

# WHAT I LEARNED

I used before the destructuring assigment but still this tutorial reminded me of how to use it. It was also intersting how he recalculated the css properties on every mousemove to simulate the moving of the text.
