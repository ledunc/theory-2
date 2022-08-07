# theory-2
## Specialisation Theory Assignment 
### 1. How does Object Oriented Programming differ from Process Oriented Programming? (10 marks)
Object oriented programming (OOP) uses concepts of objects and classes. A class is like the back-bone of the program where objects can be created into it.
Objects contain member variables which contains the behaviour and identifiable characteristics. The behaviour of the object is what it can do and the characteristics are the objects attributes.
Using a class example of a dog, the class is the template for a specific object, `my_dog`; a behaviour dogs can do is `'bark'`, this is called a method, attributes all dogs have are `'name'`, `'age'` and `'breed'`
```
# create the Dog class by calling class and initialising the attributes and methods into the class
class Dog:
    # attributes which are 
    def __init__(self, name, age, breed):
        self.name = name
        self.age = age
        self.breed = breed
    
    # bark is the method
    def bark(self):
        print(f"{name} says woof!")
        

# my_dog is the object which is the instance of a class. A specific dog
my_dog = Dog('Teddy', '11', 'Cocker Spaniel')
```
Process Oriented Programming (POP) uses concepts of calling procedures. Procedures are a set of computational instructions which can be descried as functions, these functions can be called anytime during the programs' execution.
An example of POP that adds all numbers together in a list:
```
# define a function that adds integer elements in a list
def add_nums_in_list(any_list):
    sum = 0
    for i in any_list:
        sum += i
    return sum

# defines the parameter
my_list = [1, 2, 3, 4, 5]

print(add_nums_in_list(my_list)) # returns 15
```
The differences between OOP and POP are shown in the table below

| Process Oriented Programming                                                           | Object Oriented Programming                                                                              |
|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| Program is separated into chunks called *functions*                                    | Program is separated into small parts called *objects* which are instances of classes                    |
| Program reads the code from top to bottom and executes in that order                   | OOP uses a bottom up execution approach where the object is executed first and is populated by the class |
| POP is not designed for code re-usability because functions are very specific          | OOP is designed for code re-usability ie. classes                                                        |
| Languages used in POP are FORTRAN, ALGOL, COBOL, BASIC, Pascal and C                   | Languages uses in OOP are Java, C++, C#, Python, PHP, Ruby and Swift to name a few                       |
| Uses the concept of procedure abstraction                                              | Uses the concept of data abstraction                                                                     |
| Useful for small to medium sized programs, struggles with larger more complex programs | Suitable for large and complex programs                                                                  |
| Doesn't use data hiding so is less secure than OOP                                     | Uses inheritance and data hiding - more secure                                                           |
| Overloading is not possible in POP                                                     | Overloading is possible in OOP                                                                           |
| Difficult to add new data and functions                                                | Adding new data and functions is easy                                                                    |
| Has no access specifier                                                                | Has an access specifier such as private, public and protected                                            |
| The function is more important than the data in POP                                    | The data is more important than the function                                                             |
        
### 2. What's polymorphism in OOP? (10 marks)
Polymophism in programming means that a method/ operator or object can perform differently in different scenarios. An example of this is the `len()` function:
```
# string data type
len("hippopotamus") # 12 characters in the string

# list data type
len(["tea", "coffee", "hot chocolate"]) # 3 items in the list

# dictionary data type
len({"Film": "Kung Fu Panda", "Rating": 5}) # 2 items in the dictionary
```
Another example is the `+` operator: this works with integers adding them together, or strings concatenating them.
```
# integers
sum = 5 + 3 # the sum is 8 

# strings
message = 'Hello ' + 'World' # 'Hello World'
```
In terms of OOP polymorphism is an important concept that allows classes to use methods with the same name as a different class.
An example is a `Cat` and `Dog` classes have a `name` and `age` but make a different `sound`.
```
class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def __str__(self, name, age):
        return f"{self.name} a cat, who is {self.age} years old"
        
    def sound(self)
        return "Meow!"
        
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def __str__(self, name, age):
        return f"{self.name} a dog, who is {self.age} years old"
        
    def sound(self)
        return "Woof!"
        
their_cat = Cat("Winston", 3)
their_dog = Dog("Odin", 12)

for animal in (their_cat, their_dog):
    animal.sound()
    animal.__init__()

# same methods __init and noise() but the methods are not linked, but we can iterate through them with 'animal' variable to get them to produce the associated sounds for a cat and dog
```
Two types of polymorphism can occur: overloading and overriding.
Overloading is not possible in Python but is a way to create multiple methods with same name but different arguments; this can be achieved in Java however.
**Overriding** the methods and attributes in a parent class to specifically fit the child class is due to inheritance.
An example of overriding is if the parent class is `Shape` and there are subclasses for different shapes such as a `Rectangle` and `Triangle`.
```
class Shape:
    def __init__(self, name):
        self.name = name
        
    def area(self):
        pass
    
    def sides(self)
        return "Common shapes have 1 to 9 sides"
    
class Rectangle(Shape):
    def __init__(self, width, height):
        super().__init__("Rectangle")
        self.width = width
        self.height - height
    
    def area(self):
        return self.width * self.height
    
    def sides(self)
        return "A rectangle has 4 sides, of 2 different lengths"

shape_1 = Rectangle(5, 3)
print(shape_1.sides)

# Rectangle (child) overrides Shape (parent) class with method, sides
```


### 3. What's inheritance in OOP? (10 marks)
In inheritance, there is a parent class and a child class in which the child inherits all the methods adn properties from the parent class. It can also be called the class (parent) and the subclass (child) or base class (parent) and derived class (child).
The child class also allows the programmer to create more methods specific to the child class. Inheritance is useful in programming because it makes the code more reusable and obeys the software principles DRY "Don't Repeat Yourself" and KISS "Keep it Simple Stupid".
In this example the `Vehicle` class has `wheels` and makes a `noise`. The `Car` class inherits from this using `super()`, a car has 4 `wheels` and makes a `"beep"` sound. The method exclusive to cars is using the `handbrake`. The `my_car` is able to `move` using the inherited method from `Vehicle`.
```
class Vehicle:
    def __init__(self, wheels, noise):
        self.wheels = wheels
        self.noise = noise
        
    def move(self, distance):
        return f"The vehicle moved {self.distance} forward"
    
    def noise(self):
        return f"The vehicle went {self.noise}"

class Car(Vehicle):
    def __init__(self, wheels, noise):
        super().__init__(self, 4, "beep")
    
    def handbrake(self):
        return f"{Car} put on its handbrake"

my_car = Car(4, "beep") 
my_car.move(4) # inherits move from parent class Vehicle
my_car.handbrake() # new method specific to a car
```

### 4. If you had to make a program that could vote for the top three funniest people in the office, how would you do that? How would you make it possible to vote on those people? (10 marks)
I would use python and Flask to create a survey to ask the staff members who they thought was the funniest with all the names drop-down menu where they can choose their answers. This would be submitted through a form so would be a POST method in Flask.
I would then connect the Python file to a SQL database which would collect all the votes of the people as they were posted from the python Flask application. 
I would import `mysql.connector` in Pycharm and create a function to connect to the SQL database.
Once the voting period (1 week max) is over I can perform an action in mySQL to retrieve the top 3 funniest people.
My database would look similar to this:

| Name                | Funniest |
|---------------------|----------|
| John Appleseed      | 1        |
| Katie Pinecone      | 1        |
| Elizabeth Margarine | 0        |
| Victoria Sponge     | 1        |
| Katie Pinecone      | 1        |

Since there may lots employees in the office I would make an index on `Name`.
I would make sure to `GROUPBY Name` first then refine the criteria in the database to `HAVING` `SUM(Funniest)` to work out the total amount of votes for each person. Then finally `LIMIT = 3` to select the top funniest 3 people.
Based on my table Katie Pinecone, John Appleseed and Victoria Sponge are the funniest people in the office.

### 5. What's the software development life cycle? (10 marks)
<img width="440" alt="SLDC" src="https://user-images.githubusercontent.com/102866922/183299101-66e9c68d-aaba-4fb4-bb42-28b33e7131d1.png">

The Software Development Life Cycle (SDLC) is a cyclic process which shows steps that explain how software development goes from an idea to delivery of a customer product.
The development cycle is never-ending because updates containing bug fixes and additional features are inevitable.

The **planning** stage (1) involves production management (material resource allocation, capacity planning, provisioning, procurement requirements) and project management (human resource allocation, project scheduling and cost estimation). 
This is done with collaboration with operations and security teams, working together to ensure nothing is missed.

Stage 2 is where the **requirements** of the software is drawn up. The business stakeholders and subject-matter experts come up with the requirements of what the software should do nd how it should perform then business communicates these requirements for new development and enhancement with IT. 
Architects, development teams and product managers work with the experts to document the processes that must be automated in software. In the SDLC the requirements stage can be done in Agile or Waterfall. If the output is in a Waterfall project then a document is drawn up that lists these requirements. In Agile produces a backlog of tasks that need to be performed.
Requirements use different capturing techniques and is split into 2 categories: visual and functional. Visual techniques include wireframe and blueprints whereas functional techniques use a manual example document or the AS/ WHEN/ THEN method. An example of how to complete the AS/ WHEN/ THEN technique is AS (a role), WHEN (action) then (result).

Step 3 of the SDLC is the **design** phase. Based on the decided requirements of the software, the architects and develops start to design it. The process used to design involves patterns for application architecture and software development.
Design patterns solve algorithmic problems consistently and rapid prototyping called spike helps to compare solutions to find the optimal choice.
Whiteboard sessions outline the system flow and architecture and produces valuable design documents that list the patterns and components for the project and the code produced by spikes.
A very simple architecture diagram looks like this:

<img width="452" alt="theory-diagram" src="https://user-images.githubusercontent.com/102866922/183299042-cd24cd37-8851-4c80-a12e-4bfb6e4fa83f.png">

Step 4 of the SDLC involves **implementation** of the software under development to produce working software quickly. There are 2 methods that can be used to implement the software, either Agile or Waterfall. At the end of this phase there should be a testable, functional software. To ensure the business stakeholders expectations are met, they should regularly attend meetings.
The implementing stage can be done in Agile or Waterfall. If it is completed in time-boxed sprints (usually lasting 1 or 2 weeks) that is an Agile method, if it is done all at once in a single block of effort that's Waterfall.

Step 5 is the **testing** phase which is one of the most important aspects of the SDLC because it's very difficult to deliver quality without rigorous testing. 

Tests to measure quality:
* Code quality
* Unit testing
* Integration testing
* Performance testing
* Security testing

The best way to make sure these tests are run regularly is to automate them. The output of this phase is functional software which is ready to be deployed in a production environment.

Step 6 is the **deployment** phase and in an ideal world is completely automated. Depending on the experience of the business this can be a very instant process or will take longer as manual approvals are required. In a continuous development business model the deployment should be fully automated.
To actually automate the deployment of applications to the production environment Application Release Automation (ARA) tools are used and are usually integrated continuously. At the end of phase 6 the product should be released as working software.

Step 7 is the **maintenance phase** this isn't actually the last phase because the SDLC will continue but the software must be monitored closely for proper operation.
Bugs and defects that have been discovered when the software is in production should be reported and responded to and this re-enters the SDLC to go through the process again, this is to ensure that regression doesn't occur which is when the bug-fix doesn't cause other problems.

### 6. What's the difference between agile and waterfall? (10 marks)
A Waterfall approach in SDLC is shown below, and is a cascade SDLC model that flows through the phases step by step. This method shows the gradual execution of each stage completely and is strictly documented with predefined features at every phase.

<img width="737" alt="waterfall" src="https://user-images.githubusercontent.com/102866922/183299197-fb05f30a-fec4-4d06-899f-dc89bb957db3.png">

Key features of Waterfall in SDLC:
* Requirements are documented
* Product definition is stable
* Predefined technologies stack - static
* No ambiguous requirements
* For short duration projects

An Agile approach in SDLC is shown below, it is a dynamic process where the customer can review the result at each stage of the process and change things depending on whether they are satisfied or not. This is a key advantage in the SDLC process because the customer is always kept in the loop and happy.
A disadvantage of the Agile approach is that there is absence of defined requirements (unlike Waterfall) therefore it becomes difficult to estimate the resources and costs associated.
The practical uses of the Agile model is extreme programming and are done in short weekly meetings in 'sprints' which is part of the Scrum.

<img width="604" alt="agile" src="https://user-images.githubusercontent.com/102866922/183299180-4044fbeb-50fa-4390-aa02-c8e2d869ccf6.png">

Key features of Agile in SDLC:
* The customers' needs change dynamically
* Many iterations of the same process means smaller costs for changes.
* Only requires initial planning to start the project (unlike Waterfall)

### 7. What is a reduced function used for? (10 marks)
`reduce()` is used on iterables (`list`, `str`, `tuple`, `dict` and any objects defined with an `__iter__()` method) to **reduce** it to a single cumulative value, this is also known as folding.
It is part of the `functools` module in Python 3.0.
A coding example of this using `lambda` functions is shown below and is cumulated from left to right.
```
from functools import reduce 
reduce(lambda a, b: a + b, [0, 1, 2, 3])
# will return (((0 + 1) + 2) + 3) = 6 'a' is the accumulated value and b is the next value in the iterable```
```
It follows the process of:
* The first 2 elements in the sequence are chosen and result is calculated (eg. a = 0, b = 1, a + b = 1)
* Next the previous result becomes the first element in the sequence again and the next item in the sequence becomes the second and the result is obtained (eg. a = (0 + 1) = 1, b = 2, a + b = 3)
* This process continues until there are no more elements left in the sequence (eg. a = 3, b = 3, a + b = 6)
* The final result is returned (eg. 6)

The similarities and differences between`reduce()` and `accumulate()` are shown in the table below:

| reduce()                                                                                  | accumulate()                                                                                |
|-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| functools module                                                                          | itertools module                                                                            |
| stores intermediate results and returns only final result eg. 6                           | returns an iterator containing intermediate result eg. [0, 1, 3, 6, 6]                      |
| uses iterables                                                                            | uses iterables                                                                              |
| reduce(function, sequence) takes function argument first then the sequence                | accumulate(sequence, function) takes sequence as first argument then function as the second |
| can take 3 arguments an optional 'initialiser' which will return if the iterable is empty | can take 3 arguments an optional 'initialiser' which will return if the iterable is empty   |

### 8. How does merge sort work (10 marks)
Merge sort is a divide-and-conquer type sorting algorithm. It works by **dividing** the unsorted list until there are N sublists (where N is the number of elements in the original array). In each sublists there is 1 element that is unsorted. **Conquer** repeatedly merges 2 sublists together at a timme to produce a new sorted sublist and continues until all elements are fully merged into a sorted array.

Unsorted array [2, 4, 5, 1, 3]

Dividing into N = 6 sublists [2] [4] [5] [1] [3] [6]

Merge sublists together 2 at a time to produce sorted sublists [**2**] [**4**] [5] [1] [3] [6] &rarr; [2, 4] [5] [1] [3] [6]

Repeat [2, 4] [**5**] [**1**] [3] [6] &rarr; [2, 4] [1, 5] [3] [6]

Repeat [2, 4] [1, 5] [**3**] [**6**] &rarr; [2, 4] [1, 5] [3, 6]

Merge into N/3 = 2 sorted sublists [**2**, 4, **1**] [5, 3, 6] &rarr; [1, 2, 4] [5, 3, 6]

Repeat [1, 2, 4] [**5**, **3**, 6] &rarr; [1, 2, 4] [3, 5, 6]

Merge into 1 sorted list [**1**, **2**, 4] [3, 5, 6] &rarr; [1, 2, 4] [3 , 5, 6]

Repeat [1, 2, **4**] [**3** , 5, 6] &rarr; [1, 2, 3, 4] [5, 6]

Repeat [1, 2, 3, 4] [**5**, **6**] &rarr; [1, 2, 3, 4, 5, 6]

A code example of solving an unsorted list (array) using a merge sort method is seen below
```
def merge_sort(arr):
    # The last array split
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    # Perform merge_sort recursively on both halves
    left, right = merge_sort(arr[:mid]), merge_sort(arr[mid:])

    # Merge each side together
    return merge(left, right, arr.copy())


# helper function
def merge(left, right, merged):
    left_cursor, right_cursor = 0, 0
    while left_cursor < len(left) and right_cursor < len(right):

        # Sort each one and place into the result
        if left[left_cursor] <= right[right_cursor]:
            merged[left_cursor + right_cursor] = left[left_cursor]
            left_cursor += 1
        else:
            merged[left_cursor + right_cursor] = right[right_cursor]
            right_cursor += 1

    for left_cursor in range(left_cursor, len(left)):
        merged[left_cursor + right_cursor] = left[left_cursor]

    for right_cursor in range(right_cursor, len(right)):
        merged[left_cursor + right_cursor] = right[right_cursor]

    return merged
```

### 9. Generators - Generator functions allow you to declare a function that behaves like an iterator, i.e. it can be used in a for loop. What is the use case? (10 marks)
Generators are similar to iterators but more elegant, they can achieve the same thing essentially but without `iter()` and `next()` methods in the class.
Generators use the `yield`, normal functions use the `return` keyword instead, but this is the only difference. `yield` also works the same as `return` but remembers the state of the function, whereas `return` does not.

The differences between iterators and generators are shown in the table below

| Iterators                                                | Generators                                                       |
|----------------------------------------------------------|------------------------------------------------------------------|
| Serves as a holder for objects that can be iterated over | Facilitates the creation of a custom iterator                    |
| Uses a class                                             | Uses a function                                                  |
| Not always a generator                                   | Is always an iterator                                            |
| Doesn't use yield                                        | Uses yield keyword                                               |
| Not as concise code as using generators                  | Results in very concise code                                     |
| No local variables are used                              | All local variables before the yield statement are stored by it. |

An example of a generator and how it works is shown below:
```
def my_generator():
    n = 2
    print('This is printed first')

# generator function contains yield statements
    yield n

    n += 1
    print('This is printed second')
    yield n

    n += 1
    print('this is printed last')
    yield n

g = my_generator()
print(next(g)) # 'This is printed first' 2 
print(next(g)) # 'This is printed second' 3 
print(next(g)) # 'This is printed last' 4 

# since all generators are iterators the next() property can be used to iterate through the next values
```
The use case of generators are to allow the programmer to declare a function that behaves like an iterator in a very fast way with clear code. They are particularly useful when working with a large data set.

### 10. Decorators - A page for useful (or potentially abusive?) decorator ideas. What is the return type of the decorator? (10 marks)
Decorators are functions which take another function as an argument and returns the modified version of initial function by enhancing the functionality in some way. Decorators are called with an `@` symbol before the same of the decorator and is used to *decorate* functions.
Functions support all the operations that are generally available to other entities - they act as 'First-Class Citizens' in Python. 

The advantages of a decorator are:
* can use them to pass other functions as **arguments** 
* can return them from other functions as **values**
* can **store** them in variables and data structures

An example of a decorator used to protect another function is shown below, it will only show my favourite colour as `'pink'` if my name is correctly entered.
```
def only_allow_if_name_is_lydia(func):
    def guarded_function():
        name = input("Stop! What is your name? ")
        if name == 'Lydia':
            func()
        else:
            print("Sorry access denied")
    return guarded_function

@only_allow_if_name_is_lydia
def print_fav_colour():
    print('pink')
    
print_fav_colour() # this will perform the guarded function first because the @only_allow_if_name_is_lydia is a decorator of the print_fav_colour function
```
The disadvantages of decorators is that it can be potentially abusive an example is as follows:
```
my_abusive_list = []

@my_abusive_list.append
def some_function():
    pass

# this case uses a list method (.append) inside calling the decorator, this is not very good practice
```
