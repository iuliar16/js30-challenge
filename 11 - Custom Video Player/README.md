# PROJECT DESCRIPTION

This project implements a video player with functionalities such as play, pause, skip buttons, volume and playback speed.

We use document.querySelector to target the classes we need, such as player, video, progressBar etc.

the function togglePLay is called when the video is clicked and it is used to play/pause the video. If the video is paused, a click will trigger the play action and vice versa.

The function updateButton is called when clicking on the play/pause button (toggle) and it changes its icon to match the state of the video.

The function skip is called on click and mousemove over the 2 skip buttons (back 10s and forward 25s). These 2 buttons both have the attribute data-skip (with values - 10 and 25), therefore we can access these values in skip function using this.dataset.skip. We use parseFloat to convert this values into numbers and we update video.currentTime by adding the skip value.

The function handleRangeUpdate is called on click and mousemove over the 2 ranges - for volume and playbackRate. These 2 ranges are inputs with the atttribute name (volume and playbackRate) and default value = 1. In this function we modify video[this.name] to be this.value meaning video.volume will receive the new value for volume selected by user and the same for playbackRate.

The function handleProgress makes sure the progressBar moves along with the video. the flexBasis property of the progressBar shows in percents how wide the progress bar should be, so we calculate the percentage of the current moment in video with (video.currentTime / video.duration) \* 100; and update the flexBasis of the progress bar with that value.

The function scrub makes the video go to a specific point when the user clicks somewhere on the progressBar. We use mousedown flag like this: when mousedown is true and the mouse is moving on the progressBar, we call scrub function. When the mouse is released, mousedown becomes false.

# WHAT I LEARNED

I did not work with the HTML element video before so I did not really have much experience with methods like play or pause and all the other properties like currentTime, paused, duration.
