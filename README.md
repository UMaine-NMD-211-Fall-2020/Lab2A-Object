# Lab2A-Object
By the end of this lab, you should know what objects are and be able to create your own. 

## Useful REadings
[Daniel Shiffman's tutorial on objects](https://processing.org/tutorials/objects/)
for 
## Lab Process
0. Open Processing
1. Create a folder for lab 2A, `2A-*YOUR FIRST NAME*-*YOUR LAST NAME*`. Create a README.md inside this folder. 
2. Return to your blank processing file. Save your file within it as `2A-*YOUR FIRST NAME*-*YOUR LAST NAME*`
3. Add your introductory comments to the top of your file. Save.
```processing
/*  Lab 2A
    FirstName LastName
    September 16, 2020
    
    Create an Object
    - create an object
    - scale an object
*/
```
4. Fill in the set up section of your document. Consider the canvas size. Consider if you want to see strokes. Consider how you want to draw rectangles and ellipses. 

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
```
5. Draw two of a favored shape on the canvas. This example will use triangles. 
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
  triangle( 100, 100, 100, 200, 200, 200);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 150, 125, 150, 225, 250, 225);
  
}
```
6. Now, we start to build a class for your shape. The example class is TriShape
/*  Lab 2A
    Katarina Hoeger
    September 16, 2020
    
    Create an Object
    - create an object
    - scale an object
*/
TriShape tri;

void setup(){
  size( 500 , 500);   
  noStroke();
  rectMode(CENTER);
  
  // initialize triangle
  tri = new TriShape( 300, 300);
}

void draw(){
  background(255);
  
  tri.display();
}

class TriShape{
  // creates a unified triangle shape
  float cx; // shape center x
  float cy; // shape center y
  
  // lets the computer know what cx and cy should be 
  TriShape( float xIn, float yIn){
    cx = xIn;
    cy = yIn;
  }
  
  // draws triangle for us
  void display(){
  // triangle 1
  fill( 255, 0, 0, 200);
  triangle( 100, 100, 100, 200, 200, 200);
  
  // triangle 2
  fill( 255, 255, 0, 200);
  triangle( 150, 125, 150, 225, 250, 225);
  }
}

## Lab Submissions
Link to your github repository with your lab below.

[Example First Name - 2A ](http://example.com/)



