# CSS Parallax

An implementation of Parallax using CSS.

Based off [Daily Fire's Article on Medium](https://medium.com/@dailyfire/pure-css-parallax-simple-tricks-da102d0ffdb9) about CSS Parallax.

## Why this package?

Parallax is a popular UX feature that is typically implemented with JavaScript, using costly window.onscroll event listeners and callbacks functions running hundreds of per scroll.

Implementing Parallax using the CSS 3D Transform properties makes it possible to implement parallax without consuming as many computational resources as a JavaScript implementation.

## API

<!-- Image of layers -->

## Compatability

CSS 3D Transforms and Perspective are supported by most modern browsers.

**As of June 2020, CSS Parallax does not work in Safari for iOS 13**. This is described in Chris Coyier's article on CSS Tricks, [iOS 13 Broke the Classic Pure CSS Parallax Technique](https://css-tricks.com/ios-13-broke-the-classic-pure-css-parallax-technique/)
and a [StackOverflow Thread](https://stackoverflow.com/questions/58409202/css-only-parallax-scrolling-stoped-working-with-ios-pados13)
Basically, 3D Transforms no longer cause elements to scroll at different rates nor appear to have any distance from the user on Safari iOS.
The only way to counteract this is to test for userAgents that are iPads, iPhones, iPods, etc, since feature testing for `translate: translateZ()` still returns true both in CSS and JS, despite it not working at all. Then, remove the scaling from elements where it is applied.
Most methods of implementing parallax are prevented from functioning on mobile, since they can be computationally expensive and mobile are optimized to reduce computations. This may be a good instance to use *graceful degradation*.

## Resources

-   [Pure CSS Parallax by Daily Fire](https://medium.com/@dailyfire/pure-css-parallax-simple-tricks-da102d0ffdb9)
-   [Performant Parallaxing by Google](https://developers.google.com/web/updates/2016/12/performant-parallaxing)
-   [Pure CSS Parallax Websites by Keith Clark](https://keithclark.co.uk/articles/pure-css-parallax-websites/)

## To Do
- Test for prefers-reduced-motion support
- Implement UA tests for iOS and remove transformations.