# PROJECT DESCRIPTION

This project connects to the device's GPS using the broswer's Geolocation API and uses live location updates to display your current speed and rotate the arrow according to the direction of movement.

We use document.querySelector to get the SVG graphic arrow and the text element showing the speed value.

Then we use the Geolocation API to continuously track the device'position. Inside the success callback, data contanins a coords object with latitude, longitude, speed, heading (direction of travel).
We use:
arrow.style.transform = `rotate(${data.coords.heading}deg)`;
this rotates the arrow based on the heading.

# WHAT I LEARNED

I did not use the geolocation api before and I learned now more about it and also I learned more about the behaviour of this api that depends on the hardware because the browser can only return speed and heading if the device actually has GPS or motion sensors - like a phone.
