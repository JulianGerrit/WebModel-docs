﻿# Language Documentation

**Steyn Language** `[steːn ˈleɪŋɡwɪd͡ʒ]` is a language designed for scientific modelling.\
It's syntax was inspired by programming languages such as Java.\
The language supports simple if statements and Mathematical expressions.

Steyn Language was designed by steenooo aka Freek Steen.

## Syntax

The language has it's roots in languages such as Java.\
The execution of a model requires a *Start Instruction*.\
The syntax of which is similar to the model. The start instructions do not support conditional statements.

### Variables
Variables are defined globally. The scope of initialization does not affect access to the variables.
Variables can be uppercase and lowercase and consist. There is no maximal length of a variable.
Variables can only consist of characters in the basic latin alphabet. 
Numbers and special characters are not supported.

The language recognizes two variable types. Hidden and Visible variables.
A visible variable is a variable that will be used to draw the graph. 
To define a visible variable one should use the keyword `draw`.
To define the x axis for this graph, use `X_AXIS` on the position of a color.
```
draw x as X_AXIS;
draw y as (234, 0, 116);
draw z as #4934eb;
```
The color of the line in the graph can be assign through the `as` keyword. 
The color can be defined through HEX, RGB or predefined color values;
Predefined colors have to be written with full uppercase. The following colors were added:
`WHITE, LIGHT_GRAY, DARK_GRAY, BLACK, RED, PINK, ORANGE, YELLOW, GREEN, MAGENTA, CYAN, BLUE.`
Hidden variables do not need to be defined. Both hidden and visible variables should be initialized.
Initialization of variables can be done in the start instructions and in the model.\
Variable Initialization is done through the assignment operator `=`. 
```
a = 10;
b = 5 / 8;
c = 2 * PI;
```



### Conditional Statements
The language supports conditional statements through `if` and `else` statements.
The if statements support
[comparative and logical operators](#conditional-operators)

### Model Termination
To terminate a running model, it's possible to use the keyword `end`.\
This will terminate the model the next iteration.\
This keywords allows the user to limit the amount of iterations.
```
if(t > 10) {
   end;
}
```

### Math Operators

| Action   	| Operator 	| Example 	|
| ---- | ---- | -------: |
| Add      	| +        	| a + b   	|
| Subtract 	| -        	| a - b   	|
| Multiply 	| *        	| a * b   	|
| Divide   	| /        	| a / b   	|
| Power    	| ^        	| a ^ b   	|

Illegal mathematical operations (such as division by zero) will result in a NaN value.\
The model will continue executing.



### Conditional Operators

| Action            	| Operator 	| Example 	|
| ---- | ---- | -------: |
| Greater           	| \>        | a > b   	|
| Lesser            	| <        	| a < b   	|
| Greater Or Equal  	| >=       	| a >= b  	|
| Lesser or Equal   	| <=       	| a <= b  	|
| Equals            	| ==       	| a == b  	|
| And               	| &&       	| a && b  	|
| Or                	|  \|\|      	| a \|\| b  |
| Not               	| !        	| !a      	|

### Functions
The language supports predefined mathematical functions\
Functions can have either one or two parameters.\
The provided functions are implemented through `kotlin.math`.
```
a = sin(0.45);
b = round(0.5435633563, 3);

```

###### TODO: Add table of functions...

## Examples

##### Increment T. Stop at t > 10
###### Start Instructions
```
draw x as X_AXIS;
draw t as RED;
t = 0;
dt = 1;
```
###### Model
```
if(t > 10) {
   end;
}
x+=dt;
t+=dt;
```
##### Simple harmonic motion
###### Start Instructions
```
draw F as RED;
draw v as BLUE;
draw t as X_AXIS;
t = 0;
dt = 0.001;
C = 2;
m = 0.81;
u = 0.5;
v = 0;
a = 0;
```
###### Model
```
F = -C * u;
a = F/m;
v = v + a * dt;
u = u + v * dt;
t+=dt;
```

##### Damped oscillations
###### Start Instructions
```
draw Fn as RED;
draw v as BLUE;
draw t as X_AXIS;
t = 0;
dt = 0.001;
C = 2;
m = 0.81;
u = 0.5;
v = 0;
a = 0;
k = 0.1;
```
###### Model
```
Fv = -C * u;
Fw = -k * v;
Fn = Fv * Fw;
A = Fn/m;
v = v + a * dt;
u = u + v * dt;
t+=dt;
```
