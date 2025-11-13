# PROJECT DESCRIPTION

This project adds an animation effect so that images slide in as you scroll down the page.

The function debounce limits how often another function can run. func is the function to delay (checkSlide in our case), wait is by defalt 20ms (how long to wait between runs), immediate telss wheter to call it immediately or after the wait time.

We use document.querySelectorAll to find all elements with class slide-in (the images). The function checkSlide iterates over the images and calculates the vertical position where the image is half shown
window.scrollY = how far you've scrolled down
window.innerHeight is the viewport height.

const slideInAt = (window.scrollY + window.innerHeight) - sliderImage.height / 2;

We substract the sliderImage.height/2 to obtain a threshold halway trough the image.

isHalfShown flag is true if the scroll position has reached halfway trough the image

isNotScrolledpast flag is true if you have not scrolled past the image yet.

if the flags are active (so the image is halfway visible but not past), we add the class active, which triggers the CSS slide animation, otherwise we remove the class active.

# WHAT I LEARNED

I did not realize that scrolling can fire so many events per second and that in this case we could use a function like debounce to make sure a function does not run excessively. Other than that, the formulas he used to calculate when to trigger the slider in and when to know if we passed an image with scrolling were interesting.
