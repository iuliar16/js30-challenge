# PROJECT DESCRIPTION

This project uses reduce to calculate the total time of the videos in a list.
We have a ul with each li having the attribute data-time="mins:seconds".

We use ocument.querySelectorAll("[data-time]") to get all the li elements and since this gives us a list of nodes and we need to apply map and reduce over it, we apply Array.from to make it an array.

We map over the array, we take node.dataset.time (because each li has data-time attribute) so now we have mins:secs. We split this with timeCode.split(":"). which will give 'mins secs' and this is a string so we apply parseFloat to create numbers. Then we return the number of seconds (min\*60+secs). Then apply reduce so for each li we add up the seconds.

Now we have the total amount of seconds and we want to transform it into hours, mins and seconds left.

We divide secondsLeft by 3600 (there are 3600 seconds in an hour) to get the hours. Math.floor() rounds down to the nearest whole number.

We apply modulus 3600 to secondsLeft toremove the full hours we calculated from secondsLeft (the remainder after division to 3600).

To get the minutes, we divide secondsLeft by 60.

We apply modulus again to get the secondsLeft.

# WHAT I LEARNED

It reminded me of how we can use Array.from or the spread operator in case we want to transform a list of nodes into an array and how to use the map function multiple times in a row on the same array (in the same instruction).
