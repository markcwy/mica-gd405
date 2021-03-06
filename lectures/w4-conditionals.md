# Conditionals
Conditionals are everywhere in softwares. Anytime, you want to diverge and create different results based on different situations, you will use the conditionals. Here, we will look at a few simple examples.

## Boolean

A boolean expression can be evaluated to either true or false. It will always be either true or false.

```js
console.log(3 < 4);
console.log(3 + 4 == 7);
console.log(4 + 4 < 7);
```

## If statement
We can use the boolean expression to run the code only when a condition is met (true):

```js
function draw() {
  background(0, 255, 0);
  if (mouseX < width/2) {
    background(255, 0, 0);
  }
}
```
## else
We can improve the previous example by adding `else` - what happens when the condition is not met (false):

```js
function draw() {
  if (mouseX < width/2) {
    background(255, 0, 0);
  } else {
    background(0, 255, 0);
  }
}
```
## else if, AND(&&), OR(||)
We can check multiple conditions by using `if`, `else if`, `else` and `&&`(and) nd `||`(or):

```js
function draw() {
	background(200);
	
  if (mouseX < width/3) {
    rect(0, 0, width/3, height);
  } else if (mouseX >= width/3 && mouseX < width/3*2){
    rect(width/3, 0, width/3, height);
  } else {
		rect(width/3*2, 0, width/3, height);
	}
}
```
## Events
### Mouse press
We can set the condition to check if the mouse is pressed, using the system variable `mouseIsPressed`. This is a boolean variable, meaning it will always be either true or false.

```js
function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
}

function draw() {
  background(200);
	
  if (mouseIsPressed == true) {
    textSize(128);
  } else {
    textSize(24);
  }
  text("HEY", width/2, height/2)
}
```

We can also check which mouse button is pressed by using nested if statements.

```js
function setup() {
	createCanvas(400, 400);
	textAlign(CENTER, CENTER);
}

function draw() {
  background(200);
	
  if (mouseIsPressed == true) {
    textSize(128);
		if (mouseButton == LEFT) {
			fill(255, 0, 0);
		} else {
			fill(0, 255, 0);
		}
  } else {
		textSize(24);
		fill(0);
	}
	text("HEY", width/2, height/2)
}
```

### Key press
Similarly, we can check if a key is pressed.

```js
function setup() {
	createCanvas(400, 400);
	background(200);
	textAlign(CENTER, CENTER);
}

function draw() {
  
	textSize(160);
	if (keyIsPressed) {
		fill(random(255));
		text(key, random(width), random(height));
	}
}
```

Notice that as long as you hold down a key, the if statement gets checked every frame. It is because the statement is inside `draw()`, which keeps running. If you only want to check the keypress once, there is another way.

### Key press function

```js
function draw() {
  
}

function keyTyped() {
	textSize(160);
	if (keyIsPressed) {
		fill(random(255));
		text(key, random(width), random(height));
	}
}
```

Here, I am suing `keyTyped()`, not `keyPressed()` so that I can differentiate between uppercase and lowercase characters.

### Saving image with keypress

```js
function keyTyped() {
	if (key == '=') {
		save(month() + "-" + day() + "-" + hour() + "-" + minute() + "-" + second() + ".png");
	}
}
```


-----
*Exercise: Look at [p5.js Reference](http://p5js.org/reference/). There are a few different functions related to key presses. See if you can connect different keys to draw different shapes. For example, can you connect arrow keys to move your shape up, down, left and right?*

*Exercise: Can you create a simple painting program, where each key is mapped to a different color?*

*Exercise: Think about interesting conditions you can apply to your type design. This will be a good first step in thinking about design that responds to conditions and environments.*
