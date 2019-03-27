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
[Huggly Laser Panda Factory](https://codepen.io/sdras/full/waXKPw)
- 13KB Gzipped
- Cross browser works lovely
- [Codepen](https://codepen.io/sdras/pen/waXKPw)

### Draggable
- [Mr. PotatoHead Example](https://codepen.io/sdras/pen/gbERKQ)
- [Pastel Dots](https://codepen.io/sdras/pen/Qbdmjy)
- Rich Callback Systems
  - onPress
  - onDragStart
  - onDrag
  - onDragEnd
  - onRelease
  - onLockAxis
  - onClick
- "this" refers to the Draggable instance itself, so you can easily access its "target" or bounds.
- [Draggable with Drop Logic](https://codepen.io/GreenSock/pen/GFBvn)
- [Snap Points](https://codepen.io/sdras/pen/d37e832bb3655bbc50bb14ea868104e8)
- [Draggable Timeline Control](https://codepen.io/sdras/pen/NqYGZv)
- [Interpolation With Style Binding](https://codepen.io/sdras/pen/jwwpap)
- [Interactive Wall-E](https://codepen.io/sdras/pen/YZBGNp)

### Interactive Example
[Example Project](https://codepen.io/frankluongo92/pen/rRgyYE)


## GSAP Extras
[Section Slides](http://slides.com/sdrasner/adv-svg-3?token=IiYk_UQj)

### DrawSVG
- Greensock offers this
  - [DrawSVG Example](https://codepen.io/sdras/pen/5018570864785bc281d2aef4732880f4)
  - [GreenSock Options](https://codepen.io/GreenSock/pen/bNdLyR)
- Doing it in CSS
  - [CSS Example](https://codepen.io/sdras/pen/8c38ae4121eae5b6dc035e19c48b35b4)
- [Shel Silverstein's Everything On It](https://codepen.io/sdras/pen/qEdova)
- [Happy New Year's](https://codepen.io/team/WAW/pen/xRoxZY)
- [Weather Notifier](https://github.com/sdras/vue-weather-notifier)

### Motion Along a Path
[Steampunk Lighting](https://codepen.io/sdras/pen/MYQxXe)
```javascript
TweenMax.to($firefly1, 6, {
bezier: {
  type:"soft",
  values:[{x:10, y:30}, {x:-30, y:20}, {x:-40, y:10},
          {x:30, y:20}, {x:10, y:30}],
  autoRotate:true
},
ease:Linear.easeNone, repeat:-1}, "start+=3");
```

### Curviness & Rotation
[Curviness Example](https://codepen.io/sdras/pen/PqEPqz)
```javascript
function displayVals() {
    //get the value from the dropdown
    var singleValues = $("#single").val();
    //the timeline for the changing animation
    tl.to($('.s2'), 1.75, {
      rotation: 360,
      bezier: {
        type: 'thru',
        values: bezier,
        curviness: singleValues
      },
      ease: Power1.easeInOut
    });
  }
  displayVals();
```

[Rotation Example](https://codepen.io/sdras/pen/aOZOwj)
```javascript
 autoRotate: ["x","y","rotation",0,false]
```
- Position property 1 (typically "x")
- Position property 2 (typically "y")
- Rotational property (typically "rotation", but can also be “rotationX” or “rotationY”)
- Number of degrees (or radians/Math.PI) to add to the new rotation at the onset (this is optional)
- Boolean value indicating whether or not the rotational property should be defined in radians rather than degrees (default is false which results in degrees)


### Animating Text
- Support Back to IE8
- Breaks into characters, words or lines
- Honors natural line breaks
- Option to create auto-incrementing classes, i.e. `.char1, .char2, .char3`

---

This doesn't require Plugins!
```javascript
 var foo = new SplitText("#bar", {type:"words",
   //optional
   wordsClass:"word"
 });
```

---

[Bad Gradient Example](https://codepen.io/sdras/pen/VLBdOp)
[Good Gradient Example](https://codepen.io/sdras/pen/akAWPR)

```javascript
TweenLite.set(cont, {
  transformPerspective: 600,
  perspective: 300,
  transformStyle: "preserve-3d",
  autoAlpha: 1
});
```

```javascript
var tl = new TimelineLite,
  doSplitText = new SplitText(cont, {
    type: "words, chars"
  }),
  cWords = doSplitText.words,
  cChars = doSplitText.chars,
  numWords = doSplitText.words.length;
```

Helper Function for getting random number:
```
function totesRando(max, min) {
  return Math.floor(Math.random() * (1 + max - min) + min);
}
```

```javascript
tl.add("start");
for (var i = 0; i < numWords; i++) {
  tl.from(cWords[i], 6, {
    z: totesRando(100, 500),
    opacity: 0,
    rotation: totesRando(360, -100),
    ease: Expo.easeOut
  }, "start+=" + Math.random() * 0.3);
}
```

[Illustrated Words Example](https://codepen.io/sdras/full/RNWaMX)


### Relative Color Values


## Advanced SVGs
[Section Slides](http://slides.com/sdrasner/adv-svg-3?token=IiYk_UQj)


### Clipping & Masking


