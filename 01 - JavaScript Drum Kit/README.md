# PROJECT DESCRIPTION

This code creates a basic drum kit, we have some letters on the UI and when we press the corresponding keys the letters light up and create a sound.

Each button is actually a div having an attribute called data-key, and for each data-key we have an audio. 

We have a playSound function which is called on 'keydown' event (when the user presses a key on the keyboard). This function looks for the key that was pressed and for the corresponding audio, and for that key, it adds the class 'playing' (which will make the border of the key light up). We  play the corresponding audio with audio.play() and we use audio.currentTime = 0 so if the user presses multiple times on the same key, the sound plays again and again.

The function removeTransition  is called on 'transitionend' event, so when the user no longer presses a key. When that happens, this function removes the playing class so the key style comes back to normal. This happens after 0.07 seconds after the key was released (we can change by updating  transition: all .07s ease in key class).

# WHAT I LEARNED

If I were to be given this task, I would have totally used setTimeout instead of adding an event listener (transitionend), and I did not know about the connection between this event and the transition of 0.07s from styles.css. That was new to me in this tutorial.