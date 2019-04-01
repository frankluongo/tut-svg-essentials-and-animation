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
**Codepen Examples:**
- [Relative HSL Colors Example](https://codepen.io/sdras/pen/c647706356bf2e1b940d0d5c6fdbe1b4)
- [Another Hue Changing Example](https://codepen.io/sdras/pen/YyXewa)
- [Time Comparison Example](https://codepen.io/sdras/pen/RZGqxR)

**Code Example:**
```javascript
//button hue
function hued() {
  var ch1 = "hsl(+=110%, +=0%, +=0%)",
  tl = new TimelineMax({
    paused: true
  });

  tl.add("hu");
  tl.to(mult, 1.25, {
      fill: ch1
    }, "hu");
  ...
  tl.to(body, 1.25, {
      backgroundColor: ch1
    }, "hu");

  return tl;
}

var hue = hued();
```


### Creating a Story Exercise
**Prompt:** Combine 2 of the effects we just learned to tell a simple story with SVG animation:
- DrawSVG
- Motion Along a Path
- SplitText
- HSL Tween


### MorphSVG
**Codepen Examples:**
- [Interchangeable Hipster](https://codepen.io/sdras/pen/BodKjP)
- [CSS Tricks](https://codepen.io/sdras/pen/85b34f90de906d707b10e235de5959d5)
- [Shape Index](https://codepen.io/sdras/pen/f4e735983d9972abd35d74062ea0e543)
- [Live Coding Example](https://codepen.io/sdras/pen/eKLeao)
  - [Live Coding Video](https://vimeo.com/292473138)
- [Candle](https://codepen.io/sdras/pen/gaxGBB)
- [SVG Menu](https://codepen.io/lbebber/pen/LELBEo)

**How To Code Samples:**
Point From One ID To Another
```javascript
TweenMax.to("#start", 1, {morphSVG:{shape:"#end"},
   ease:Linear.easeNone});
```
This will convert one element to another by changing the path points

---

Convert To Path Data
```javascript
MorphSVGPlugin.convertToPath("circle, rect,
  ellipse, line, polygon, polyline");
```
This is converting a rectangle or some other shape to paths so you can morph them

---

```javascript
MorphSVGPlugin.convertToPath("#foo");
```

Use ShapeIndex
```javascript
TweenMax.to("#start", 1, {morphSVG:{shape:"#end",
   shapeIndex:"1"}});
```
- This is for finely tuning morphs
- Default is shapeIndex: "auto"
- Load the extra plugin, and a GUI will come up
- Usually auto will be correct, but you can pick
- Use findShapeIndex(#start, #end)

---

Filters
```html
<defs>
    <filter id="Blur">
      <feGaussianBlur in="SourceGraphic" stdDeviation="9" result="blur"></feGaussianBlur>
      <feColorMatrix in="blur" mode="matrix"
       values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 19 -7" result="goo"></feColorMatrix>
    </filter>
  </defs>
```

---

Naming
```html
    <path id="f-stable" class="st7" d="M133.5 265.5s-29.5 12-28-60.5 23.5-91.5 23.5-91.5-10
       23-5.5 52.5 25.5 60.5 10 99.5z" />
    <path id="f1" class="st9" d="M132.5 266.5s-29.5 12-28-60.5-1.2-108.3-1.2-108.3 17.8 39.8
       22.3 69.3c4.6 29.5 22.4 60.5 6.9 99.5z" />
    <path id="f2" class="st9" d="M127.3 266.3s-24 11.8-22.5-60.7 24.2-93.3 24.2-93.3-7.8
       25.2-3.3 54.7c4.5 29.5 33.3 64.3 1.6 99.3z" />
```

---

Flame
```javascript
MorphSVGPlugin.convertToPath("ellipse");

function flame() {
  var tl = new TimelineMax();

  tl.add("begin");
  tl.fromTo(blurNode, 2.5, {
    attr: {
      stdDeviation: 9
    }
  }, {
    attr: {
      stdDeviation: 3
    }
  }, "begin");
  var num = 9;
  for (var i = 1; i <= num; i++) {
    tl.to(fStable, 1, {
      morphSVG: {
        shape: "#f" + i
      },
      opacity: ((Math.random() * 0.7) + 0.7),
      ease: Linear.easeNone
    }, "begin+=" + i);
  }
```

### Bonus Demos
**Codepen Examples**
- [Catmull-Rom Spline](https://codepen.io/osublake/pen/BowJed)
  - [Related Article](http://schepers.cc/getting-to-the-point)
- [Catmull-Rom Spline Candle](https://codepen.io/sdras/full/EVRJqg)
- [Exploding World](https://s.codepen.io/sdras/debug/VpYeNj)
- [Sound Interaction Example](https://codepen.io/sdras/pen/zvXbGJ)
- [Introvert Pen](https://codepen.io/sdras/pen/dPqRmP)

**How To Code Samples:**

Catmull-Rom Spline
```javascript
function solve(data) {

  var size = data.length;
  var last = size - 4;

  var path = "M" + [data[0], data[1]];

  for (var i = 0; i < size - 2; i +=2) {

    var x0 = i ? data[i - 2] : data[0];
    var y0 = i ? data[i - 1] : data[1];

    var x1 = data[i + 0];
    var y1 = data[i + 1];

    var x2 = data[i + 2];
    var y2 = data[i + 3];

    var x3 = i !== last ? data[i + 4] : x2;
    var y3 = i !== last ? data[i + 5] : y2;

    var cp1x = (-x0 + 6 * x1 + x2) / 6;
    var cp1y = (-y0 + 6 * y1 + y2) / 6;

    var cp2x = (x1 + 6 * x2 - x3) / 6;
    var cp2y = (y1 + 6 * y2 - y3) / 6;

    path += "C" + [cp1x, cp1y, cp2x, cp2y, x2, y2];
  }

  return path;
}
```

---

Polygon Catmull-Rom Spline
```javascript
var poly = document.querySelector("polyline");
var path = document.querySelector("path");

var points = [
  100,350,
  200,100,
  300,350,
  400,150,
  500,350,
  600,200,
  700,350
];

poly.setAttribute("points", points);
path.setAttribute("d", solve(points));
```

---

Exploding World
```javascript
tl.call(addAttr);
  tl.fromTo(feTurb, 1, {
    attr : {
      baseFrequency: '0 0'
    }
  }, {
    attr : {
      baseFrequency: '0.8 1.2'
    },
    ease: Sine.easeOut
  });
  tl.to(feTurb, 1, {
    attr : {
      baseFrequency: '0 0'
    },
    ease: Sine.easeIn
  });
  tl.call(removeAttr);
```

Helpers
```javascript
// filter attribute helpers
function addAttr() {
  feTurb.setAttribute('baseFrequency', '0 0');
}

function removeAttr() {
  var applyFilter = document.getElementById('applyFilter');
  applyFilter.removeAttribute('filter');
}
```

---

Sound Example
```javascript
//balloon
function balloonGrow(){
  var balloon = $("#balloon")[0];
  var radius = balloon.getAttribute("r");
  var cySet = balloon.getAttribute("cy");
  balloon.setAttribute('r', parseInt(radius) + 10);
  balloon.setAttribute('cy', parseInt(cySet) - 10);
  if (parseInt(radius) > 125) {
    ion.sound.play("balloon-pop3");
    var balloonTl = new TimelineMax();
    balloonTl.add("pop");
    balloonTl.to("#balloon", 0.05, {
      scale: 5,
      opacity: 0,
      transformOrigin: "50% 50%",
      ease: Circ.easeOut
    }, "pop");
    ...
    setTimeout(function(){
      balloon.setAttribute("r", "45");
      balloon.setAttribute("cy", "233.5");
    }, 200);
  }
}
```


## Advanced SVGs
[Section Slides](http://slides.com/sdrasner/adv-svg-3?token=IiYk_UQj)


### Clipping & Masking
**Notes**
- SVG Support for clipping is very high

**Codepen Samples:**
- [Clipping Vs Masking](https://codepen.io/sdras/pen/d2a9315e310901a3d43ba3bdf8413c65)
- [Clipping Vs Masking Article](https://css-tricks.com/masking-vs-clipping-use/)
- [Animation in a Clipped Path](https://codepen.io/sdras/pen/wKMVYr)
- [CSS Clip Path](https://codepen.io/sdras/pen/myExro)
- [SVG Animation](https://codepen.io/sdras/pen/xOjAmV)
- [GIF Masking](https://codepen.io/sdras/pen/BReNEN)
- [Yoksel](https://codepen.io/yoksel/)


**Code Examples:**
How to Structure Clip Paths
```html
<defs>
  <clipPath id="clippy">
    <ellipse cx="276" cy="147" rx="272" ry="147"/>
  </clipPath>
</defs>
```
Styling For It
```css
.img {
  clip-path: url(#clippy);
}
```


### ViewBox
**Codepen Samples**
- [Dynamic Viewbox](https://codepen.io/sdras/pen/512230ed732f9b963ad3e50c8d4dcbb8)
- [Animated ViewBox Data Visualization](https://codepen.io/sdras/pen/dXoLEJ)
- [Flow Chart Demo](https://codepen.io/sdras/full/VjvGJM/)
- [Bustle Flowcharts](https://www.bustle.com/flowcharts)


### SVGOrigin
**Codepen Samples**
- [Cow and No HitTest](https://codepen.io/sdras/pen/863bd219acb1d6a016930c239af9050b)
- [Cow Over The Moon](https://codepen.io/sdras/pen/doZReX)
- [Hit Test in SVG](https://codepen.io/sdras/pen/MwxRBL)

