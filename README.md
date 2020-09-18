# Lab2A-Object
By the end of this lab, you should know what objects are and be able to create your own. 

## Useful REadings
[Daniel Shiffman's tutorial on objects](https://processing.org/tutorials/objects/)
for 
## Lab Process
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
## Lab Submissions
Link to your github repository with your lab below.

[Example First Name - 2A ](http://example.com/)



