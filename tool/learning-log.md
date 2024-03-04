# Tool Learning Log

Tool: Matter.js

Project: **X**

---

10/23/23:
videos : The coding Train : Matter.js physics 

installing : ```java 
<script src="matter.js" type="text/javascript"></script> 
```

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
Runner.run(runner, engine);
```


 10/26/23 :
 tinkering i use matter.js on replit to test out the code which it all the code on the html and javascript

the number in the middle of the code changes the size of the shape    
```java
World.add(world, [
  Bodies.circle(200, 400, 100),
  Bodies.circle(400, 200, 55),
```

10/27/23:

tinkering

after that tinkering on replit

in isStatic if you type true it will be a actally a shape and if false the shape on top just fell
```java Bodies.rectangle(200, 10, 800, 50, { isStatic: false }),```

if i change the wireframe to true all the colors of the shape are gone 
```java
let render = Render.create({
  element: document.body,
  engine: engine,
  options: {
    width: 1000,
    height: 600,
    wireframes: false
  }
```


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
</html>
```

11/3/23
i learn that i need to add a renderer ,engine and add also to make the user able to move the objects with it mouse
```java
let render = Render.create({
  element: document.body,
  engine: engine,
  options: {
    width: 800,
    height: 600,
    wireframes: false
```

11/5/23
from the codes i found on replit i know that it adds the shape to website or game but i still don't know why it gives error when i try to change the shape from 

a circle to a rectangle 

```java
World.add(world, [
  Bodies.circle(200, 500, 50),
  Bodies.circle(200, 400, 25),
  Bodies.rectangle(200, 300, 50,50)
  Bodies.rectangle(300, 200, 50, 50)
])
```


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

```java
function StartSlingshot() {
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
 });
```

11/20/23
`Matter.Engine` 

simluation of the world

`Matter.Render`

basic HTML canvas-based renderer

`Matter.Runner` 

creates a loop 

`Matter.Bodies`

creates the shapes you want 

`Matter.Composite` 

a container for compound objects 

`Matter.Composites` 

mostly use for layout

`Matter.Constraint` 

for creating and manipulating constraints

`let engine`

`let render`

`let runner`

variables dedicated to the objects for the work with matter.js. ( dont' know how to explain this so just copy the defintion )

first we had to create a engine

` engine = Engine.create();`

second we had to create a renderer 

` render = Render.create ({ stuff inside don't know yet });

third we have to run the renderer 

` Render.run(render);`

fourth we have to create a runner

` runner = Runner.create();`

and 5th we have to run the engine 

` Runner.run(runner,engine);

11/21/23

when creating a shape 

```java
Bodies.rectangle (400,399,332,232,)
Bodies.circle
```
still don't know what does the numbers means i think it the length , width and height 

and those 2 shape are the ones that i mostly seen

i think when adding colors you use render 

in the code it saids 

```java
Bodies.rectangle (400,399,332,232,)
Bodies.rectangle (400,399,332,232,{
render: { fillstroke : 'red'}
```

11/22/23

 to create 

```java
const Engine = Matter.Engine,
render = Matter.render,
World = Matter.World,
Bodies = Matter.Bodies 
````

then create a engine , renderer then add and start the engine

when creating a shape and add ut to the world 

`const box = Bodies.rectangle(100,100,40,40);`

then we add it to the world 

`World,add(engine.world,[box]);`

11/23/23

The order of creating matter.js

1 create engine

2 create renderer

3 create shapes or bodies 

4 add bodies to the world

5 run the engine

6 run the renderer

when creating a loop for matter.js
```java
function matterLoop(){
Matter.Engine.update(engine);
Matter.Render.world(render);
requestAnimationFrame(matterLoop);
}
```
the call the function

`gameLoop();`

11/25/23

with all the steps in learn 2 days ago i createed my first shape 

next step is learn about how to use mouses to control the moving shape in the game

11/26/23

on the official website : https://brm.io/matter-js/docs/classes/Mouse.html

it shows the classes

`Matter.Mouse.create(element)`  i think in the parethesis the elemnet means the shape that is control for the movement of the mouse 

another method 

`Matter.Mouse.clearSourceEvents(mouse) `

the first method looks better and more understand able to me 

11/30/23 
i found this code on google

```java
// add mouse control
 let mouse = Mouse.create(render.canvas),  // i think this one  is used to connect it to something which make the mouse able to be used
 mouseConstraint = MouseConstraint.create(engine, {
 mouse: mouse,
 constraint: {
 stiffness: 0.2,     // i think this is how fast the mouse is going to work
 render: {
 visible: false
 }
 }
 });
```

12/2/23

what i tried to make 

i want to try making multiple block stack on it 

on javascript  

create engine

create renderer

create the blocks properties ( i think this is how it is make ) i used some of the code i found online

```java
var boxWid = 100;
var boxHei = 100;
var blockAmount = 7;
var x = 100;
var y = 50; 
```
then make the blocks


12/3/23
 start from what i left off yesterday
```java
 for (var i = 0 ; i < blockAmount; i++) {
var x1 = x;
var y2 = y + (boxHei + 10) * i;

var block = Matter.Bodies . rectangle (x,y, boxWid ,boxHei, {
density : 0.50,
friction :0.5;
restitution : 0.6 });
```

then add it to the world with matter.world add

and start the engine and renderer
 
12/7/23

i try retry tinkering with the starter code in the offical matter.js website 

i found out that the install code from the offical website didn't work 

`<script src="matter.js"></script>`

but i use the install code from ` https://www.codebrainer.com/blog/learn-matterjs-with-examples`

it worked

`<script src="https://cdnjs.cloudflare.com/ajax/libs/matter-js/0.17.1/matter.min.js"></script>`

but anyways

i change the code where it had the square to circle and a bunch of circle but they keep rolling of the webpage


1/8/24
i what i make the shape have colors 

i founded a video on youtube about it 

https://www.youtube.com/watch?v=O4w8hbcSFYs

```java
render: {
         fillStyle: 'red', // this fills in the shape with color
         strokeStyle: 'blue', the outine around the shape 
         lineWidth: 3
    }
```

1/22/24
`var boxA = Bodies.rectangle(400, 200, 80, 80);`

the number in front stands for the distance between each of the shape

idk the 200 and the 80 location stands for the height and the width of the shapes

```java
var boxA = Bodies.rectangle(400, 50,  100, 100);
var boxB = Bodies.rectangle(400, 50, 100, 100);
var boxC = Bodies.rectangle(400,50,100,100);
var boxD = Bodies.rectangle(400,50,100,100);
var boxE = Bodies.rectangle(300, 50, 100, 100);
var boxF = Bodies.rectangle(300, 50, 100, 100);
var boxG = Bodies.rectangle(300, 50, 100, 100);
var boxH = Bodies.rectangle(300, 50, 100, 100);
var boxI = Bodies.rectangle(200, 50, 100, 100);
var boxJ = Bodies.rectangle(200, 50, 100, 100);
var boxK = Bodies.rectangle(200, 50, 100, 100);
var boxL = Bodies.rectangle(200, 50, 100, 100);
var boxM = Bodies.rectangle(100, 50, 100, 100);
var boxN = Bodies.rectangle(100, 50, 100, 100);
var boxO = Bodies.rectangle(100, 50, 100, 100);
var boxP = Bodies.rectangle(100, 50, 100, 100);
var ground = Bodies.rectangle(400, 610, 810, 60, { isStatic: true });

// add all of the bodies to the world
Composite.add(engine.world, [boxA, boxB,boxC,boxD,boxE,boxF,boxG,boxH,boxI,boxJ,boxK,boxL,boxM,boxN,boxO,boxP, ground]);
```
code above used to create a stack of blocks


2/1/24
i added a circle for it to be the laucher and a platform for it to stay on it 
```java
var ballA = Bodies.circle(600,500,30,70);
var groundB = Bodies.rectangle(600, 500, 150, 30, { isStatic: false });
```
i'm still try for the circle to move and hit it target 


2/26/24

i try creating the model of how the sling shot is going to look like

i made some rectangle which is going to be the holder of the shape

i still trying to make a label of the shapes on the rectangle


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
var bucketA = Bodies.rectangle(250,100,130,80);
var bucketB = Bodies.rectangle(100,530,130,80,{isStatic:true});
var bucketC = Bodies.rectangle(60,300,130,60,{isStatic:true});


var ground = Bodies.rectangle(400, 600, 810, 60, { isStatic: true });
var ballA = Bodies.circle(600,150,30,70);
var groundB = Bodies.rectangle(600, 200, 100, 10, { isStatic: true });



// add all of the bodies to the world
Composite.add(engine.world, [ballA,groundB,bucketA,bucketB,bucketC ,ground]);
// run the renderer 
Render.run(render);

// create runner
var runner = Runner.create();

// run the engine
Runner.run(runner, engine);
```

3/4/24
after all the trys in jsbin i decide to  it move to the codespace and add it there but is not really working well 



