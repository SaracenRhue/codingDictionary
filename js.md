# javascript

```javascript
console.log("Hello World!");
```

' ' can be used instead of " " and ; is optional

## Datatypes

```javascript
var myNum = 5; //global variable
let myString = "Hello"; //local variable
const myBool = true; //local constant
```

```javascript
var myNumbrs[] = {1,2,3}; //array
var dict = {name:"John", age:30, city:"New York"}; //dictionary
```

## Casting

change the data type of a variable

```javascript
var x = 3
var x_as_string = String(x)
var x_as_int = Number(x_as_string)
```

## String Operations

```javascript
var a = "Hello, World!"
var b = 420
a += b //Hello, World!420
```

```javascript
a.length //16
a.slice(0, 5) //returns the first 5 letters (Hello)
a.charAt(1) //returns the second letter (e)
a.toUpperCase() //sets all letters as upper case
a.toLowerCase() //sets all letters as lower case
a.trim() //removes all whitespaces
a.replace("H", "J") //replase a letter
```

## Arrays

can contain different data types

```javascript
var cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Opel"; //change value
cars.push("Audi"); //add value
cars.pop(); //remove last value
cars.shift(); //remove first value
cars.length; //returns the length
```

## Flow Control

### if else statement

```javascript
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

### switch statement

works with int and char

```javascript
let x = "0";
switch (x) {
  case 0:
    text = "Off";
    break;
  case 1:
    text = "On";
    break;
  default:
    text = "No value found";
}
```

if there is no 'break' the next case will be executed too

### for loop

```javascript
for (var i = 0; i < 5; i++) {
  console.log("helloworld"); //prints helloworld 5 times
}
```

#### loop through array

```javascript
for (var i = 0; i < cars.length; i++) {
  console.log(cars[i]);
}
```

#### forEach

```javascript
cars.forEach((item, index, array) => {
  console.log(item, index);
})
```

## functions

```javascript
function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}

let x = myFunction(4, 3);   // Function is called, return value will end up in x
```

### arrow function

```javascript
var hello = () => {
  return "Hello World!";
}
```

## Query selectors

 select DOM elements

 selects the first element with the tag body

```javascript
var body = document.querySelector('body');
```

selects the element with the id button

```javascript
var button = document.querySelector('#button');
```

selects all elements with the class someclass and returns an array

```javascript
var classElements = document.querySelectorAll('.someclass');
```

## Create elements

```javascript
var newElement = document.createElement('div'); //creates a new div element
var text = document.createTextNode('Hello World!'); //creates a text node
newElement.appendChild(text); //adds the text node to the div element
document.querySelector('body').appendChild(newElewment); //adds the div element to the body
```

### inner HTML

```javascript
var div = document.querySelectorAll('div')[0];
div.innerHTML = '<p>some text</p>'; //replaces the content of the div with a paragraph
```

### HTML attributes

change HTML attributes
(attribute names are written in camelCase)

```javascript
var img = document.querySelectorAll('img')[0]; //selects the first image
body.class += 'someclass'; //adds the class someclass to existing classes
img.src = 'path/to/image.jpg';
img.alt = '#';

var a = document.querySelectorAll('a')[0];
a.href = 'https://github.com/SaracenRhue';
```

### CSS attributes

change CSS attributes
(attribute names are written in camelCase)

```javascript
var body = document.querySelector('body');
body.style.backgroundColor = 'red';
```

## JSON fetch

get data from a JSON file
json files are formatted lika a dictionary {}
or multiple dictionaries in an array [{},{}]

```javascript
fetch("./src/data.json").then((response) => {
      return response.json();
    }).then((json) => {
      json.forEach((object) => {
        console.log(object.name);
      });
    });
```
