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
