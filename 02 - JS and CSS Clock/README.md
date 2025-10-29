# PROJECT DESCRIPTION

This project creates an analogic clock and the challenge is to get the 3 hands (minutes, seconds, hours) move correctly.
We have a function - setDate which is called once per second using setInterval. this function creates an object containg the current hour. We have 3 divs (one for each hand) and we use document.querySelector to get them, and for each of them we calculate the number of degrees. For example, for seconds we need (seconds/60)*360 + 90 where (seconds/60) is a full complete circle, multiply by 360 to transform into degrees and add 90 because every hand begins from the position of 90 degrees so we need to compensate.

The movement of the hands is done using the following styles:
transform: rotate(90deg) - initially the hands are aligned horizontally (at 12 o'clock),
transform-origin: 100% - the hands move around the right end, 
transition-timing-function: cubic-bezier(0.1,2.7,0.58,1); transition: all 0.05s; - these help the move to seem more realistic, so they do not move suddenly.

# WHAT I LEARNED

I learned how to use the css properties - transform-origin and transition-timing-function. It was interesting to me how we needed to add the extra 90 when calculating the degrees for each hand because in CSS a rotation of 0 degrees means horizontally to the right but in real clocks to start from 12 o'clock means 90 degrees clockwise.