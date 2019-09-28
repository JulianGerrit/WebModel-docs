# Language Documentation

Steyn Language is a language designed for scientific modelling.\
It's syntax was inspired by programming languages such as Java.\
The language supports simple if statements and Mathematical expressions.


## Syntax

### Conditional Statements
The language supports conditional statements through `if` and `else` statements.
The if statements support
[comparative and logical operators](#Conditional-Operators)


### Variables
Variables are defined globally.\
The scope which they are defined in does not affect the variables.


### Math Operators


| Action   	| Operator 	| Example 	|
| ---- | ---- | -------: |
| Add      	| +        	| a + b   	|
| Subtract 	| -        	| a - b   	|
| Multiply 	| *        	| a * b   	|
| Divide   	| /        	| a / b   	|
| Power    	| ^        	| a ^ b   	|



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

## Functions


## Examples

##### Increment t
###### Start Instructions
```
draw t as RED;
t = 0;
dt = 1;
```
###### Model
```
if(t > 10) {
   end;
}
t+=dt;
```
##### FOO
###### Start Instructions
###### Model

##### BAR
###### Start Instructions
###### Model