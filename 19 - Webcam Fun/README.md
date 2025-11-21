# PROJECT DESCRIPTION

This project uses webRTC API to access the user's webcam and display the live video feed directly on a webpage.

We first get the dom elements with document.querySelector. The function getVideo uses getUserMedia to ask permission for the camera only and on success, sets video.srcObject to the stream and starts video.play().

The function paintToCanvas() is used to draw video frames on the canvas and apply some effects. drawImage copied the video framte to the canvas and getImageData pulls the raw pixel data (an RGBA array).
We then apply an effect by modifying that pixel array with rgbSplit(pixels). putImageData writed the modified pixels back to the canvas.

The function takePhoto plays the shutter sound and converts the current canvas frame to a data url in order to take a photo of the canvas. It create a link with downlowd="handsome" and it inserts it at the top of .strip so the newest snapshot appears first.

The function redEffect applyes an image effect of red using pixel manipulation, it increases red, reduces green, halves blue for each pixel.

The rgbSplit function offsets each color channel to nearby indices in the array, to create a ghosted color split.

The greenScreen function reads slider values to define min/max thresholds for R G B. Any pixel inside that color range becomes transparent with alpha = 0

# WHAT I LEARNED

I learned to use the getUserMedia API to access the webcam in a secure way and to work with live video and canvas together. I also learned more about manipulating pixel data with getImageData() and putImageData() and understand how RGBA color channels work and how shifting or modifying their values changes the resulting image.
