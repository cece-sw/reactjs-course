# SECTION 1

This section's goal is to have a refresher on the javascript ofter used syntax. The code present in this section will be usable and used as a reminded of the possibilities offered by Javascript *ES7* or describe as well as *ES2016*.

## let and const

const is used when we assign a value once and we plan to never changed it anymore. This is never going to receive a new value.

let is pretty much equivalent to the old "var" and tend to replace it. The use of var is discouraged since ES6. "let" is used when the value inside is really variable.

A usefull tool is [jsbin.com](https://www.jsbin.com) to test js code directly.

## arrow functions

a normal function is declared so: "**function myFnc(){}**" while an arrow function is declared so "**const myFnc=()=>{}**".

`function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  () => alert("You agreed."),
  () => alert("You canceled the execution.")
);`

Arrow function can be use inside another function with .map() for exemple 
	array.map((string) => string.length)
	
the arrow function keep the context and thus we can use this ".this" keyword as expected.

`const multiply = number => number * 2

console.log(multiply(2))

##exports and imports (modules)

==person.js==
```
const person = {
	name:'Max'
}
export default person
```
==utility.js==
```
export const clean = () =>{...}
export const baseData = 10 ;
```
==app.js==
```
import person from './person.js'
import prs from './person.js'

import {baseData} from './utility.js'
import {clean} from './utility.js'
```
or
`
import * as bundled from './utility.js'
`

## classes old way

```
class Person {
	name = 'Max'
	call = () => {...}
}

const myPerson = new Person()
	myPerson.call()
console.log(myPerson.name)

class Master {
	constructor(){
	this.gender = 'male'
	}
	
	printGender(){
	console.log(this.gender)
	}
}

class Person extends Master{
	constructor(){
	super();
	this.name = 'Max'	
	}
```
## classes with ES6
```
class Human {
	gender = 'male'
	printGender = () => {
		console.log(this.gender)
	}
}


class Person extends Human{
	name='max'	
	gender='female'	
	printMyName = () =>{
		console.log(this.name)
		}
	}
```

## classes, properties and methods

| properties 				| methods/functions |
| ----------- 				| ----------- |
| ES6										|
| ` constructor(){this.myProperty = 'value'}`			|myMethod(){...}|
| ES7										|
| myProperty = 'value'			| myMethod= () =>{}			| 

# Spread & Rest Operator
## spread
"..." --> Spread --> used to split up array elements OR objecti properties\
```
	const newArray = [...oldArray,1,2]
	const newObject = {...oldObject, newProp:5
	}
```
## rest
"..."	--> used to merge a list of function arguments into an array\
```
	function sortArgs(...args){
		return args.sort()
	}
```
# destructuring

## Array destructuring
```
[a, ,b] = ['Hello','ara','Max']
console.log(a) \\Hello
console.log(b) \\Max
```
## Object destructuring

```
{name} = {name:'Hello',age:28}
console.log(name) \\Max
console.log(age) \\undefined
```

Objects and array are reference types and not primitive types
object is stored in memory and the pointer is copied when we re assigned the value and point to the same object.
same occurs for arrays.

code to really copying the object
```
const person = {
	name:'Max'
}
const secondPerson ={
	...person
}
person.name = 'Manu'
```

function callMe(name) { 
    console.log(name);
}
to
const callMe = function(name) { 
    console.log(name);
}
to
const callMe = (name) => { 
    console.log(name);
}
with only one argument
const callMe = name => { 
    console.log(name);
}
to simply return a value
const returnMe = name => name