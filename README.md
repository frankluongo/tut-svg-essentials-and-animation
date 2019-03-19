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
-

