# JavaScript

```JavaScript
console.log("Hello World!");
```

## Datatypes

```JavaScript
var myNum = 5; //global variable
let myString = "Hello"; //local variable
const myBool = true; //local constant
```

```JavaScript
var myNumbrs[] = {1,2,3}; //array
var dict = {name:"John", age:30, city:"New York"}; //dictionary
```

## Casting

change the data type of a variable

```JavaScript
var x = 3
var x_as_string = String(x)
var x_as_int = Number(x_as_string)
```

## String Operations

```JavaScript
var a = "Hello, World!"
var b = 420
a += b //Hello, World!420
```

```JavaScript
a.length //16
a.slice(0, 5) //returns the first 5 letters (Hello)
a.charAt(1) //returns the second letter (e)
a.toUpperCase() //sets all letters as upper case
a.toLowerCase() //sets all letters as lower case
a.trim() //removes all whitespaces
a.replace("H", "J") //replase a letter
```

## Flow Control

```JavaScript

```

## Arrays

```JavaScript
var cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Opel"; //change value
cars.push("Audi"); //add value
cars.pop(); //remove last value
cars.shift(); //remove first value
cars.length; //returns the length
```

loop through array

```JavaScript
for (var i = 0; i < cars.length; i++) {
  console.log(cars[i]);
}
```

loop through array with forEach

```JavaScript
cars.forEach((item, index, array) => {
  console.log(item, index);
});
```

## Query selectors

 select DOM elements

 selects the first element with the tag body

```JavaScript
var body = document.querySelector('body');
```

selects the element with the id button

```JavaScript
var button = document.querySelector('#button');
```

selects all elements with the class someclass and returns an array

```JavaScript
var classElements = document.querySelectorAll('.someclass');
```

## Create elements

```JavaScript
var newElement = document.createElement('div'); //creates a new div element
var text = document.createTextNode('Hello World!'); //creates a text node
newElement.appendChild(text); //adds the text node to the div element
document.querySelector('body').appendChild(newElewment); //adds the div element to the body
```

### inner HTML

```JavaScript
var div = document.querySelectorAll('div')[0];
div.innerHTML = '<p>some text</p>'; //replaces the content of the div with a paragraph
```

### HTML attributes

change HTML attributes
(attribute names are written in camelCase)

```JavaScript
var img = document.querySelectorAll('img')[0];
body.class += 'someclass'; //adds the class someclass to existing classes
img.src = 'path/to/image.jpg';
img.alt = '#';

var a = document.querySelectorAll('a')[0];
a.href = 'https://github.com/SaracenRhue';
```

### CSS attributes

change CSS attributes
(attribute names are written in camelCase)

```JavaScript
var body = document.querySelector('body');
body.style.backgroundColor = 'red';
```

## JSON fetch

get data from a JSON file

```JavaScript
fetch("./src/data.json").then((response) => {
      return response.json();
    }).then((json) => {
      json.forEach((object) => {
        console.log(object.name);
      });
    });
```
