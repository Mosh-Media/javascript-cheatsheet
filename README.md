

## Map function 

```
const smartPhones = [
  { name:'iphone', price:649 },
  { name:'Galaxy S6', price:576 },
  { name:'Galaxy Note 5', price:489 }
];

```
```
let arr = [1, 2, 3, 4, 5];
let arr2 = arr.map(num => num * 2).filter(num => num > 5);
// arr2 = [6, 8, 10]
```
```
const prices = smartPhones.map(smartPhone => smartPhone.price);
console.log(prices);
```

## Working with promises

```
function delay(ms) {
  return new Promise(resolve => setTimeout( resolve, ms));
}
```

```
delay(3000).then(() => alert('runs after 3 seconds'));
```

## For in loop

```
let array = [1,2,3];

for ( let i in array){
  
  console.log(array[i]);
  
}
```

## Angular loops
```
*ngIf="(users$ | async).length"
*ngFor="(let user of users$ | async)"
```



## observables

## pipe

## subscribe

