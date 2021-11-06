# 1 - What is JavaScript?

###### tags: `apcsp txt` `cs`

> *Any sufficiently advanced technology is indistinguishable from magic.*
>
> *--Arthur C. Clarke*

## 1.1 What is a Computer Program?

Everyday you interact with computers.  If you use your cell phone, ride in a car, use a microwave, swipe a credit card, or, of course, use a computer to word process a paper, you are interacting with a computer.  Nearly every aspect of our lives from the clothes we wear to the food we eat, from medical treatments to sporting events, typically involve and sometimes depend on computers.

We have all told computers what to do, in the sense of telling our phones who to call or what music to play or telling our cars how fast to go, but in each of those cases we are really interacting with a program that is designed to listen for precisely the kind of thing you are telling it and nothing else.  The computers in your car, for instance, don't know how to make coffee, and the computers in the machines that made the fabric in your clothes, don't know how to stream your favorite music. But the computer in your coffee maker and one of the computers in your car may in fact be very similar computers with very similar capacities, but what is different is the program that they are running.

A computer program is a set of instructions that the computer must follow.  Without a program, a computer just sits and does nothing.  When you run an app on your phone, you are choosing to run a program.  Where to the programs come from? Programmers write them and that is what you will learn how to do in this course.

People write programs using vocabulary (commands) and grammar (syntax) that makes sense to people.  Just like there are different human languages in the world, there are different computer languages that can be used to write programs, each having their own commands and syntax.  In this course, we will study a language called JavaScript, also known as ECMAScript.  

Our computers though, don't know JavaScript or any other human language.  Computers really are sets millions of carefully arranged [switches (transistors)](http://www.explainthatstuff.com/howtransistorswork.html).  Switches can be either on or off. One or more switches can be connected to other switches to turn them on or off.  By creatively configuring these switches, computer scientists have found ways of getting them to do mathematical calculations like adding.  Furthermore, they have found ways of getting them to do logical calculations, such as `IF A > B, then do C`.  

If you are interested in the guts of a computer, that is, how it physically works, watch the [Crash Course Computer Science series](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo) episodes, especially 1 thru 8.  They are only about 10 minutes each so you could easily binge them on a weekend.  Specific episodes will be noted throughout this text.  While they cover topics not required for this course, they do provide useful background that can help you better understand what is going on.

> *In one sense a computer is only the transistors and the connections between them, but describing it like this loses something in the process. You can't really understand the computer unless you understand its functional relationships, what it's trying to accomplish, and the purpose that it serves to its human creators.*
>
> *--Bill Newsome*

Using the building blocks of mathematical and logical calculations, computer scientists have found ways to get switches to do amazing things, but since it all comes down to switches being on or off, we have to program computers in on's and off's.  We often call these on's and off's 1 and 0 and refer to them as [**binary**](https://learn.sparkfun.com/tutorials/binary) language.

![Translating a High Level Language Into Binary](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/languagelevels.png "Translating to Binary")

We will write programs in JavaScript using English words and mathematical symbols that we are familiar with. JavaScript is called a high level language since it is far removed from the actual 1's and 0's. Our JavaScript program will be handed off to another program that turns it into binary for the computer to actually execute.  In JavaScript, this conversion program is called an [*interpreter*](http://voidcanvas.com/is-javascript-really-interpreted-or-compiled-language/).  In other languages, it may be called a *compiler*, as in the diagram above.  For more information on this whole process, there's a wide ranging but very interesting article on coding/programming by Paul Ford [here](http://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/#grabbag). Chapter 2 of the article is the most relevant part.  You can also watch [Crash Course Computer Science episode 11](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/dilbert1.png" width="100%" alt="Dilbert - Scott Adams - Universal Features Syndicate, Inc. 1992" hover="Dilbert - Scott Adams - Universal Features Syndicate, Inc. 1992">

While we can do a ton of programming in high level languages like JavaScript without using any binary math, we should still be familiar with the basics. Even though in binary we only have 2 digits, we can still count just as well as if we had 10, by using place value.  Just like we can count higher than 10 even though we only have 10 digits in our normal decimals system, we can count higher than 2 in binary.  Consider the table below:

| Decimal | Binary | Hex  |
| ------- | ------ | ---- |
| 00      | 00000  | 00   |
| 01      | 00001  | 01   |
| 02      | 00010  | 02   |
| 03      | 00011  | 03   |
| 04      | 00100  | 04   |
| 05      | 00101  | 05   |
| 06      | 00110  | 06   |
| 07      | 00111  | 07   |
| 08      | 01000  | 08   |
| 09      | 01001  | 09   |
| 10      | 01010  | 0A   |
| 11      | 01011  | 0B   |
| 12      | 01100  | 0C   |
| 13      | 01101  | 0D   |
| 14      | 01110  | 0E   |
| 15      | 01111  | 0F   |
| 16      | 10000  | 10   |
| 17      | 10001  | 11   |

Leading zeros have been included to emphasize place value.  Decimal is how we count if we have 10 digits (0 - 9).  We probably adopted this pattern since we have 10 fingers, but note that we don't use one of our fingers for zero. This subtle difference between counting on our fingers and zero being one of our digits causes some problems later in the course. Binary is how we would count if we only had 2 digits.  Can you see that we move over to the left in place value when we run out of digits on the right, just like in the decimal system?  Then we just keep doing the pattern over and over again. Hex (or hexadecimal) has been included to show that we can use this counting pattern for any number of digits.  In hex, we have 16 digits (0 - F).  Hex is most commonly used to conveniently represent binary values that are less than 111111 or 255 in decimal, since in hex they would only require 2 digits: 111111 (binary) = FF (hex).  For instance you may have seen yellow represented in a paint program as FFFF00, which is hex, or a when setting up a cable modem or a cell phone you may have had to enter a device address like 9BD6735E-C14D-5D06-9155-CEB0D46C26FC, these are typically hex as well.  All this to say that counting with 2 digits (binary) just follows the same pattern as counting with 10 digits or 16.

> *There are 10 kinds of people in the world: those who know binary and those who don't.*
>
> *--Anonymous*

Take a look at [Crash Course Computer Science episode 4](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo) to better understand binary math.

## 1.2 Writing a Computer Program

> **TARGET**: Be able to use the Repl.it IDE to write and run simple JavaScript programs.

Follow your teacher's instructions and login to Repl.it and enter the CS1 JavaScript course and choose program **P>1.2C Hello World**. Repl.it is a software environment that allows you write programs in JavaScript.  It then turns your program into something a computer can understand, runs the code and gives the results back to you. The REPL in the name Repl.it stands for Read Evaluate Print Loop. REPL's are simple programming tools that programmers use, and while Repl.it started out as being fairly simple, it has developed into an integrated development environment (IDE).  It is quite possible to write programs with just a text editor, but REPL's and IDE's are very useful.

Repl.it will give you 3 windows.  On the right you will find the assignment instructions from your teacher. The top left window is the *editor* where you write your program, and the bottom left window is called the *console* and it is where you can get information back from your program run.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/replit_helloworld.jpg" width="100%" alt="Repl.it window">

The 3 vertical dots (ellipses) menu in the upper left corner gives you choices mostly about how your screen looks. The green submit button at the upper right is what you press when your program is working properly and you are ready to turn it in.

It is traditional for a first program to be something called "Hello World". Type the following statement in the console (bottom left).

```javascript
"Hello" + " " + "World";
```

This is a program. It doesn't do much, but it's a start. In this book, code examples like `"Hello" + " " + "World";` will be set in a monospaced font similar to what is used in Repl.it and also placed in a light grey box. It will make the examples easier to follow and it will make them easier to copy and paste.

Also note that every statement in JavaScript should end in a *semicolon*. Although the JavaScript interpreter is smart enough to add in missing semicolons for you when it is reading what you have written, it doesn't always do it the way you might expect, so you should always put semicolons at the end of each statement. Later in the course you will see that some statements may run longer than one line. The semicolon goes at the end of the *entire* statement. 

Now type the same code in the editor (top) window and press run.  While you can type code directly into the console, you will typically type it into the editor and then run it to see results in the console.  In order for your teacher to see and test the code that you write when you submit an assignment, it must be typed into the editor.

After submitting your completed Hello World program, take some time and play around with the program.  You can break it, in the sense that it may not work, but you can't break it, in the sense that it isn't fixable.

Try typing `1 + 1` in the console and hit return. Try some other math with minus, times (*) and divide (/). Now try `"green" + 1`. Make sure you use the quotes around green. Did you correctly predict the outcome? As you can see, the computer understood the plus sign to mean "string together" (*concatenate*) rather than "add" in a mathematical sense. Try other combinations of words (with and without quotes) or numbers with the + operator and then try some combinations with the * (*asterisk*).

You may sometimes get error messages in red, which means that your code isn't understood by the interpreter. That's OK, see if you can fix the error.

Finally, since computer programs are read not only by computers but by people, we often need to add information for people that makes our programs easier to understand, but which isn't needed by the computer.  To do this we use two forward slash symbols (//).  Anything on a line after two forward slashes is a *comment* for people and is ignored by the computer.  For instance:

```javascript
//This is a comment line
"Print this " + "to the console"; //The code on this line will run
//This line will be ignored: "Print this";
```

Only line 2 of the program will show up in the console, but not the comment at the end of line 2.  Anything after 2 forward slashes is ignored.

## 1.3 Variables

> **Target**: Be able to create proper variables, request user input and provide output to the user. 

To this point we've been poking around at a computer as though it is some sort of calculator with a full [QWERTY](http://gizmodo.com/why-we-still-use-qwerty-keyboards-even-though-theyre-a-1643855077) keyboard and a big screen. Not too useful. In order to write useful programs, we need **variables**. Variables in computer programs are pretty much like variables in algebra. They "contain" values and those values can change. It is perhaps a better metaphor in computer science to say that the variable *points to* a value rather than to say it *contains* a value, but for an introductory programming course, "contains" works just fine and it keeps it consistent with your math class concept of variables.

In JavaScript programming there are a variety of ways to create variables. This is the standard way:

`let firstNumber = 7;`

`let` is a **reserved** word that JavaScript uses to indicate that the word after it is a variable name. Don't try to use `let` for anything else. It is a reserved word and JavaScript will complain if you do. Look at the list of reserved words [here](https://www.w3schools.com/Js/js_reserved.asp). The "=" puts the number 7 into the variable `firstNumber`. If you don't assign a value to the variable, JavaScript will assign the value `undefined`. It is much better to assign an initial value because it tells us what type of variable you intend it to be and it helps us find errors as we read through the program. Let's take it a little farther with the four line program below. Go to **P>1.3AB Full Name** in Repl.it and paste the first 4 lines below into the editor.

```javascript
let firstNumber = 7;
let secondNumber = 6;
let sumNumber = firstNumber + secondNumber;
sumNumber;
    
> 13
```

I will use the > symbol to indicate what the computer produces in the console as a result of running the program. Can you follow what is going on?

You might be concerned that the assigning seems to be going the wrong direction. You might feel like we should use 7 = firstNumber to put 7 into the variable rather than the other way around, but that isn't how it's done, so you'll have to get used to it. Just think of it like x = 7 in algebra, the 7 goes into the x.

You should always make variable names reflect their purpose, but keep in mind that they can't start with numbers, can't contain non-alphanumeric characters (except \$ and _ ), can't be reserved words like let, and can't contain spaces. We can get around the no spaces rule by using the "\_" character or by interspersing capital letters. Both `first_name` and `firstName` are valid and slightly more readable versions of our variable `firstname` and yet don't break the no spaces rule. Interspersing capitals is the most common technique used in JavaScript programming. It is usually referred to as *CamelCase*.  You should not use all caps for variables even though it is technically valid because all caps is used to indicate a constant.

![Camel Case](https://storage.googleapis.com/codeavengers.appspot.com/cloud/lesson-plans/intro-to-coding/camelcase.png)

With multiple line programs like this, we can make programs that do a bit more for us. Try making a similar 4 line program to the example above by using the variables `firstName`, `lastName` and `fullName`. Hint: put quotes around strings of letters like "Bob" and "Smith". Can you figure out from the variable names what the program should do? Add a comment line which briefly explains what the program does.

Finally you need to know that `let` is a relatively new addition to JavaScript.  Originally the keyword `var` was used to declare variables.  But `var` had some confusing behaviors and it is better for you to use `let`. Don't be surprised however if you read other people's JavaScript on the internet or in books and they still use `var`.  It is very common.

For additional background information take a look at [Crash Course Computer Science episode 12](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo)
​    
## 1.4 Input & Output: I/O

We've made some progress, but there are still some important pieces needed to make useful programs. We can work with strings and do some math and **output** results to the console, but what if we wanted our program to ask a user for something, process that information somehow, and then give the new result back to the user. We can already do output, but we need a way of getting information from the outside world into our program. We need **input**. Input and output are often abbreviated I/O.

> On two occasions I have been asked,
>
> *"Pray Mr. Babbage, if you put into the machine wrong figures, will the right answers come out?"*
>
> I am not able rightly to apprehend the kind of confusion of ideas that could provoke such a question.
>
> *--Charles Babbage (1864)*

Copy and paste the following in the Repl.it program window for **P>1.4C Next Age**:

```javascript
let age = prompt("What is your age?");
let nextAge = 50 + age;
alert("In fifty years you'll be " + nextAge);
```
Notice that the colors are not the same between this text and Repl.it. There is no standard color scheme for *syntax highlighting*, you just have to get used to however your environment does it, unless you are allowed to personalize it.  At present, Repl.it does not let you choose the syntax highlighting colors. Run the program, but first, try to predict what it will do.

Repl.it shows you a dialog box asking for your age. If you respond, the program will continue and tell you that in 50 years you will be `nextAge`. But it will say you are over 5000 years old! What is going on here?

We have some new commands that I'm going to call **functions** (although it would be more precise to call them **methods**) The `prompt()` function displays a box for the user to type something into and then takes what they type and sticks it into the variable age. The `alert()` function also displays a box with info, but doesn't ask any questions.

So we've got input from `prompt()` and we've got output from the `alert()` and it is no longer in the console, so we're heading toward our goal, but something is wrong with the math. We are expecting `50 + age` to be put into the variable `nextAge`, but instead we get 50xx with the xx being whatever age the user enters. The + is doing a concatenation rather than an addition, as though `age` is text and not a number. And that is the problem. In JavaScript any input from a `prompt()` is considered to be text, what we call a **string**, that is a string of letters. Fortunately there is a way to turn strings that look like numbers into actual numbers. It's the `Number()` function. Its **syntax** or proper usage, can be seen in the first line below and note that it *must* start with a capital N:

```javascript
let actualNumber = Number("10");
let finalResult = actualNumber + 5;
finalResult;

> 15
```
Here `Number()` turns the string value "10" into the number 10 that we use to do arithmetic. That will solve our programming problem.

As your programs get longer and more complex, it is a good practice to *declare* all your variables at the top of the program rather than along the way. We can use a single `let` statement and separate each variable with a comma as follows:

```javascript
let age = 10,
    color = "green",
    life = true;
```
While I could have put all three lines on a single line, notice how the *indenting* improves readability. There are often multiple ways to do something. The goal of our various decisions is readability and error avoidance. We may not choose the most convenient way but we should always choose the most readable way. Using descriptive variable names, declaring them at the beginning of a program and assigning initial values has over decades of programming proven to be the best way to do things.

Repl.it provide some nice editing and formatting features.  If you right click on a selected section of code, you have the option to format it, that is, it will automatically indent correctly.  This is very helpful when trying to find errors.  If you right click a variable name, you have the option of changing all of them.  There are many other helpful options as well in the command palette.

Finally, please understand that while we are using the Repl.it environment to learn programming, if we were to use the same code on a webpage, the web browser would also produce prompt and alert boxes for input and output.  The code we learn in Repl.it will be useful in more realistic situations like web pages.

## 1.5 Types of Values & Operators

> **Target**: Be able to describe and use different value types.

In the previous section you saw that in JavaScript some types of values are treated differently than others. For instance in the situation "green" + 1; the 1 is treated differently than in the situation 2 + 1. JavaScript (or more precisely the JavaScript interpreter) will make its best guess as to what you mean. In the situation "green" + 1; it assumes that you want the 1 to be a character, not a number, since it doesn't have any simple way of turning "green" into a number. But in the situation 2 + 1, it assumes that you want both the 2 and the 1 to be numbers, although you could force them to be understood as characters by putting quotes around them.

The issue goes back to the fact that everything a computer deals with is ultimately binary. In binary, 00000001 is 1, but it can also mean "true". How does the computer know the difference? In binary, 01000001 is 65, but it also stands for the letter 'A'. In binary, the number 5 that we can do math with is 000000101, but the character '5' is 00110101, which is also the number 53. This could be very confusing even for a computer. The way the computer keeps all this straight is by requiring that we tell it what **type** of a value something is before we ask it to do some work with it.

### *• Numbers*

JavaScript understands several types of values. The first type of value is **number**. You have already worked with numbers like 1, 0.3 and -47. You can use positive or negative numbers up to about 16 digits, with or without a decimal point. This is because all numbers in JavaScript use 64 **bits**.  A bit is a single 0 or 1.  The number 1101 (decimal 13) would be 4 bits and 11010010 (decimal 210) would be 8 bits, and so on. The most digits you can get out of 64 bits is about 16. With JavaScript numbers you can also use scientific notation: 1.23e4 means 1.23 x 10^4^. The biggest power of 10 you can use is about 300.  Clearly JavaScript allows you to do math with much greater precision than you calculator.

You can add, subtract, multiply, and divide numbers. You can also use parens and you can expect JavaScript to obey the normal PEMDAS order of operations from your math classes. There is one more operator that frequently comes in handy called the remainder operator, or **modulo** and it is represented by the % symbol. It gives the remainder after dividing the first number by the second as follows: 5%2 is 1, 8%3 is 2, etc. You should play with these in your editor to make sure you understand how they work.

### *• Strings*

The second type of value is called a **string**. A string is indicated by putting quotes around something, even a number. "Red" is a string and "2" is also a string. Almost anything can be put between quotes and JavaScript will see it as a string. You can't do math with a string, but you can **concatenate** strings using the + operator as you've already seen.

So far we've been outputting the results of our programs by either stating the variable name that contains the output we want, or by using an `alert()`.  This works but it is often more useful to send things to the console and we have a function that does that better than just stating a variable name.  The function is `console.log()`.  It works just like `alert()` in that whatever you put between the parens is outputted, but this case, to the console.

But what if you need to use a string with a quote symbol inside it like:

`"The " symbol is called a double quote."`

JavaScript won't like it because it doesn't know how to interpret the three quote symbols - it is expecting only two. The way around it involves using a backslash symbol ( \ ). Notice that it is tilting the opposite direction from a division symbol ( / ) known as a *forward* slash and the comment symbol (//). The backslash symbol inside a string alerts JavaScript and tells it that whatever comes right after it is special. So to fix the situation above we would type:

`"The \" symbol is a double quote."`

and it would give us what we want. You should experiment in your editor to see how it works. This process of using a backslash to get out of the normal meaning of a character and into a different meaning is called **escaping**, or using an escape sequence.  There are other escape sequences as well, such as `/n` and `/t` which are next line and tab respectively.

### *• Boolean Values*

There is another type of value called a **Boolean** value, after British mathematician George Boole. A Boolean value can be either true or false. Something like

`3 > 2;`

will produce the value true and

`3 < 2;`

will produce the value false. The symbols `<` and `>` are called **logical** operators and they can be used with strings as well as numbers. The statement

`"Adam" < "Eve";`

will produce the value true. Why? Experiment in Repl.it to see if your reasoning is correct. There are other logical operators such as >= which is "greater than or equal to", and != which is "not equal to", and == which is "equal to". The reason for the double equal sign is that the single equal sign is already used as the assignment operator.  In many cases the triple equal sign is preferred since it checks not only value but type. Try making some true or false statements with those operators.

There are also some operations that can be applied to the Boolean values, true and false. The operations are AND, OR and NOT and their operator symbols are &&, || and ! respectively. According to Boolean logic, a statement is only true if it is entirely true. For instance,

`true && true && false && true && true;`

would produce the value false, but

`true && true;`

would produce the value true. Try some experiments with the other Boolean operators to make sure you understand how they work. If you are interested in how this mathematics is achieved electronically, take a look at [Crash Course episodes 3 and 4](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

### *• Type Coercion*

JavaScript tries hard to make sense out of your programs, even to the point of changing the type of your values. This is called *type coercion*. For example

`"5" - 1;`

produces the number 4, which is nice because that is probably what you intended anyway, but

`"5" + 1;`

produces the string "51", which may or may not be what you wanted. This feature of JavaScript cuts both ways. Sometimes it helps you, but just as often it produces results that you didn't expect or intend and it can make it difficult to find errors in your program.  While you can make your code more compact sometimes by taking advantage of type coercion, your code will be more readable if you make use of the `Number()` and `String()` functions to indicate conversion between types.
