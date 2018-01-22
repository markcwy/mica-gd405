# Drawing Basics

To draw with code in Processing, you will have to memorize a few basic drawing functions. The best way to find out about these functions are to visit the official website's [reference section](https://processing.org/reference/). It lists all the functions(building blocks) and comes with examples.

## Coordinates
In Processing, there is no user interface like brush or pen tool. You have to define the position of the things you want to draw by setting x and y coordinates. the origin `(0, 0)` is located at the top-left corner.


## Point
You rarely draw point by point, but it can be useful when you want to paint each pixel.
```java
point(x, y);
```

## Line
Define the beginning point and the ending point.
```java
line(beginX, beginY, endX, endY);
```
*Exercise: Draw X at each corner of the canvas.*

## Rectangle
Define top-left corner, its width and height.
```java
rect(topleftX, topleftY, width, height);
```
If you want to draw from the center of rectangle, first change the mode.
```java
rectMode(CENTER);
rect(centerX, centerY, width, height);
```
*Exercise: Draw 2 rectangles with the same parameter values. Use rectMode(CENTER) for the second one.*

## Ellipse
By default, an ellipse is drawn from the center.
```java
ellipse(centerX, centerY, width, height);
```
To draw from the top-left corner, change the mode before you draw.
```java
ellipseMode(CORNER);
ellipse(cornerX, cornerY, width, height);
```
*Exercise: Draw 5 concentric circles from the center of the canvas.*

## Triangle
A triangle requires 3 pairs of point.
```java
triangle(x1, y1, x2, y2, x3, y3);
```
Exercise: Draw 3 triangles that share a corner with another.

## Quad
A quad requires 4 pairs of points. Be careful with the order of the points.
```java
quad(x1, y1, x2, y2, x3, y3, x4, y4);
```
*Exercise: Draw 2 parallelogram that are partly overlapping with each other.*

## Vertex
For complex shapes, use `vertex()` to place as many points as you want. All the vertices between `beginShape()` and `endShape()` will be connected with straight lines.
```java
beginShape();
vertex(10, 10);
vertex(50, 20);
vertex(70, 80);
vertex(40, 40);
vertex(10, 40);
endShape();
```
If you want to connect the last vertex and the first vertex, add an optional parameter to `endShape()` as below:
```java
endShape(CLOSE);
```
*Exercise: Draw the outline of an uppercase F using vertices.*

### Stroke weight
```java
strokeWeight(5); // set stroke width to 5 px.
```
*Exercise: Go back to one of the earlier sketches and play with color, transparency and strokeweight.*

## Color
You can set colors of the stroke and the fill. 
```java
stroke(0); // set stroke to black
fill(255); // set fill to white
noStroke(); // do not display stroke.
noFill(); // do not display fill.
```

Each color channel can take 256 different values from `0` to `255`. To use color, use Red, Green and Blue channels.
```java
stroke(255, 0, 0); // set stroke to full red.
fill(0, 255, 0); // set fill to full green.
```

Remember to set the color *before* you draw a shape.
```java
stroke(200);
line(0, 0, 100, 100);
stroke(100); // this function has no effect.
```

### Transparency
Adding an optional parameter will enagle the transparency to both greyscale and RGB color.
```java
fill(200, 100); // set fill to light grey with transparency.
stroke(255, 0, 0, 80); // set stroke to red with transparency.
```


