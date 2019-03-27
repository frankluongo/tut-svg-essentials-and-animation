# SVG Essentials & Animations, Vol. 2

## SVG Anatomy Overview
[Course Slides](http://slides.com/sdrasner/adv-svg-1?token=UCdXy3zz#/37)

### Platonic Shapes
#### Viewbox
- The viewbox returns `x, y, width, height`
- The viewbox is the containing element, the content of the SVG are the paths inside it
- Rectanges will have x, y, with, and height
- Circles have `cx, cy,` and `r` because they're measured from the center
- Polygons have `x` and `y` points represented here: `points="xValue, yValue"`
- Lines have `x1, y1, x2, y2` points

### Viewbox & Responsive
- The viewbox will just resize

### PreserveAspectRatio
- Default is `preserveAspectRatio="xMidYMid meet"`
- You can also set it to none to have the illustration squish

### Paths, Groups & Polylines
[SVG Demo](https://codepen.io/netsi1964/full/pJzWoz)
[Path Demo](https://codepen.io/anthonydugois/embed/mewdyZ/?height=600&theme-id=5162&default-tab=result#result-box)
- `<g>` is a group of SVG paths
- The `z` at the end of a path means it's closed
- They always start with `d` for drawing and have an `M` for MoveTo
- You can apply fill and stroke to Groups as well
- `polyline` has points

### Animated Bezier Curves & Template Literals
- You can use Bezier curves and template literals in JS to manipulate paths

### Accessibility
[SVG Accessibility Article](https://developer.paciellogroup.com/blog/2013/12/using-aria-enhance-svg-accessibility/)
[CSS Tricks](https://css-tricks.com/accessible-svgs/)
```html
<svg aria-labelledby="title"
  id="svg"
  role="presentation"
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 765 587">
<title id="title"
  lang="en">
  Icons that illustrate Global Warming Solutions
</title>
...
</svg>
```


## CSS Animation

### Optimizing & Building
- Get it down to as few points as possible
- Smooth out curves and make them use as few points as possible
- Use SVG Filters for shadows

- [SVG Editor](http://slides.com/sdrasner/adv-svg-1?token=UCdXy3zz#/53)


### Constructing an SVG
- Use `Export As` in Illustrator to export the SVG
  - Use `Presentation Attributes` for the styling
  - Use `Show Code` to see the element

### Starting an SVG
- Design everything first, then slowly unveil
- Sketch things out

### Prototyping
- Write in code

### Sprites
- Setting a negative start for an animation will give a more natural look

### Atmospheric & Elemental Motion
- Further away is less contrast and blurry
- Does the air or environment effect movement?
- Reduce precision allows for understanding


## GreenSock

### Tools Overview
http://slides.com/sdrasner/adv-svg-2?token=FxyYIMcu#/3

#### Correct Tools
CSS / SCSS
- Small sequences and simple interactions
- Once you get more than 3... switch to:

GSAP / Greensock
- Great for sequencing and complex movement
- Cross-browser consistency

React Spring / React-Motion
- Great for single movements that you'd like to look realistic


### Performance & GSAP
Using CSS, check out these resources:
- [Debugging CSS](https://css-tricks.com/debugging-css-keyframe-animations/)
- [High Performance Animations](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/)
- [Performant CSS](http://eng.wealthfront.com/2015/06/30/implementing-netflix-redesign/)


Hardware acceleration cheat:
```scss
@mixin accelerate() {
 transform: translateZ(0);
 backface-visibility: hidden;
 perspective: 1000px;
}

.foo {
  @include accelerate();
}
```

Not using CSS, good.
- Check out the gsap cheatsheet


### Exercise
Take an SVG, and animate it with GreenSock. Use a timeline and the position parameter or labels. There are starter pens for reference in the repo: https://github.com/sdras/svg-workshop/
## UI/UX Animation
[Slides](http://slides.com/sdrasner/adv-svg-2?token=FxyYIMcu)

### UI vs Standalone Animation

#### UI/UX Animation
The point of these is to smooth out the interaction of the interface

- [Sample Icons Repo](https://github.com/sdras/vue-sample-svg-icons)
  - `fill="currentColor"` will inherit color from text around it
- [UX Choreography](https://codepen.io/sdras/pen/Kwjyzo)
  - Using animation to enhance the UX of the website
- Animation is great for transtioning from one state to another
  - [Adding a List Item](https://cssanimation.rocks/list-items/)
- [Great Navigation Example](https://www.concrete-matter.com/)

#### Standalone Animation
The purpose of this is to wow the user and keep them entertained
- [Contact Form](http://codepen.io/sdras/full/LEorev)



### Social Engineering With Animation
- [Designing Interface Animation](https://rosenfeldmedia.com/books/designing-interface-animation/)

#### Anticipatory Cues
- [Anticipatory Study](https://www.viget.com/articles/experiments-in-loading-how-long-will-you-wait/)
- Using animation can ease wait times
- Use different types of animations for different events on the site

#### SVG Illustration
- SVG's are useful for adding a bit of pizazz to a block of text


### Context Switching
- [Example](https://codepen.io/sdras/full/qOdwdB)
- Animation helps with context switching, [article here.](https://css-tricks.com/the-importance-of-context-shifting-in-ux-patterns/)
- [It can help reveal importance as well](https://codepen.io/sdras/full/qOdWEP)

### Improving an Existing UI Demo
- [Trip Planner Demo](https://codepen.io/sdras/full/amJLxN)
- Incorporate Animation into the experience of using the site

### Interaction, JS Detection & Scaling
- Animation is great for animating interactions and states
- JavaScript can listen to CSS Events
- You can use preset animations and scale up

### Interaction & GSAP Timeline Functions
```javascript
tl.pause() // Pause timeline
tl.resume() // Continue playback
tl.restart() // Restart the timeline
tl.play(X) // Play from Xs
tl.play(-X) // Play Xs from end
tl.seek(X) // Go to Xs or 'label'
tl.reverse() // Reverse playback anytime
tl.timeScale(x) // Speed up/slow down timeline
tl.progress(0.5) // Skip to halfway
```

### Interaction Demo


