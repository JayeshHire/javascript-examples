Here are some examples to understand and learn basic variables in javascript.

##instantiating variables in javascript using var keyword

*instantiating variable* 
var processes;
processes =  10; //assigning value to the variable

*instantiating variable and initialising at the same time*
var desktop = "ubuntu";

##instantiating variables in javascript using the let keyword

*instantiating variable*
let processes;
processes = 10 ; //assigning value to the variable

*instantiating variable and intialising at the same time*
let desktop = "ubuntu"; 

Both the let and var keywords are used to initialise variables in javascript. But under the hood both have a different implementation. var was initially used for defining variables in javascript. But due to some problems with it's implementation new keyword let came into the picture. Most of the latest browsers shows support for the let keyword. It is better to define variables with let keyword than with var. Apart from their internal implementation var and let have one more difference among them. Variables declared with var can be again intantiated. But those instantiated using the let keyword cannot be instantiated.

Here's how it is.

var processing_running = true;

//instantiating the variable with the same name. This works fine.
var processing_running = false;

//creating a variable using let
let data_processed = true;

//instantiating the variable again
let data_processed = false;

//above declaring with the let keyword will show error. Because you cannot declare the variable with the same name using let keyword more than once.
//Here is the error on your firefox browser
SyntaxError: redeclaration of formal parameter "data_processed" ;

#Data types in javascript
Javascript is a dynamically typed language. This means that we don't have to explicitly mention the data type of the variable while defining the variable. The javascript engine automatically detects the data type of the variable before compiling it to the machine code. But it is necessary to get familiar with the common data types in javascript programming language.

1. number: -
	The number data type is used to store all different kinds of numerical types inside it. Whether it is integer, floating point, double or long all the numerical data types are stored inside this number data type.
let common_processes = 10; // number data type
let controller_frequency = 9.23; // number data type
let entropy = -2.09; // number data type

2. boolean: -
	All the boolean types such as true or false are stored inside the variables of boolean data type.
let process_finished = true;
let tool_available = false;

3. null: -
	null value is the intentional abscence of an object. It is considered falsy for boolean operations.

4. undefined: -
	While null is the abscence of object, undefined is the abscence of value. 
	Following cases can return us undefined value: -
		1. if we return nothing from a function
		2. if we are accessing a non-existent property of an object
		3. if we declare a variable without initialising it
		4. Many methods return undefined when no element is found

5. BigInt: -
	We can store numbers even beyond the max safe integer limit ( Number.MAX_SAFE_INTEGER ) using BigInt. We can do this by appending n to the number or by using the BigInt() function.

Examples: -
console.log(BigInt(Number.MAX_SAFE_INTEGER) + 2n === BigInt(Number.MAX_SAFE_INTEGER) + 2n);
//you will get true for the above statement

console.log(Number.MAX_SAFE_LIMIT + 2 === Number.MAX_SAFE_LIMIT + 2);
//This will return false because this is in terms of normal number data type.
//number data type cannot hold such large ammounts of data. Hence, you will
//not get the correct results for the values higher than the safe integer limit.


6. string: -
	Any text or a series of characters can be stored in this data type.

Example: -
let name = "Ganesh";
let surname = "Chillale";
//above are few examples of string. 
//I will share more detailed uses of strings and some of it's widely used methods in the upcoming blogs.

7. Symbol: -
	Symbol data type is used for creating unique identifiers. These are used as a name of any property or they can be used as a key for the object. Every Symbol is different from one another. Symbol() function is used for creating symbols.

Example: -	
let name = Symbol("name");
let surname = Symbol("name");
let score = Symbol("score");

let score_chart = {
	name : "jay",
	surname : "vardhan",
	score : 100,
};

//let's try getting the value for prop1
console.log(`obj property 1 : ${score_chart.name}`);

//upon executing we will get the value for the property 1 of score_chart object
//We might feel that name and surname variables are the same but in reality though they are not equal//You can check for yourself using the below statement
console.log(name === surname);

### Here is another example of symbols 
let red = Symbol("red");
let green = Symbol("green");
let blue = Symbol("blue");


let color = {
	red : 180,
	green : 210,
	blue : 68
};

We have created 3 different symbols as the property of the color object. Symbols ensures that every key of the object is unique. If we use a string instead of symbol there could be similar keys created for the same object and this could lead to a major bug.

let's try creating the above color object with the same keys.
let color = {
	"red" : 10,
	"red" : 20,
};
//this will not give us an error
//instead if we try accessing the property we will get the last assigned value to that property

console.log(`Red color : ${color["red"]}`);

From this example we can understand that how much Symbol data type is important in javascript for writing better programmes.

Here we reach to the end of this blog.
In the next blog I will be covering topics like handling strings and some of their useful methods.
