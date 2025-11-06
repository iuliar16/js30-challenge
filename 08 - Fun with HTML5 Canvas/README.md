# PROJECT DESCRIPTION

This project creates a window size canvas that you can draw using the mouse.
We have html element canvas with the id = draw, which we grab using document.getElementById and gets the 2D API we will use to draw with. (getContext('2d'))

In order to make the canvas fill the windows we use:

  canvas.width=window.innerWidth;
  canvas.height=window.innerHeight;

The strokestyle BADA55 applied is the starting stroke color, and we use lineJoin and lineCap = round so we have rounded corners where lines meet, and globalCompositeOperation = multiply creates some kind of color-blend effect where lines overlap.

isDrawing is a flag used to know when to draw(only when the mouse id down)

lastX and lastY are the last mouse position

hue is the color hue in HSL; and it will cycle from 0 to 359

direction is a flag that controls wether the line width is growing or shrinking.

The function draw sets the current hue to strokeStyle and increases hue at every call, and because hue becomes a very large value, when it comes to 360 it sets it back to 0.
We use the method beginPath() to start the line, then:

ctx.moveTo(lastX, lastY);     - to start where the last segment ended, then:

 ctx.lineTo(e.offsetX, e.offsetY); - to end at current mouse position

  [lastX, lastY] = [e.offsetX, e.offsetY];  - update last position for the next mousemove event.

  As long as the linewidth is between 1 and 100, we just increase or decrease the linewidth in function of direction, for example- direction is true and linewidth is 90, then for the next 10 calls of the function we will just increase the lineWidth, when we hit linewidth=100, the direction will become False, and from now on we decrease the lineWidth until it reaches 0, then grow again and so on.

  The draw function is called on event mousemove, and on event mousedown (so when we click the screen), the flag isDrawing becomes true so only when we keep the mouse clicked and move the mouse we will draw, here we also set lastX and lastY again to the starting point will be exactly under the cursor, and not 0,0.

  On events mouseup (when mouse is released) and mouseout (cursor leaves the canvas) we prevent drawing with isDrawing = false.

# WHAT I LEARNED

I worked with canvas before and I was familiar with these funtions, but I did not use hsl before and it was interesting to me how he worked with the direction and lineWidth. And I also did not know about globalCompositeOperation before.