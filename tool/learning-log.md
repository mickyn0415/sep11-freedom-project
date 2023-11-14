# Tool Learning Log

Tool: Matter.js

Project: **X**

---

10/23/23:
videos : The coding Train : Matter.js physics 

installing : ```java <script src="matter.js" type="text/javascript"></script> ```

tinkering :

i try the demos and it kind of changing my mind of making a 2048 game

now i want to make a sling shot game




10/24/23:
 tutorial:  https://www.codebrainer.com/blog/learn-matterjs-with-examples 

10/25/23
getting started 

```java
// module aliases
var Engine = Matter.Engine,
    Render = Matter.Render,
    Runner = Matter.Runner,
    Bodies = Matter.Bodies,
    Composite = Matter.Composite;

// create an engine
var engine = Engine.create();

// create a renderer
var render = Render.create({
    element: document.body,
    engine: engine
});

// create two boxes and a ground
var boxA = Bodies.rectangle(400, 200, 80, 80);
var boxB = Bodies.rectangle(450, 50, 80, 80);
var ground = Bodies.rectangle(400, 610, 810, 60, { isStatic: true });

// add all of the bodies to the world
Composite.add(engine.world, [boxA, boxB, ground]);

// run the renderer
Render.run(render);

// create runner
var runner = Runner.create();

// run the engine
Runner.run(runner, engine); ```


 10/26/23 :
 tinkering i use matter.js on replit to test out the code which it all the code on the html and javascript

the number in the middle of the code changes the size of the shape    
```java World.add(world, [
  Bodies.circle(200, 400, 100),
  Bodies.circle(400, 200, 55),```

10/27/23:

tinkering

after that tinkering on replit

in isStatic if you type true it will be a actally a shape and if false the shape on top just fell
```java Bodies.rectangle(200, 10, 800, 50, { isStatic: false }),```

if i change the wireframe to true all the colors of the shape are gone 
```java let render = Render.create({
  element: document.body,
  engine: engine,
  options: {
    width: 1000,
    height: 600,
    wireframes: false
  }```
<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->

10/29/23
it tried starting with the html

```java
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>matter.js</title>
 <script src="https://cdnjs.cloudflare.com/ajax/libs/matter-js/0.17.1/matter.min.js"></script>
 <script src="scripts.js"></script>
 <style>
 canvas {
 position: relative;
 width: 500px;
 height: 500px;
 background-color: white;
 }
 </style>
</head>
<body>
 
</body>
</html>```

11/3/23
i learn that i need to add a renderer ,engine and add also to make the user able to move the objects with it mouse
```java
let render = Render.create({
  element: document.body,
  engine: engine,
  options: {
    width: 800,
    height: 600,
    wireframes: false```

11/5/23
from the codes i found on replit i know that it adds the shape to website or game but i still don't know why it gives error when i try to change the shape from 

a circle to a rectangle 

```java
World.add(world, [
  Bodies.circle(200, 500, 50),
  Bodies.circle(200, 400, 25),
  Bodies.rectangle(200, 300, 50,50)
  Bodies.rectangle(300, 200, 50, 50)
])```


11/7/23
i went on the website that i found
https://www.codebrainer.com/blog/learn-matterjs-with-examples
it gives me example from

Create falling objects
flying balloon
Create balloon with the rope
 make a slingshot game

11/10/23

i try creating the example from codebrainer but it not really working i tried on replit i think there was to much code so it not working  this was the code that i found

```java function StartSlingshot() {
 clearWorld("Slingshot")

 // add bodies
 let ground = Bodies.rectangle(395, 600, 815, 50, { isStatic: true });
 let rockOptions = { density: 0.004 };
 let rock = Bodies.polygon(170, 450, 8, 20, rockOptions);
 let anchor = { x: 170, y: 450 };
 let elastic = Constraint.create({
 pointA: anchor,
 bodyB: rock,
 stiffness: 0.05,
 render: { strokeStyle: 'gray', lineWidth: 2 }
 });
 let ground2 = Bodies.rectangle(610, 250, 200, 20, { isStatic: true });

 let pyramid = Composites.pyramid(550, 0, 5, 10, 0, 0, function (x, y) {
 return Bodies.rectangle(x, y, 25, 40);
 });```

11/13/23
