# Lab2A-Object
By the end of this lab, you should know what objects are and be able to create your own objects. You should be able to scale them too. 

You specifically need to produce an image with
- 3 or more objects placed in different places on the canvas
- at least 2 objects scaled


## Useful REadings
[Daniel Shiffman's tutorial on objects](https://processing.org/tutorials/objects/)
for 
## Lab Process
Run through these steps to finish the lab. Remember to save frequently!
### Setup
0. Open Processing
1. Create a folder for lab 2A, `2A-*YOUR FIRST NAME*-*YOUR LAST NAME*`. 
Create a README.md inside this folder. 
2. Return to your blank processing file. 
Save your file within it as `Lab2A-*YOUR FIRST NAME*-*YOUR LAST NAME*`
3. Add your introductory comments to the top of your file. Save.
```processing
/*  Lab 2A
    Katarina Hoeger
    September 16, 2020
    
    Create an Object
    - create an object
    - scale an object
    
    File contains
    1. 3 objects
    2. an example of a scaled object
*/
```
4. Fill in the set up section of your document. 
Consider the canvas size. Consider if you want to see strokes. 
Consider how you want to draw rectangles and ellipses. 
My example uses trianges, so I will not use rectMode or ellipseMode

```processing
/*  Lab 2A
    Katarina Hoeger
    September 16, 2020
    
    Create an Object
    - create an object
    - scale an object
*/

void setup(){
  size( 500, 500);
  
  noStroke(); // get rid of outlines
}
```
### Hardcode Shape with a Class
5. Draw two (or more) of a favored shape on the canvas. 
This example will use triangles.  
Choose your own set of shapes.
```processing
/*  Lab 2A
    Katarina Hoeger
    September 16, 2020
    
    Create an Object
    - create an object
    - scale an object
*/

void setup(){
  size( 500 , 500);   
  noStroke();
  rectMode(CENTER);
}

void draw(){
  background(255);
  
  // triangle 1
  fill( 255, 0, 0, 200);
  triangle( 100, 100,       //x, y per point
            100, 300, 
            300, 300);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 200, 200,       // x, y per point
            200, 400, 
            400, 400);
}
```
#### Beginnings of Class Formation
6. Now, we start to build a class for your shape. 
The example class is TriShape. 
We first make the structure of a class. 
```processing
void setup(){
  size( 500 , 500);   
  noStroke();
  rectMode(CENTER);
}

void draw(){
  background(255);
  
  // triangle 1
  fill( 255, 0, 0, 200);
  triangle( 100, 100,       //x, y per point
            100, 300, 
            300, 300);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 200, 200,       // x, y per point
            200, 400, 
            400, 400);
}
/*CHANGES START*/
class TriShape{
  
  // class intrinsic values
  
  // constructor
  TriShape(){ 
  }
  
  // display
}
/*CHANGES END*/
```
7. We have the beginnings of a class, but we need to make the class a global class, so that we can use it in our overall code. 
Do this by declaring the class above void setup. 
```processing
/*CHANGES START*/
TriShape tri1;
/*CHANGES END*/

void setup(){
  size( 500 , 500);   
  noStroke();
  rectMode(CENTER);
}

void draw(){
  background(255);
  
  // triangle 1
  fill( 255, 0, 0, 200);
  triangle( 100, 100,       //x, y per point
            100, 300, 
            300, 300);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 200, 200,       // x, y per point
            200, 400, 
            400, 400);
}

class TriShape{
  
  // class intrinsic values
  
  // constructor
  TriShape(){ 
  }
  
  // display
}
```
8. Next, we need to create an instance of TriShape object. 
```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  /* CHANGE START */
  // initialize trishape
  tri1 = new TriShape();
  /* CHANGE END */
}

void draw(){
  background(255);
  
  // triangle 1
  fill( 255, 0, 0, 200);
  triangle( 100, 100,       //x, y per point
            100, 300, 
            300, 300);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 200, 200,       // x, y per point
            200, 400, 
            400, 400);
}

class TriShape{
  
  // class intrinsic values
  
  // constructor
  TriShape(){ 
  }
  
  // display
}
```
9. Our class isn't doing anything yet. 
Show this to yourself by commenting out our draw triangle lines. 
Then, uncomment them.

10. Create a void display function / method inside of your class object definition. 
```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  // initialize trishape
  tri1 = new TriShape();
}

void draw(){
  background(255);
  /* CHANGE 1 START*/
  /* CHANGE 1 END*/
}

class TriShape{
  
  // class intrinsic values
  
  // constructor
  TriShape(){ 
  }
  
  /* CHANGE 2 START*/
  // display
  void display(){
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( 100, 100,       //x, y per point
              100, 300, 
              300, 300);
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( 200, 200,       // x, y per point
              200, 400, 
              400, 400);
  }
  /* CHANGE 2 END*/
  
}
```
11. Run the file. 
You still cannot see the triangle. 
We need to display `tri1` (or your class instance name) in draw. 
Once you make the changes below, run again, and you should be able to see the object. 
```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  // initialize trishape
  tri1 = new TriShape();
}

void draw(){
  background(255);
  
  /* CHANGE START */
  // display objects
  tri1.display();
  /* CHANGE END */
}

class TriShape{
  
  // class intrinsic values
  
  // constructor
  TriShape(){ 
  }
  
  // display
  void display(){
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( 100, 100,       //x, y per point
              100, 300, 
              300, 300);
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( 200, 200,       // x, y per point
              200, 400, 
              400, 400);
  }
}
```
### Generalized Class
Right now, our conglomerate shape is hardcoded.
That means, we had to physically say where each point is laid out. 
If we can write out the orientation of each shape with respect to one point in the shape, we can place the object wherever we want. 

12. Our shapes are currently hardcoded. 
We need to write the shapes in terms of their center points for the entire shape is. 
We need to define local variables for the class, values intrinsic to any instance of this class object. 
```processing

TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  // initialize trishape
  tri1 = new TriShape();
}

void draw(){
  background(255);
  
  // display objects
  tri1.display();
}

class TriShape{
  
  // class intrinsic values
  /* CHANGES HERE */
  float cx;
  float cy;
  /* END CHANGES */
  
  // constructor
  TriShape(){ 
  }
  
  // display
  void display(){
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( 100, 100,       //x, y per point
              100, 300, 
              300, 300);
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( 200, 200,       // x, y per point
              200, 400, 
              400, 400);
  }
}
```
13. We need to add the local variales by adding them to the constructor. 
Two changes were made - one in the constructor, one in the method setup where we initialize TriShape.
```processing

TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  /* CHANGE 1 HERE */
  // initialize trishape 
  tri1 = new TriShape( 250 , 250 ); // TriShape object centered at (250, 250)
  /* END CHANGE 1 */
}

void draw(){
  background(255);
  
  // display objects
  tri1.display();
}

class TriShape{
  
  // class intrinsic values
  float cx;
  float cy;
  
  /* CHANGE 2 HERE */
  // constructor
  TriShape( float xInput, float yInput){
    cx = xInput;
    cy = yInput;
  }
  /* END CHANGE 2 */
  
  // display
  void display(){
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( 100, 100,       //x, y per point
              100, 300, 
              300, 300);
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( 200, 200,       // x, y per point
              200, 400, 
              400, 400);
  }
}
```
14. We rewrite our shape in terms of  our centerpoints. 
If you have uncentered rectangles, ellipses, or a triangle write it in terms of how far each point is from the centerpoint of the conglomerate shape.
If you have centered rectangles and ellipses, you need to figure out how to write the centerpoint of each shape the object is composed of in terms of conglomerate shape's centerpoint.

*Triangle example below.* (I hope to add a rectangle or ellipse example shortly, but let's make sure all the rest of the lab work goees up first. )

```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();

  // initialize trishape 
  tri1 = new TriShape( 250 , 250 ); // TriShape object centered at (250, 250)
}

void draw(){
  background(255);
  
  // display objects
  tri1.display();
}

class TriShape{
  
  // class intrinsic values
  float cx;
  float cy;
  
  // constructor
  TriShape( float xInput, float yInput){
    cx = xInput;
    cy = yInput;
  }

  // display
  void display(){
    /* START CHANGES */
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( cx - 150,   cy - 150,   // x1, y1
              cx - 150,   cy + 50,    // x2, y2
              cx + 50,    cy + 50);   // x3, y3
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( cx - 50   ,   cy - 50    ,   // x1, y1
              cx - 50   ,   cy + 150   ,   // x2, y2
              cx + 150  ,   cy +150    );  // x3, y3
     /* END CHANGES */
  }
}
```

And, that's it! You now have generally defined, moveable class objects.

### Make Your Class Scaleable
15. The first step of scaling the shape is to add a scalar input to the class. 
We need to add it to the local variables and constructor, as well as fix the instance where we instantiate the object. 
```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  /* START CHANGES 1*/
  // initialize trishape 
  tri1 = new TriShape( 250 , 250 , 0.7); // TriShape object centered at (250, 250)
  /* END CHANGES */
}

void draw(){
  background(255);
  
  // display objects
  tri1.display();
}

class TriShape{
  
  /* START CHANGES 2 */
  // class intrinsic values
  float cx; // centerpoint's x
  float cy; // centerpoint's y
  float s;  // scalar
  
  // constructor
  TriShape( float xInput, float yInput, float scalar){
    cx = xInput;
    cy = yInput;
    s = scalar;
  }
  /* END CHANGES 2*/

  // display
  void display(){
    // triangle 1
    fill( 255, 0, 0, 200);
    triangle( cx - 150,   cy - 150,   // x1, y1
              cx - 150,   cy + 50,    // x2, y2
              cx + 50,    cy + 50);   // x3, y3
    
    // triangle 2
    fill( 255, 255, 0, 200);
    triangle( cx - 50   ,   cy - 50    ,   // x1, y1
              cx - 50   ,   cy + 150   ,   // x2, y2
              cx + 150  ,   cy +150    );  // x3, y3
  }
}
```
16. We need to use the scalar we added. Multiply everything related to object placement in the display method by the scalar. All centerpoints. All widths and heights. All endpoints. 
```processing
TriShape tri1;

void setup(){
  size( 500 , 500);   
  noStroke();
  
  // initialize trishape 
  tri1 = new TriShape( 250 , 250 , 0.7); // TriShape object centered at (250, 250)
}

void draw(){
  background(255);
  
  // display objects
  tri1.display();
}

class TriShape{
  

  // class intrinsic values
  float cx; // centerpoint's x
  float cy; // centerpoint's y
  float s;  // scalar
  
  // constructor
  TriShape( float xInput, float yInput, float scalar){
    cx = xInput;
    cy = yInput;
    s = scalar;
  }


  // display
  void display(){
    /* CHANGES START */
    // triangle 1
    fill( 255 , 0 , 0 , 200);  // r , g, b , transparency
    triangle( s*(cx - 150  ), s*(cy - 150), // x1, y1
              s*(cx - 150)  , s*(cy + 50),  // x2, y2
              s*(cx + 50 )  , s*(cy + 50)); // x3, y3
  
    // triangle 2
    fill( 255 , 255, 0 , 200 );
    triangle( s*(cx - 50)   ,   s*(cy - 50)  ,   // x1, y1
              s*(cx - 50)   ,   s*(cy + 150)  ,  // x2, y2
              s*(cx + 150)  ,  s*(cy +150)  );  // x3, y3
    /* CHANGES END */
  }
}
```
This time, when you run the code, you should see the changes!
### Multiple Class Objects
17. We have a class. We can make multiple instances of the class and make a cool pattern. This requires 3 changes. Design something with your shape. 
```processing
/* CHANGE 1 */
TriShape tri1;
TriShape tri2;
TriShape tri3;
TriShape tri4;
TriShape tri5;
/* END CHANGE 1 */

void setup(){
  size( 500 , 500);   
  noStroke();
  
  /* CHANGE 2 */
  // initialize trishape 
  tri1 = new TriShape( 4750 , 1000 , 0.1); // TriShape object centered at (250, 250)
  tri2 = new TriShape( 700 , 150, 0.5);
  tri3 = new TriShape( 175 , 325, 1);
  tri4 = new TriShape( 250 , 150, 1.3);
  tri5 = new TriShape( 200 , 150, 0.3);
  /* END CHANGE 2 */
}

void draw(){
  background(255);
  
  /* CHANGE 3 */
  // display objects
  tri1.display();
  tri2.display();
  tri3.display();
  tri4.display();
  tri5.display();
  /* END CHANGE 3 */
}

class TriShape{
  

  // class intrinsic values
  float cx; // centerpoint's x
  float cy; // centerpoint's y
  float s;  // scalar
  
  // constructor
  TriShape( float xInput, float yInput, float scalar){
    cx = xInput;
    cy = yInput;
    s = scalar;
  }


  // display
  void display(){
    /* CHANGES START */
    // triangle 1
    fill( 255 , 0 , 0 , 200);  // r , g, b , transparency
    triangle( s*(cx - 150  ), s*(cy - 150), // x1, y1
              s*(cx - 150)  , s*(cy + 50),  // x2, y2
              s*(cx + 50 )  , s*(cy + 50)); // x3, y3
  
    // triangle 2
    fill( 255 , 255, 0 , 200 );
    triangle( s*(cx - 50)   ,   s*(cy - 50)  ,   // x1, y1
              s*(cx - 50)   ,   s*(cy + 150)  ,  // x2, y2
              s*(cx + 150)  ,  s*(cy +150)  );  // x3, y3
    /* CHANGES END */
  }
}
```

## Lab Submissions
Link to your github repository with your lab below.

[Example First Name - 2A ](http://example.com/)



