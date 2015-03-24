# Java-211
Programs written for my Java Object-Oriented Program class

These are the assignments given:

Assignment 1:
Part a)

Create a class called MyDegree. It should have two variables of type double. One called fahrenheit and the other celsius. It should have one constructor that takes in two variables, the first of type double the second of type String. Depending on the value of the String parameter (which should be either fahrenheit or celsius) set the corresponding variable to the value passed as a parameter. Compute the value for the other variable. (Hint: Fahrenheit to Celsius: f = (9/5)*c +32, Celsius to Fahrenheit: c = (5/9)*(f-32). Create 2 get methods, one for each variable. Create 2 set methods, one for each variable (don’t forget to change the other variable from within each set method).

Part b)

Create a class called MyDate. It should have 3 variables of type int: named date, month, and year. It should have 2 variables of type MyDegree: named high and low. Create a constructor that takes in 3 parameters of type int. The constructor should call method isValid and pass it all three parameters. If the 3 parameter were all valid values, they should be set to the date month and year variables. If the isValid method returns false, some default date should be used instead (you choose what the default date value should be). If the default date was used, a JOptionPane message dialog box should be used to alert the user that the entered date was invalid and which date was used instead. Create a method isValid that will verify if the values passed are a valid date. Create set methods for the high and low variables. These 2 set methods should each take in 2 parameters, those 2 parameters should be passed to the constructor of class MyDegree and the resulting object created should be set to the variable (high or low). Create get methods for all 5 variables. The get methods for high and low should not return the MyDegree object, but instead should return the degree value of that object as an int. (Make sure to convert it to an int)

Part c)

Create a class called main which has a main method within it. The main class should ask the user through JOptionPane objects for a date, month, and year. Use 3 JOptionPane objects. Create a MyDate object. Using the get methods of MyDate, verify with the user (using a Confirm Dialog box (a method within JOptionPane) that the MyDate object has the correct date. Remeber, you must get the values from the MyDate object and not use the variables that were passed to the MyDate constructor, since, if the date was not valid, a default date was used instead. If the user clicks the NO button, the user should be asked for another date using JOptionPanes. HINT: use a while loop.  If the user clicks the YES button, the MyDate object should be stored in an array of type Mydate. HINT: create the array outside (ie. before) the while loop, otherwise it will become "out of scope" (ie. cease to exist) after the while loop. Create 4 more MyDate objects for the next 4 days in the calendar. HINT: use the isValid method from class MyDate to determine if these next dates are valid (for example, if the 1st date is June 30th, the 2nd date should be July 1st, not June 31st). Store these other MyDate objects in the array. Then, from within this main method, use the set methods of class MyDate to set the high and low variables. Make up values. Do not try to look up the high and low temperatures of those days. Lastly, print out to the console the high and low temperatures for all 5 days in Fahrenheit and then print out the high and low temperatures in Celsius.

an example output should look like this:

Fahrenheit:

6/30/14 high 84 low 69

7/1/14 high 82 low 61

...

Celsius:

6/30/14 high .... etc.

----------------------------------------------------------------------------------------------
Assignment 2:

Create an object called GSSArray. (it stands for growable self-sorting array)

This object will manage an array of type int.
Create a private variable for an array of type int.
In the constructor for this object, take in an int value which will determine the starting size of the array.
The constructor should also instantiate the array.

Create a public method called insert, which will take in an int and find the location in the array where it belongs and insert it there.
If the array is full, then before inserting the value, method insert should call private method increaseSize, which will create a new array which is double the size of the current array. Then it will copy the values from the original array into the new array and set the private variable to this new array.

The array should keep track of how many of its indexes are filled. Create a private variable called lastindex which will be equal to the last index of the array that has a value.

Create a public method delete, which will take an int and if will remove the 1st instance of that number in the array. If the number doesn't exist, the method should return false, otherwise it should return true. (Don't forget to update variable lastindex in methods delete and insert.)
----------------------------------------------------------------------------------------------
Assignment 3:
Add the following 2 methods to the LinkedList2 class that we created last week:

find and delete

The find method should take in an integer value and return the 1st Node object in the list that has that value. If there is not a Node object with that value, a new Node object should be ceated with a negative value and that new Node should be returned instead.

The delete method perform that same task as the delete method in the original LinkedList class

----------------------------------------------------------------------------------------------
Assignment 4:

part a)

Create 2 classes, DynamicStack and DynamicQueue, both of which will inherit from class LinkedList that we created together in class. (It is posted here on blackboard)
Here is what you I want you to do:
In LinkedList:
1) add a variable of type int called count, which will keep track of how many nodes are in the list.
2) make both variables count and head protected scope

****For DynamicStack and DynamicQueue , the order is based on the order in which they were added. These lists should not be sorted based on any value.
Therefore, the insert and delete methods must be overridden.
In both DynamicStack and DynamicQueue :
1)Create one constructor that takes in a parameter of type int.
   The constructor should create a node with that int, and have the head variable point to it.
2)Create a method to override the parent classes insert method
3) Create a method to override the parent classes delete method.  **** Note: see bottom****
4) Remember to update the count variable in all 3 of these methods.
5) Create method clearAll in both classes. The method should look at the node at the top or front and print out to the console its int value, and then delete that node from the list, calling method delete. Continue printing and deleting until the structure (stack or queue) is empty. Use the count variable to determine when the structure is empty.

For class DynamicStack, the head variable should point to the node at the top of the stack.
For class DynamicQueue, the head variable should point to the node at the front of the queue. In addition, I recommend that you have a variable called "back" or "last" to point to the last node in the list.



****Note 1****
The delete method in class LinkedList took in an int as a parameter. In order for the children classes to override the parent classes' method, the method signature must match EXACTLY, including the parameter list. Therefore, the delete method of the children classes must take in an int value. The int taken as a parameter is NOT the value of the node to be deleted, since only one node could possibly be deleted in these structures (either the top or the front). Instead the int value is the number of nodes that should be deleted from the stack or queue. If the int passes as a parameter is greater than the number of nodes in the list, then the list should be completely emptied. Be careful to avoid null pointer exceptions.

****Note 2****

If all of the Nodes are removed from the list, then the head pointer will point to null. If you then try to insert a Node, you will cause a NullPointerException. Therefore, you must check if head is null before calling any methods on it.

part b)

Create 2 classes, StaticStack and StaticQueue, both of which will inherit from class GSSArray that you created in assignment 2.

For this part of the assignment, I am leaving it up to you to determine what variables you need for these classes. You also are to determine if you want to use the variables of the parent class or redefine them in this class. 

Create a constructor that calls the parent class's constructor.

Methods insert and delete have to be overridden for the same reason as in part a. Just like in part a, The delete method should delete as many values as the paramter passed to it and the insert method should insert the parameter passed either at the front or on top (depending on if it is class StaticStack or StaticQueue)

Do not override method increaseSize.

Create a method clearAll() that will look at the location at the top or front and print out to the console its int value, and then delete that value from the list, calling method delete. Continue printing and deleting until the structure (stack or queue) is empty.  

HINT:

for the queue, use a variable to keep track of which index is the front of the queue and another variable for the back of the queue. Otherwise, you will have to perform a lot of shifting.

part c)

Create an instance method called print() in each of your 4 classes. The method should print out to the console all of the int values, in order
I want you to create a main method in another class called Assignment4.
The main method should create an instance of each of your 4 new classes. Their starting size for the StaticQueue and StaticStack should be 4.

For each structure:

Insert the numbers: 18, 3, 7, 36, 9, 14

call method delete 2 times

Then call method clearAll()

Insert the number 1.

After each method call, call method print (how else could you know if the code is doing what it is suppossed to do)

Then call method clearAll from both the queue and the stack.

----------------------------------------------------------------------------------------------
Assignment 5:

1) Inheritance: You must determine what should be abstract, what should be inherited, and what should be overridden (Hint: I am expecting at least one abstract method in this assignment, which means at least one abstract class)
a) Create class Shape. The class should have a variable for the shape's area and perimeter. There should also be methods to "get" these variables. Also create a method called calculate, whose purpose is to calculate the appropriate values for both of these variable and then set them (do not create a "set" method for these variables). 
b) Create classes Circle, Rectangle, and RightTriangle that each will inherit from class Shape, and class Square, decide if class Square should inherit from class Rectangle or class Shape. Include whatever additional variables that are appropriate to each of these shapes.
Create method bodies for any abstract methods that might have been inherited.
c) The constructors for these objects must take in some int value (which will determine the size of the shape). If that parameter (or parameters) are not positive (zero or negative), throw an IllegalNegativeArgumentException. (see part d). The String passed to the constructor of the exception class should be a meaningful description of the context in which the exception is being thrown.
d) Create class IllegalNegativeArgumentException, which should inherit from IllegalArgumentException. 
e) Create method resetDimensions in each of these classes (hint, rely on inheritance). The method does not take in any parameters. It should generate a JOptionPane to ask the user what the new value (or values) should be for the variable (or variables) that determine the size of this object. Put the line of code that would convert the string into an int in a try/catch block to catch for a NumberFormatException. In the same try block, throw an IllegalNegativeArgumentExcpetion if the value is not positive. Catch here for this Exception too, but not in the same catch block that the NumberFormatException was caught. If either Exception is thrown, do not change the value (or values) of the variables. Do not ask the user to input again a new value. A JOptionPane should be created to inform the user of the type of error made in his input, and that no changes were made.
f) Create another class that has only a main method, call this class Assignment5. This method should create an array of type Shape, with room for 10 shape objects. Fill the array with a variety (at least one of each of the 4) of Shape objects. Then, loop through the array, calling calculate on each of the shape objects. Rely on polymorphism, do not determine what each object type is. Output (to the console or with a JOptionPane) the average area of all 10 shapes

----------------------------------------------------------------------------------------------
Assignment 6

Using your solution from assignment 5, instead of using the built in GUI class, JOptionPane, you are to create and use your own GUI class. In the last assignment, you were to use both methods showInputDialog and showMessageDialog. For this assignment, your GUI class (or 2 classes if you prefer) should be able to create similar GUI objects with similar functionality as these 2 methods of JOptionPane. 

Make sure you resubmit all of your classes from assignment 5 in addition to whatever new classes you create for this assignment.

----------------------------------------------------------------------------------------------
Assignment 7

A)

1)

a) create a method called sum in class Node (any of the Node classes that we have created), that will recursively calculate the sum of all of the int data values from that node to the last node in the list. (HINT: using the next pointer) This method should return (NOT PRINT OUT) the sum that was calculated.

b) IN CLASS LINKED LIST, create a method called sum that will take an int, n, as a parameter. It will call method sum (of class Node) on the nth node in the list. (the head is node 1, the node after head is 2, etc.) And then print out to a file the sum that was calculated. If the parameter passed is negative or zero, then the sum should be zero. If n is greater than the number of nodes in the list, then throw an appropriate exception.

2)

a) create a method called printBackwards in the same Node class. The method should take as a parameter an object of type PrintWriter. It should be a recursive method. The purpose of the method is to print all of the values from all of the nodes from the current node (as in the this  keyword) until the end of the list IN BACKWARDS ORDER. In other words, the last node in the list will appear at the beginning of the output text file, and the current node will appear later in the text file. 

b) create a method printB in the same LinkedList class. The method should create an instance of PrintWriter and call the method printBackwards from class Node. 

MAKE SURE that you use different output files for part 1 and part 2.

B) Using class Shape that you created from assignment 5. Change class Shape to implent the interface Comparable. The Shape objects should be compared based on their areas. Make sure to use the Generic Comparable.

C) Create a main class called Assignment 7. The main method should read from the file that is attached to this assignment. The main method should create a new LinkedList Object, using the number 6 as the value passed to the constructor. Then the main method should read from the file and for each numeric value read it should add that number to the list. Then the method should call methods sum and printB of class LinkedList.
