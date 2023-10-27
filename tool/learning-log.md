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
  Bodies.circle(400, 200, 55),
```

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
