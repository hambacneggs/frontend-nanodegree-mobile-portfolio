## Website Performance Optimization portfolio project

This is a project for the Udacity website optimization course.

### How to use
To view the optimized homepage, go to [https://hambacneggs.github.io/frontend-nanodegree-mobile-portfolio/](https://hambacneggs.github.io/frontend-nanodegree-mobile-portfolio/)

To view the optimized pizzeria page, go to [https://hambacneggs.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html](https://hambacneggs.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html)

### What was optimized

#### index.html
- Added a "print" media type to the print.css stylesheet. This removes the stylesheet from the critial rendering path when not being printed.
- Minified css and js files to reduce download size.
- Moved minified style.css inline to stop it from blocking rendering while the file was being downloaded. _I normally wouldn't do this, since the stylesheet wouldn't be cached, but since this project was about optimizing ONE page, I think it was appropriate._
- Optimized pizzeria.jpg by resizing and optimizing using ImageOptim.
- Moved render blocking scripts to the bottom of the body element.
- Implemented Web Font Loader to remove the Google Font stylesheet from the critical rendering path.

#### pizza.html and main.js
- Rewrote changePizzaSizes function (also removed determineDx function). Instead of looping through and styling each div with JS, the new code changes the class on the parent element #randomPizzas and that changes the size of the child elements via CSS (using new styles in style.css).
- Edited updatePositions to fix the Forced Synchronous Layout. Having a reference to `document.body.scrolltop` in the for loop was causing the issue, so I moved it to outside of the loop.
