# Introduction

	
Typically a compiler is made up of a front end that converts source programs to a intermediate representation, a middle end that carries out phases of optimizations and a back end that generates target object codes. 

In this project, you are expected to implement the middle part (Data Flow Analysis) of a toy compiler that accepts a subset of C.

The accepted language is a subset of C. The test programs that will be used to evaluate the following properties:

1. There are no pointers in the program.
   
2. There are no structure types in the program.

3. The only data types are integer and floating point scalars and one-dimensional integer arrays.

   
The compiler is written in Java.


# Set Up

Here, we briefly describe the working procedure of the offered compiler.

## Step I: test_prog.c --> {test_prog.adap, test_prog.adap.h}

We use lcc as our compiler's front end that converts the test programs into an intermediate form, ADAP. 
ADAP is actually an abstract syntax tree (AST) whose readable form is dumped into an output file with extension .adap. 
For your convenience, we have already converted the test programs and put into the adapt_files folder in the project template.

## Step II: {test_prog.adap, test_prog.adap.h} --> AST

Now it comes to Java. 
The AST_lib offers classes to transform the .adap files into internal AST representations. 
You'll create an instance of ProgAst using your test program's adap file name as the constructor's input parameter. 
Then you'll be working on the AST all the way until code generation.

## Step III: AST --> test_prog.out.c

The third step is code generation which is simply done by calling the AST's method GenCode(). An output C file will be dumped with extension .out.c. 
Now compile the output .out.c file into an executable object file then run it on your PC, you'll see and check the outputs.

# In Detail

## Data Flow Analysis

The optimizations in this phase involve data flow analysis.

The method is AVAIL.

