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

##classes
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

##classes, properties and methods

| properties 				| methods/functions |
| ----------- 				| ----------- |
| ES6										|
| ----------- 				| ----------- 				|
| ` constructor(){			|myMethod(){...}
|	this.myProperty = 'value'	|
|	}` 				|
| ----------- 				| ----------- 				|
| ES7										|
| ----------- 				| ----------- 				|
| myProperty = 'value'			| myMethod= () =>{}			| 





