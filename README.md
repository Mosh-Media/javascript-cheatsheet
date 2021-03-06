# What is this?

Snippets cheat sheet that I am putting together to help us develope faster and cleaner code, while following latest syntax and design practices :boom: :raised_hands:

enjoy!



# Table of content:

- [JavaScript](#javascript)
    - [Data Structures](#data-structures)
    - [Arrow Functions](#arrow-functions)
    - [This](#this)
    - [Classes](#classes)
    - [Objects](#objects)
    - [Prototypes](#prototypes)
    - [Map, Filter and Reduce](#map-filter-and-reduce)
    - [Closures](#closures)
    - [Maps and Sets](#mapsandsets)
    - [Promises](#promises)
    - [Await/Async](#await/async)

- [Angular](#angular)
    - [Angular CLI](#angular-cli)
    - [Modules](#modules)
    - [Routes](#routes)
    - [Components](#components)
    - [Directives](#directives)
    - [Services](#services)
    - [Pipes](#services)
    - [Observables](#observables)
    
- [TypeScript](#typescript)



# Javascript

>An object-oriented computer programming language commonly used to create interactive effects within web browsers.


## Data Structures 

- Stacks
  - push
  - pop
- Queues


## Arrow Functions 

ES5 function syntax

```
const a = 1
const b = 1
const sum = function(a,b){
   return a + b
}
console.log(sum) //2
```

ES6 function syntax
    Cleaner look and easier to debug

```
const a = 1
const b = 1
const sum = (a,b) => {return a + b}
console.log(sum) //2
```

#### Classes 

A Class is basically a blueprint that describes the object to be created.

- Classes inherit properties and methods from other classes by extending them.
- Classes establish a hierarchical relationships.

```
class Cars{
  
  constructor(name){
    this.name = name;
    this.type = 'vehicle';
    this.wheels = true; 
  }

  getType(){
    return this.type;
  }
  
}

//Extending class Cars to Boats
class Boats extends Cars{
  
  constructor(name){
    super(name);
    this.wheels = false;
  }
  
    getType(){
    return super.getType();
  }

}

//Initiating new instance of class Boat and pass it a boat name

let boat = new Boats('Zombies Can\'t Swim');

console.log(boat); //{ name: "Zombies Can't Swim", type: "vehicle", wheels: false }


```
## Objects


- Creating an Objects:
  - Object literals
  - Constructors
  - ES6 Classes

```
class vehicle {
 constructor(name, type){
 	this.name = name;
    this.type = type;
 }
}

let boat = new vehicle('Unsinkable','Boat');
``` 
  
- Shallow copying an Object:  
  - Spread Syntax ```[...]```
  - ```Object.assign()``` method

```
let dog = {
	type: "Sharpie",
  name: "Bentley"  
}
//Spread Syntax
let puppy = {...dog}

console.log(puppy); //{ type: "Sharpie", name: "Bentley" }

//Object assign method
let doggo = Object.assign({}, dog);

console.log(doggo) //{ type: "Sharpie", name: "Bentley" }
```

We can use Object methods such as entries.

```
let keys = Object.entries(boat)[0]; //["name", "Unsinkable"]

```

Destructuring is used to extract values from Object properties into another variable.

```
const {name, type} = boat;
console.log({type}) //{ type: "Boat" }
```

#### Prototypes
- Concatenative inheritance
- Inheriting methods and properties directly from another object
- Prototype delegation


```
const gasCars = {
  BMW: "German",
  Audi: "German"
};

const electricCars = Object.assign({Tesla: "American"}, gasCars);

console.log(electricCars.BMW);
// expected output: German

```

### Map, Filter and Reduce

```
const cars = [

  { name:'BMW', id:1 },
  { name:'Tesla', id:2 },
  { name:'Audi', id:3 }

];

```
**Map** works on an array and return an array that’s it

```
const carNames = cars.map((car, index, cars) => car.name);
console.log(carNames); //["BMW", "Tesla", "Audi"]

```
**Filter** works on array return an array for filtered items.

```
const bmw = cars.filter((car, index, cars) => car.name === 'BMW') 
console.log(bmw) //{ name: "BMW", id: 1 }
```
**Reduce** works on an array but can return anything you want it to return. 
```
const allCars = cars.reduce((all, car, index, cars) => all + ' ' +car.name, 'All Cars:') 
console.log(allCars) // "All Cars: BMW Tesla Audi"
```

#### Closures

Closures are a returned function inside of a function.

- Returned function has access to properties in original function.
- Function variables are enclosed in the scope of the function
- Used in callbacks.
- Used for data privacy.

```


const sendCode = (code) => {
  

  return {
    send: () => code
  }
  
}

const testClosure = sendCode('123').send();

console.log(testClosure) //123

```


#### Maps and Sets

Basic map operations

```
let map = new Map();

map.set('value', 100);

map.get('value') //100

map.has('value') //true

map.delete('value') //true

map.has('value') //false

map.clear();

map.size //0

```

#### Sets

Sets basic operations

```
let cars = new Set();

cars.add('BMW')

cars.has('BMW') //true

cars.delete('BMW') //true

cars.has('BMW') //false

cars.size //1

cars.clear( );

cars.size //0
```
#### Find

```
const electricCar = carNames.find(car => car !== "Tesla")

console.log(electricCar) //["BMW", "Audi"]
```
#### Find Index

```
const carIndex = [...cars].findIndex((key) => key.name == "Tesla" );
console.log(carIndex); //{ id: 2, name: "Tesla" } 
```

#### Repeat

console.log("Value".repeat(3)) //ValueValueValue

#### For in loop

```
let array = [1,2,3];

for ( let i in array){ 
  console.log(array[i]);
}
```

#### Promises

Callbacks alternatives

```
function delay(ms) {
  return new Promise(resolve => setTimeout( resolve, ms));
}
```

```

delay(3000).then(() => alert('runs after 3 seconds'));

```

#### Await/Async

Promises alternative

```
//Generates a number from 1 to 10 
function randomNum(){
	return Math.floor(Math.random() * 10);
}

//Returns the sum of both random values 
const sum = async () => {
  
  const x = await randomNum(); //Output: 5
  const y = await randomNum(); //Output: 10
  return x + y; //Output: 15
  
}

```




## Angular

- [ ] What is Angular ?
- [ ] Angular CLI ?

#### Angular CLI

Angular Command line, helps automate some process like generating and building out app

#### Routes

Routing basically enables your user to navigate from one view/component to another without a page reload. 

Sample routes snippet

```
const routes: Routes = [
  { path: '', loadChildren: './tabs/tabs.module#TabsPageModule' },
  { path: '**', loadChildren: './tabs/tabs.module#TabsPageModule' }

];
```
#### Modules

#### Components

#### Directives

We have three types of directives:

1. Component Directives
2. Attribute Directives

Retains the DOM element and dynamically change the behavior of the component or element.

```
<div [hidden]="true"> Hidden div </div>
<p [style.color]="blue"> Blue colored paragraph </p>

```
3. Structural Directives

Completely creates, destroys and re-creates the DOM element

```*ngIf``` and ```*ngFor```


#### Built Directives

```
<div *ngIf="(users$ | async).length"> </div>
<ul *ngFor="(let user of users$ | async)"> </ul>

```
#### Services

- [ ] What are services used for?
 
#### Pipes

- [ ] Async pipes
- [ ] Subscribe to an Observable
  
#### Observables
- [ ] What is Observables
- [ ] Create Observable

Import Observable and HttpClient

```
import { Observable } from 'rxjs';
import { HttpClient } from '@angular/common/http';

```
Get http API resources

```
public posts$ :Observable<any>

constructor(public http:HttpClient){}

ngOnInit() {

    this.posts$ = this.getPosts();

}

getPosts(): Observable<any[]> {

    return this.get.http<any[]>('ENTER_API_URI', {
        params: {
          per_page: '12'
        }
      });
}


```


```
Subscribe to Pipe

```



## TypeScript

- [ ] Why typed language?

```
search(term: string) : array[]{

}

```