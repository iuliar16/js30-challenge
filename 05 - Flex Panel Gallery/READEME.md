# PROJECT DESCRIPTION

This project uses css properties to display 5 pictures with some 
moving text. When we click on a picture, the rest of the pictures become smaller, leaving space for the clicked one and we also display some more words on that picture. So each picture has 3 divs (one for each word). Only the middle one is displayed at all times, and for the rest of them, we use first-child and last-child properties to hide/display them, for the first child we have 
 transform: translateY(-100%); - this will move up (out of sight) the word
 and for the last word 
 transform: translateY(-100%); which will move it down

 We reverse this movement by adding the class open-active with   transform: translateY(0); The class open-active is added on transitionend event. We also use the class open on click to size up the font-size for these words and use flex:5 which will make the clicked panel take 5 times more than the other panels on the screen.

# WHAT I LEARNED
It helped me practice a little with transform: translateY property because I knew what it does but I did not really work with it so much and also I always used flex:1 property so things take all space from view but I was not sure what a property like flex:5 would do.
