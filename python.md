# Python

```python
print("Hello, World!")
```

' ' can be used instead of " "

## Datatypes

```python
x = "Hello World"  #str
x = 20  #int
x = 20.5  #float
x = 1j  #complex
x = ["apple", "banana", "cherry"]  #list
x = ("apple", "banana", "cherry")  #tuple
x = range(6)  #range
x = {"name": "John", "age": 36}  #dict
x = {"apple", "banana", "cherry"}  #set
x = frozenset({"apple", "banana", "cherry"})  #rozenset
x = True  #bool
x = b"Hello"  #bytes
x = bytearray(5)  #bytearray
x = memoryview(bytes(5))  #memoryview
```

## Operations

```python
x = 2**3 #2^3  
x = 2//3 #int(2/3)
```

## In and Output

```python
username = input("Enter username:") #write user input as string in variable
print(f"my name is {username}")
```

## Casting

change the data type of a variable

```python
print(type(x))  #print the type of x
x = str(3.0)  #convert to string
y = int(2.8)  #convert to int
z = float("3")  #convert to float
```

## String Operations

```python
a = "Hello, World!"
a[:5]  #returns the first 5 letters (Hello)
a[1]  #returns the second letter (e)
a.upper()  #sets all letters as upper case
a.lower()  #sets all letters as lower case
a.strip()  #removes all whitespaces
a.replace("H", "J")  #replase a letter
a.split(",")  # returns ["Hello", " World!"]
a.index("H")  #returns the index of a character in a string
```

## Lists

can contain different data types

```python
#Tuple
eggs = ("hello", 42, 0.5)  #elements in tupels are final!
#Arrays
li = [69, "banana", True]
print(li)
li[0] #returns the first element
len(li) #returns the length
li.insert(2, "watermelon") #insert an item at index 2
li.append("orange") #append an item at the end
li.remove("banana") #remove an  item
li.pop(1) #remove item at index 1
thislist = li.copy() #copy a list
tropical = ["mango", "pineapple", "papaya"]
li.extend(tropical) #add one list to anouter
li.sort() #sort the list
li.sort(reverse=True)  #sort the list descending
li.reverse() #reverse the list order
tropical.index("mango") #returns the index to a value
list.clear()  #clear the list content
del li #delete the entire list

list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2  #join two list
print(list3)

#multiple assignment trick
cat = ["fat", "gray", "loud"]
size, color, disposition = cat
#short for...
size = cat[0]
color = cat[1]
disposition = cat[2]
```

## Dictionaries

```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964, "year": 2020}
print(thisdict)
thisdict.get("model")  #returns the value of the "model" key
thisdict.keys()  #returns a list of the keys
thisdict.values() #returns a list of all values
thisdict["year"] = 2018 #change a value
thisdict.update({"year": 2020}) #changa/add key:value pair
thisdict.pop("model") #remove an item
mydict = thisdict.copy() #copy the dictionary
```

## Flow Control

### if else statement

```python
a = 200
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")

```

### while loop

```python

i = 0
while i < 6:
    i += 1
    if i == 3:
        continue  #restart the loop
    print(i)      #break to quit the loop

```

### for loop

```python
fruits = ["apple", "banana", "cherry"]
for item in fruits:
    print(item)

for i in range(5): #execute 5 times
    print(fruits)
```

### match /switch case statement

only supported in python >= 3.10

```python
n = 0
match n:
    case 0:
        print("printed if n = 0")
    case 1:
        print("printed if n = 1")
    case _:
        print("printed if none above apply")
```

## Functions

```python
def my_function(fname, lname):
    return f"{fname} {lname}"

my_function("Emil", "Refsnes")
iterable = [1, 2, 3]
map(my_function, iterable) #executes a specified function for each item in an iterable

x = lambda a: a + 10 #lambda/anonymous function
print(x(5))
```

## Classes

public: standart /items are globaly availible
private: 2 underscores at the beginning /items only availible in the current class
protected: 1 underscore at the beginning /items only availible in the current class and subclasses

```python
class Person:
    def __init__(self, name, age): #constructor //destructor: __del__
        self.name = name
        self.age = age

    def myfunc(self):
        print("Hello my name is " + self.name)

class Student(Person): #Student is a chld class of person
    pass #Student inherits the constructor and all methods from person

p1 = Person("John", 36) #create object

print(p1.name)
print(p1.age)

p1.myfunc() #call method
```

## Exceptions

```python
try:
    print(x)
except NameError:
    print("Variable x is not defined")
except:
    print("Something else went wrong")
finally:
    print("The "try except" is finished")
```

## File handling

```python
with open("text.txt", "w") as f: #open file in write mode and store in f
    f.write("Woops! I have deleted the content!") #write content/overwrite existing content

with open("text.txt", "r") as f:  #open file in read mode and store in f
    f.read()  #returns file content as string

# r+ Opens a file for both reading and writing
# w+ Opens a file for both writing and reading. Overwrites the existing file if the file exists. If the file does not exist, it creates a new file for reading and writing
import shutil

shutil.copy("exp.py", "Kap04/exp.py")
shutil.move("exp.py", "Kap04/exp.py")
```

## OS Module

```python
import os

os.listdir("./") #list all files in the current directory
os.system("ls") #run a shell command


os.remove("exp.py") #delete file
os.rmdir("myfolder") #delete folder
os.mkdir("myfolder") #create folder
os.getcwd() #get current working directory
os.chdir("myfolder") #change directory
os.path.exists("myfile.txt") #check if file exists
```

## Exel Module

```python
import openpyxl
import math

wb = openpyxl.Workbook()

sheet = wb.active
sheet.title = "myTable"  #select and name tatable
x, y = 1, 1

for i in range(-31, 31):
    sheet.cell(row=y, column=x).value = math.sin(i / 10)  #write into field
    y += 1

wb.save("table.xlsx")  #safe file
```

## Zip Module

```python
import zipfile as zf
from os import system as cmd

# zip a file
def zip(file):
    zf.ZipFile(file + ".zip", "w").write(file)
    cmd("rm -rf " + file)

#unzip a file
def unzip(file):
    zf.ZipFile(file).extractall()
    cmd("rm -fr " + file)

#backup a folder to a zip file
def backup(folder):
    zf.ZipFile(folder+".zip", "w").write(folder)
```

## yaml Module

read data from a .yml file

```python
import yaml

with open('config.yml', 'r') as file:
    yaml_file = yaml.safe_load(file)

print(yaml_file['prime_numbers'][0])
print(yaml_file['rest']['url'])
```

```yaml
rest:
  url: "https://example.org/primenumbers/v1"
  port: 8443
prime_numbers: [2, 3, 5, 7, 11, 13, 17, 19]
```

## Selenium Module

automate web browser

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from os import system as cmd


driver = webdriver.Firefox() #open browser
driver.get("https://www.google.com") #open url

tag_name = driver.find_elements(by=By.TAG_NAME, value="a") #find all elements with tag name a
class_names = driver.find_elements(by=By.CLASS_NAME, value="myclass") #find all elements with class name myclass
id_name = driver.find_elements(by=By.ID, value="myid") #find element with id myid


element = tag_name[0] #select first element
element.click() #click element
inner_html_text = element.text #get text inside a tag
href = element.get_attribute("href") #get attribute value

driver.close() #close browser
cmd("pkill firefox") #close all firefox instances
```

## Pyautogui Module

```python
import pyautogui as bot

#only needed if you want to use the mouse
size = bot.size()
width = size[0]
height = size[1]

# left click
bot.click("left")

# right click
bot.click("right")

# drag from (0, 0) to (100, 100) relatively with a duration of 0.1s
bot.drag(0, 0, 100, 100, absolute=False, duration=0.1)


bot.press("enter")
bot.press("space")
bot.keyUp("shift")
bot.keyDown("shift")
bot.write("Hello world!", interval=0.25) #write text with 0.25 seconds delay between each key
```
