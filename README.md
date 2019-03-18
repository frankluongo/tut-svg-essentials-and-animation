# SVG Essentials & Animations, Vol. 2

## SVG Anatomy Overview

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
