# Front Matter

## Introduction to JavaScript v.4.0

Jeff Seely -- Lynden High School, Lynden WA 98264

Edition 4.0 Revised Summer 2021

This text is original by the author or dependent on sources specifically cited in the text. Illustrations are original by the author, are public domain, Creative Commons, or are cited in the text. Citation does not imply use with permission.

This text is not intended for use outside of Lynden High School. It may not be legally distributed, reproduced or sold without express permission of the author. No organization or individual paid for or profited from its production. The Lynden School District is not responsible for its content.

Any hardware projects described in this text must be done under competent supervision.

At present, this text is undergoing nearly constant revision. Do not assume this version is current. Contact the author directly regarding errors at seelyj@lynden.wednet.edu

## Additional Resources 

The web is full of potentially useful things, but I wanted to highlight some free resources that I think are particularly good.

[W3Schools](http://www.w3schools.com/) and [Mozilla Developer Network](https://developer.mozilla.org/en-US/) are the basic reference sites for JavaScript and HTML.

[Eloquent JavaScript: A Modern Introduction to Programming](http://eloquentjavascript.net/) by Marijn Haverbeke - This book is free in digital form and is one of the main sources I used when writing this textbook.

[JavaScript: Novice to Ninja](http://ix.cs.uoregon.edu/~michaelh/cl-mh/CIT/JavaScript_Novice_to_Ninja.pdf) by Darren Jones - A really well organized presentation for beginning programmers.

[Harvard CS50](https://cs50.harvard.edu/) - This is not a download and it's not just about JavaScript, but the lectures & videos contain great info.

[JSBooks](http://jsbooks.revolunet.com/) - has a library of free JavaScript texts, some downloadable.

[JavaScript Tutorial](http://javascript.info/) by Ilya Kantor has a ton of good examples and demonstrates good coding style.

[DOM Enlightenment](http://domenlightenment.com/) - Cody Lindley for additional information on the document object model.

[The Pocket Guide to Writing SVG](http://svgpocketguide.com/book/#intro) by Joni Trythall is excellent.

Jakob Jenkov has some very good [SVG tutorials](http://tutorials.jenkov.com/svg/index.html) including videos.

Espruino JavaScript and Pico documentation on the [Espruino website](http://www.espruino.com/).

Joshua Davies has a series of helpful posts on the Chrome developer tools and debugging [here](http://commandlinefanatic.com/cgi-bin/showarticle.cgi?article=art033).

[Repl.it](https://repl.it/): is an online programming environment we use for beginning programming and for submitting assignments. It is not browser specific and there is nothing to install.

[Espruino Web IDE](https://chrome.google.com/webstore/detail/espruino-web-ide/bleoifhkdalbjfbobjackfdifdneehpo) (although it will not work without an attached microcontroller and also requires the [Chrome browser](https://www.google.com/chrome/)).

[Fritzing](http://fritzing.org/home/) - for creating new breadboard layouts.  The software is used frequently in this text.

[Chrome](https://chrome.google.com/): has lots of good developer tools.

If you really get into microcontrollers and want to make your own hardware, my favorite sources of material and information other than eBay are [Adafruit](http://Adafruit/), [Sparkfun](https://www.sparkfun.com/) and [Tindie](https://www.tindie.com/).

## Sources & Contributors 

While I have culled information and ideas from a lot of places, I want to acknowledge those on which I have been most dependent. Any errors in this book are mine, not theirs.

Gordon Williams creator of Espruino and Pico, at espruino.com. Many of the Pico projects are originally from his site or are adaptations of those projects.

Marijn Haverbeke in Eloquent JavaScript: A Modern Introduction to Programming.

Lauren McCarthy, et al in Make: Getting Started with p5.js: Making Interactive Graphics in JavaScript and Processing. A number of the examples in Ch. 4.5 are based on ones from this book.

This text is a work in progress and I'd like to acknowledge students and former students who have contributed significant additions and corrections:

* Ben Hamming, for reviewing and contributing changes to the text.
* Caleb Erickson, for contributions of clarification to Ch. 1
* Alex Peterson, for contributions on robotics in Ch. 3
* Alex Wyatt, for contributions on wifi and client/server communication in Ch. 7
* Ryan Kussman, for writing the Appendix 2 section on Method Draw

<!----><a name="1"></a>
# 1 - What is JavaScript?

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

<!----><a name="1.2"></a>
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

<!----><a name="1.3"></a>
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

<!----><a name="1.4"></a>
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

<!----><a name="1.5"></a>
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

<!----><a name="2"></a>



# 2 - Control Flow

We read from the top of the page to the bottom, we do math problems from top to bottom, but computer programs are not so simple.  Sometimes sections repeat or one instruction jumps to another, or some sections may be skipped entirely. When we read computer programs, we need to look for statements that control what is going on and see how the program flows from one controlling statement to another, that is, we follow the *flow of control*, or **control flow**.  In this section we study those controlling statements.

## 2.1 The IF statement

We need our program to be able to make decisions based on user input or other conditions. To accomplish this, JavaScript has reserved words like `if` and `else` that allow us to build in that decision making capacity. Consider the following code:

```javascript
let birthYear = prompt("Give year of birth");
birthYear = Number(birthYear);
let age = 2015 - birthYear;
if (age < 16) alert("You are too young to be kissed");
else alert("You are more than 16 years old.");
```

The `if` statement in line 4 sets up a decision. If ``(age < 16)`` is true, then the `alert` that immediately follow is executed. Otherwise, the `alert` after the `else` statement is executed instead.  It's one or the other. Every `if` statement needs a **conditional** inside parens, something that is either true or false. If true, the code that follows runs, if not, then it runs the `else` code if there is an `else` present. The `else` is optional. Using the `if` statement allows the program to do different things depending on the user inputs. It makes the program just a tiny bit intelligent.

> *A programmer puts two glasses on her bedside table before going to sleep. A full one, in case she gets thirsty, and an empty one, in case she doesn't.*
>
> *Anonymous*

Please note that in line 1, `birthYear` is a string variable, but in the second line it turns into a number variable. This is type coercion. This is OK to do in JavaScript, because it is a *dynamically typed* language, but most other programming languages are not dynamically typed, so we will usually avoid having variables switch between different types in this course.

Also note that we only use the reserved word `let` when we first introduce (*declare*) a variable name, never after that.

In Repl.it, open **P>2.1C** and paste in the **birthYear** code. Use this code as a template. Make your own variations on the program that ask the user for input and respond in different ways depending on what input the user gives.

<!----><a name="2.2"></a>
## 2.2 The WHILE statement

Another way to control programs is by using a while statement. Suppose in the previous program, we were concerned that the user might not put in a reasonable year of birth. We could use a `while` and an `if` statement combination to check and repeat until the user did enter a reasonable year.

![ Figure 1.C Repl.it sample program](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/fig2.2sample.jpg "birthYear program part 2")

Carefully type the program into **P>2.2C Input Checker** in Repl.it (you can copy and past it). Pay attention to the colors. If they aren't similar to what is in the example, you've typed something wrong.  If you have a black background editor, you can switch to white for this example. Change all the 2015's to the current year. Run the program and respond that you were born in the future, then respond that you were born in 1776, then respond with your actual year of birth.

The first new thing you encounter in this program is the `while` loop. It is called a *loop* because it keeps looping between the curly braces `{ . . . }` *while* its conditional statement is true. In this case, as long as the birth year the user enters is after 2015 (which is not likely) or before 1915 (which would make them over 100), the while loop will keep running. It will keep asking them what year they were born and keep converting their response to a number and putting it in the variable `birthYear`. As soon as they enter a reasonable year of birth during the last 100 years, the conditions will no longer be met and the while loop will not be executed. The program will move on to line 6 which subtracts their birth year from 2015 to get their current age.

The curly braces are also new. In JavaScript if you want to group a set of statements together, you put them inside curly braces.  This is structure from `{` to `}` is called a **block**. You would typically use curly braces for `if` statements as well, as shown below:

```javascript
if (school == "lynden") {
    alert("Your colors are green and yellow");
    alert("Your mascot is a lion");
}
```
Put the first `{` on the same line as the `if` statement as shown in this example and put the closing `}` on it's own line below the `if` statement. Everything between the braces should be indented. Indenting is very important for making your code readable and for helping you avoid errors. While the code will run without the indenting, it will be unacceptable, sort of like writing a letter without punctuation. The reason that braces were not needed in the original birthYear program is that there was only a single line of code between them. It is good practice, however, to ALWAYS use curly braces, even if you have only one line of code since you will often need to come back and add more lines in. So in this respect, the original birthYear program was an example of what *not* to do.

Here's another example of a while loop with proper curly brace placement:

```javascript
let counter = 0;
while (counter <= 5) {
    console.log("Counter = " + counter);
    counter = counter + 1;
}
```
A variable called `counter` is set to 0. Then we begin a `while` loop which adds 1 to `counter` each time through the loop and outputs the value. Eventually `counter` becomes 6 at which point the loop condition is no longer true and the program is finished. Instead of using an `alert()`, in this case we are sending the output to the console.  `Console.log()` is a very useful function/method that we will use frequently throughout the course.

It should be noted that if the condition of the `while` is never false, the loop will never stop. For instance in our example, if we had mistakenly written:

`counter = counter - 1;`

then `counter` would always be less than or equal to 5 and always true, so the loop would never end. This is called an *infinite loop*. Everybody writes one by accident sometime, but they should be avoided. If you create an infinite loop in Repl.it, you may be able break it by clicking the [stop] button, but more likely you will need to refresh the page, in which case you will lose your changes since your last save, so save often.

<!----><a name="2.3"></a>
## 2.3 The FOR loop

The next kind of control statement we will consider is the for loop. The for loop is a convenient way to do what we did with the previous while loop: repeat the loop with a counter determining the number of times we do it. The syntax of the for loop is as follows, according to the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript):

```js
for ([initialization]; [condition]; [final-expression]) statement
```

Rather than give you a specific example of code, they've given you a general statement. As you learn to program, you'll frequently be looking up how different commands work so you'll need to get used to these general statements. But they also give you an explanation of terms and at least one example:

-   The *initialization* is where we set our counter to its starting value. -   The *condition* is where we put a conditional statement that needs to stay true for as long is we want to loop to run. -   The *final-expression* is where we add whatever we want to the counter each time the loop is completed. -   The *statement* is any single statement or set of statements { . . . } to be carried out during each loop.

```javascript
for (let i = 0; i < 9; i++) {
    console.log(i);
    // more statements
}
```
There are some new things here. Their counter is the variable i, which is a common variable name for a counter. i is short for **iterate** which means to change repeatedly. It starts out at zero and the loop will run so long as i is less than 9. Then comes `i++`? The `++` is called the increment operator and its effect is to add one to whatever variable it comes after, so it has the same effect as `i = i + 1;` This operator was developed around 1969 and is found in most computer languages related to the programming language C, like JavaScript. While we're on the topic, there is another short way of incrementing a counter:

`counter += 1;`

This statement also does the same thing as `counter = counter + 1;` and `counter ++;` The reason for these shortcuts is that incrementing counters is a common programming task. Note that statements like `i++` are falling out of favor and your code would be considered higher quality if you used the preferred `i += 1` form. Take some time to play with `-=` and `*=`, they work too.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/nicetry.jpg" width="100%" alt="FoxTrot - Bill Amend -- Universal Press Syndicate" hover="FoxTrot - Bill Amend -- Universal Press Syndicate">

<!----><a name="2.4"></a>
## 2.4 The SWITCH/CASE statement

The `switch` and `case` statements aren't used for looping, rather they work like a multi-branched `if` statement. Here is an example:

```javascript
let answer = prompt("What is your favorite color?");
    switch (answer) {
	case "red":
	    alert("hearts, strawberries");
	    break;
	case "blue":
	    alert("ocean, jeans");
	    break;
	case "green":
	    alert("grass, go");
	    break;
	default:
	    alert("nice color");
    }
```
Paste it into **P>2.4 Switch Case: Favorite Day** in Repl.it. See if you can predict how it will work before you run it and then run it to see if you were right. Now put a couple of forward slashes // before each of the `break` commands. This will turn those lines into comments which the computer will ignore and it is a quick way to turn a line off and on without retyping the whole line. Now run it with the `break`'s commented out. You should now be able to describe what `break` does. Why don't we need a `break` in the `default` section? Always make sure you include a `default` case to handle unexpected situations without crashing your program. If you want, you can think of a `switch case` as a series of `if` statements with `default ` being like an `else` for all of the `if`'s.  Finally, note that `break` can be used in any loop to break out of it before it has finished.

<!----><a name="2.5"></a>
## 2.5 Commenting Revisited

Of course commenting isn't just for turning lines of code on and off, commenting is primarily to explain your code. It is important that computer programs can be read and understood at least by other people who know the particular language being used. But as our programs get more complex, grasping what the program is doing and how it works can be difficult to see. Even if you are the one who writes a program, if you return to look at it 6 months later, you might forget how it worked. It would be helpful if we had some explanatory information along with the program so that if we later need to make modifications we will be less likely to mess up something important. This is what we use comments for. Here's an example program that we will put comments into:

```javascript
/* CS1 - Jeff Seely - 9/28/15 - 3 digit Armstrong Numbers
 *  
 * This program finds all 3 digit Armstrong numbers. 
 * An Armstrong number, such as 153, is a number in which 
 * if each digit is cubed their sum equals the number itself.
 * 1 + 125 + 27 = 153
*/

let possible = 0,
    cubedNum = 0,
    d1 = 0,
    d2 = 0,
    d3 = 0;
	
console.log("The 3 digit Armstrong numbers are:");
for (d1 = 1; d1 <= 9; d1+=1) {
    for (d2 = 0; d2 <= 9; d2+=1) {
        for (d3 = 0; d3 <= 9; d3+=1) {
	    possible = d1*100+d2*10+d3;
	    cubedNum = d1*d1*d1+d2*d2*d2+d3*d3*d3;
	    if (possible==cubedNum) {
		console.log(possible);
	    }
	}
    }
}
console.log("done");
```
At the top of the program is a heading set off by /* and \*/ marks. This is one way to set off a comment. The computer ignores anything between /* and \*/ no matter how many lines it takes. This is the sort of heading that you will use in this course. Without the heading comment (and line 3 of the program), it would be very hard to know what this program was about. While the /\* . . . */ style comments can be used anywhere in a program, more commonly you will use the single line comments that you have already seen, where the comment line simply starts with //. Finally, you can add blank lines and indentations to make sections of the program more obvious.

The following is what a better commented program would look like:

```javascript
/* CS1 - Jeff Seely - 7/13/15 3 digit Armstrong numbers.
 * This program finds all 3 digit Armstrong numbers. 
 * An Armstrong number, such as 153, is a number in which 
 * if each digit is cubed their sum equals the number itself.
 * 1 + 125 + 27 = 153 
 * For 2 digit numbers, the digits would be squared 
 * and for 4 digit numbers the digits would be taken 
 * to the 4th power, etc.
*/

let possible = 0, //initialize variable for possible Armstrong number
    cubedNum = 0, //and the digits of the number cubed
    d1 = 0, d2 = 0, d3 = 0; //loop incrementers

//set up for the results
console.log("The 3 digit Armstrong numbers are:");

//loops for the 100s, 10s and 1s places: d1,d2,d3 respectively so
//that all three digit numbers are generated.
for (d1 = 1; d1 <= 9; d1+=1) {
    for (d2 = 0; d2 <= 9; d2+=1) {
        for (d3 = 0; d3 <= 9; d3+=1) {
            possible = (d1*100)+(d2*10)+d3;//calculate possible
            cubedNum = (d1*d1*d1)+(d2*d2*d2)+(d3*d3*d3);//calc cubedNum
            if (possible==cubedNum) {//see if they are the same
                console.log(possible);//if so, display
            }
        }
    }
}
console.log("done");
```
Clearly this fully commented version takes up more room and takes longer to write, but it contains useful information that helps the reader figure out what's going on. Even the addition of unnecessary parens in the lines calculating `possible` and `cubedNum` can make it easier for the reader to follow. But even though it takes up more space, the computer is ignoring all the extra and so the program runs just as quickly.

What do you mean it needs comments!? If it was hard to write, it should be hard to understand. Why do you think we call it code???

Another thing that you can do in comments is say where you got code from if you didn't write it from scratch. It is very common for programmers to copy and paste bits of code and one of the reasons this text is in digital format is so that you can easily do that. Trivial bits of code, say two or three lines, need not be attributed to a source, but if problems are solved and coded by someone else, you can't just copy and paste the code and call it yours. There are many law suits currently in the courts between software companies on specifically this matter. Plagiarism in programming languages is still plagiarism, and in most cases you can't use significant pieces of someone else's code without their permission even if you do credit them in your comments. In this course, if someone comes up with a nifty chunk of code that we want to make available to the class, we'll discuss it in class and agree to comment it if we use it. Otherwise, your code should be your own.

<!----><a name="2.6"></a>
## 2.6 Nesting

The Armstrong number program uses a technique called **nested** `for` loops, that is, a `for` loop inside of another `for` loop. In this case, three `for` loops are nested.

Can you sort out how the nested `for` loops work together to generate all the 3 digit numbers? Try *being* the computer and keep a list of the values of the variables as you go through each loop. Three nested loops is not very common but two loops are frequently nested. Notice that we needed to be able to cube each digit separately which lent itself to this structure. This was one possible algorithm, there are others.  An algorithm is a logical process for solving a problem.  Take a look at [Crash Course Computer Science episode 13](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo) for additional background information.

You can nest any sort of block you want and mix and match.  For instance you can put an `if` block inside a `for` block inside a `while` block.

<!----><a name="2.7"></a>
## 2.7 Simple Functions

In JavaScript, a function is commonly used to group together a set of statements that accomplish a task. Once the function is written it can be used anywhere in the program that it is needed by just **calling** its name instead of rewriting the code every time. As with loops, we have parens and curly brackets.

```javascript
function square(x) {
    return x * x;
}
console.log(square(12));

>144
```

The function `square` has been declared by using the keyword `function`. This syntax is called a *function declaration* and the keyword `function` works like the keyword `let`. This is not the only syntax we can use to declare a function, but it is the one we will most commonly use. The syntax requires parens after the function name, and inside the parens is a variable that will contain the value that the function will work on. This variable in the parens is called a **parameter**. In this case, we are going to **pass** the value 12 into our function and it will take the 12, assign it to the variable x and then multiply x by x, which in this case is 12 times 12. The keyword `return` determines what the value of the function will become when the function is finished. In this case, the function will become x times x or 144 which is then assigned to the variable `square`. Functions can contain as many statements as needed within the curly brackets. If no value is given in the `return` statement, or if there is no `return` statement, the value of the function will become **undefined**. At whatever point the `return` keyword is encountered, the function is exited, so be careful where you put `return`.  

Notice that no semicolon is required after the last curly brace of the function, but semicolons *are* required at the end of each statement inside the curly braces, that is, inside the block. We can now make the semicolon rule a little more precise. Semicolons are required at the end of every **executable** JavaScript statement. The function declaration doesn't actually get executed unless some statement in the program calls it (like line 4 in the previous program), so it is common to leave off the semicolon.

The following example shows how we could use our `square()` function multiple times in one program:

```javascript
function square(x) { 
    return x * x;
}

let len = prompt("Enter a length");
len = Number(len);
let areaSquare = square(len);
let areaCircle = square(len)*3.14;
alert("Area of square = " + areaSquare);
alert("Area of circle = " + areaCircle);
```

By writing our function for squaring, we can use it to calculate the area of a square and the area of a circle without rewriting the code in the function. While the amount of code in our function is trivial, the idea is easy to grasp. If we had a 30 line block of code that we needed to use a dozen times in our program, writing and calling a function would be much more efficient.

Functions can have more than one parameter and can contain loops or any of our other programming components, but they can only return one value. Next we look at a function that takes 2 parameters and calculates powers of a given base. Can you follow how it works? Remember from math class that powers are just repeated multiplication.

```javascript
function power(base, exponent) {
    let result = 1;
    for (let count = 0; count<exponent; count++)
        result *= base;
        return result;
}
console.log(power(2, 10));

>1024
```

Remember it is good programming practice to declare all variables at the top of a program, and this true for within a function too.

Try to keep in mind that a function always equals a value, or is undefined. Since a function equals a value, a function can be passed into another function as a parameter, just as if it was a value, which it is.

<!----><a name="2.8"></a>
## 2.8 Scope & Global Variables

An important thing to note is that variables declared using a `let` statement within a function or block only exist within the function or block in which they are declared. For instance in the previous example, the variable x only exists inside the `square()` function. Add the line `alert(x);` at the end of the program. While the value of x should be whatever you typed into the prompt, JavaScript tells you it is undefined. On the other hand, if you put the `alert(x);` line inside the function, it gives you the information you expect. Why do you have to put the `alert(x)` before the `return`? The part of a program where a variable is available is called its *scope*. The scope of a variable declared inside a function is the function itself. It is not available outside the function. If you need multiple functions to have access to a single variable you can pass that variable around as a parameter. This is the preferred strategy, however sometimes it is simpler just to declare the variable outside of all of the functions. These sorts of variables that are available to all the functions are called *global* variables. It is common to put the names of these global variables in all caps. We will make use of global variables later when we do some simple animations.

Using global variables is considered something to be avoided, particularly if more than one programmer is involved. Programs often get changed and have bits of code added from numerous sources. You can imagine that it would be easy for different programmers to use the same variable name and if those variables are globals it would likely break the code. The way we avoid global variables is by wrapping most of our final code inside a function statement. We control the scope of our variables by wrapping them in functions. Note that it is not the curly braces that control the scope, it is the function statement itself. The curly braces inside a `for` or `while` loop do not restrict the scope of a variable declared inside them.

Another thing to know about global variables: if you declare a variable without using `let`, that is, if you just start using a variable without formally declaring it, JavaScript makes it a global variable. This is true even inside of a function. Since this would produce very unpredictable behavior, you should ALWAYS make sure to declare variables with a `let` statement.

Finally you should be aware that variables declared with `var` only have function scope, not block scope like those declared with `let`.  They can also be global variables the same as with `let` declared variables.

Another interesting property of functions is that they can call themselves. This is called *recursion*. For instance, the following function calculates the factorial of the number passed as its parameter.

```javascript
function factorial(num) {
    if (num == 0) return 1;
    else return (num * factorial(num - 1));
}
let result = factorial(6);
console.log(result);

>720
```

While recursion is a useful and common technique, there are some potential memory problems with its current implementation in JavaScript so we won't be working with it further. These problems are likely to be addressed in future versions of JavaScript.

<!----><a name="2.9"></a>
## 2.9 Methods

In JavaScript, *methods* and *functions* are very similar, in fact, methods *are* functions, just a special sort of function. While they both have attached parens, the most apparent difference is that methods have a dot in the name as in the `console.log()` method. We have already been using several methods: `console.log()`, `window.alert()` and `window.prompt()` although the window part hasn't been necessary for our previous uses. The words to the left of the dot give us additional information about what sort of method it is and are often necessary for the proper function of the method. The `log()` method belongs to something called the console object and the `alert()` and `prompt()` methods belong to something called the window object. Objects will be one of the topics of Chapter 3.  The thing that distinguishes methods from regular functions is that methods are functions connected to objects.

There are many built in methods in JavaScript, in contrast to relatively few built in functions. Functions are mostly custom written by programmers whereas most programmers make considerable use of built in methods. In our exploration of built in methods we will begin with math methods.

### *• Math Methods*

It would be a pain if we needed to create all the normal math functions like powers, roots and trig functions by writing our own functions using only arithmetic operators. Fortunately there is a nice set of math methods that we can call whenever we need them. Below is a sample of some of the most commonly used math methods. Many more are available. If you need something that isn't listed, look it up and it will probably be there.

**Math.abs(x)** Returns the absolute value of a number.

**Math.ceil(x)** Returns the smallest integer greater than or equal to a number, that is, it rounds up.

**Math.cos(x)** Returns the cosine of an angle x given in radians.  To use angles in degrees (d), you would need to convert to radians first: $radians = \frac{\pi \times degrees}{180}$

**Math.floor(x)** Returns the largest integer less than or equal to a number, that is, it truncates anything to the right of the decimal point.

**Math.pow(x, y)** Returns base x to the power y, or x^y^.

**Math.random()** Returns a pseudo-random number from 0 to 1, but not including 1.

**Math.round(x)** Returns the value of a number rounded to the nearest integer.

**Math.sqrt(x)** Returns the positive square root of a number.

The **Math.random()** method is often used in games to simulate dice, spinners, cards or any other random element of a game. Let's start with flipping a coin.

```javascript
function flip() {
    let coin = "idle";
    if (Math.random() > 0.5) coin = "heads";
    else coin = "tails";
return coin;
}

console.log(flip());
```

Since the `Math.random()` method generates numbers between 0 and 1 and we need to split them into two equal groups, we can just check to see if they are greater or less than the half way point of 0.5. When we call the `flip()` function, coin is returned to us with a value of heads or tails. In this case, we don't need an argument since we don't need any information from the user for the function to work.

![XKCD #221](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/xkcd.png "XKCD #221")

Try out some of the other Math methods in your editor to see how they work. Make sure you capitalize the M in Math.

### *• String Methods and ASCII*

Another set of built in methods are available for working with strings. A sampling of some of the many methods available are listed below.  

Some of the methods involve Unicode so here's some background on that.  As you recall, each letter corresponds to number, which for the computer is actually binary.  The ASCII code assigns each letter a 7 bit binary value, for instance, "a" is 1100001 (97 decimal) and "b" is 1100010 (98 decimal), etc.  The ASCII code references more than just small letters, there are also capitals, numerals and other symbols that you might find on a keyboard.  But since the binary representation is only a 7 bit binary, only 0 through 127 (1111111 binary) can be represented.  In order to accommodate more characters, especially for other languages, a new system was adopted called Unicode.  It uses a minimum of 8 bits for each character (you may have seen UTF-8 in an HTML head) but can be as many as 32-bits.  This gives an enormous number of options.  Note that the original ASCII encoding was retained for those characters in Unicode7

**charAt( *index* )** returns the character at a specified index. The index of the first letter is 0, the second letter is 1, etc.

**charCodeAt( *index* )** returns the Unicode value of the character at the specified index.

**String.fromCharCode( *value* )** returns a the Unicode letter (as a string) for the given Unicode value.  You must include String with a capital S in order to turn the number into a string.

**indexOf( *character* )** returns the index of the first occurrence of the specified character, or -1 if it doesn't occur.

**replace( *searchFor, replaceWith* )** searches for something in the string and replaces it with specified text.

**slice( *startIndex, endIndex* )** returns a string from the first index up to but not including the second index.

**toUpperCase()** returns the string in upper case.

Some of the methods like `toUpperCase()` have no argument (the thing in the parens, similar to parameter), while others like `charAt()` require one argument, and others like `slice()` require two. Next is some example code to demonstrate the syntax:

```javascript
let myString = "JavaScript";
console.log(myString.toUpperCase());
console.log(myString.charAt(2));
console.log(myString.slice(4,9));

>"JAVASCRIPT"
>"v"
>"Scrip"
```

Try the other string methods in your editor to see how they work. You may need to look some up.

### *• Number Methods*

In addition to the Math methods, there are also a few Number methods that take numbers as parameters and do something with them. For instance the `isNaN()` method returns true if the parameter **is** **N**ot **a** **N**umber. The `toString()` method turns a number into a string. You should take a look at a list of number methods so you have an idea what is available. They come in handy from time to time.  A handy method for formatting numbers is `toFixed(x)` where x is the number of places to the right of the decimal point.

### *• String and Math Properties*

Along with methods, we have properties. Properties are different from functions and methods in that they don't act on anything, they don't process data, rather they simply report on something that already exists. Properties don't have arguments. For instance we have the string property `.length` and Math properties `.PI` and `.E` with syntax as follows:

```javascript
let myString = "JavaScript";
console.log(myString.length);
console.log(Math.PI);
console.log(Math.E);

>10
>3.141592653589793
>2.718281828459045
```

Try to keep in mind that JavaScript is *case sensitive*, that is `Math.PI` is not the same as `math.pi`. The first way works, the second way produces an error. As we will see in the next chapter, other languages, like HTML, are not case sensitive. These differences just mean you have to pay attention.

One of the topics covered in the programs, but not the text is encryption. For additional background on this important topic, take a look at [Crash Course Computer Science episode 33 and 31](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo)

<!----><a name="3"></a>
# 3 - JavaScript & Micro-controllers

## 3.1 Controlling Micro-controllers

### *• Microcontrollers*

Computer technology is ubiquitous in our times and we can find it in places where there is no screen or keyboard. Every currently produced automobile has several computer managing the engine and other equipment, microwave ovens and printers have computers inside, grocery stores have automated checkout lines managed by computers, home automation systems are growing in popularity, robots and drones are all the rage and they all, of course, are managed by computers. Most of these computers are small and simple with no facility for a screen, keyboard, trackpad or mouse, no USB port or speakers, none of the usual things we associate with computers. They may have a very limited UI (**user interface**) or none at all. They are designed to run one program over and over again. They are loaded with that program when they are installed and that's all they do. In most cases what we are talking about is not a general purpose computer but a microcontroller. Microcontrollers typically consist of a single chip or *IC* ([Integrated Circuit](https://learn.sparkfun.com/tutorials/integrated-circuits)) containing a processor (computer), memory and some form of I/O.

> *Computer science is no more about computers than astronomy is about telescopes.*
>
> *--Edsger Dijkstra*

Microcontrollers became commercially available in the 1970's and as their cost dropped their power increased. They are used in nearly all electronic devices. Hobbyists have long built things with microcontrollers but in the last few years programming microcontrollers has become much more accessible. These easily programmable and inexpensive microcontrollers are now used extensively to quickly prototype new products prior to their mass production or to provide solutions to one-time problems.

### *• Espruino Pico*

The Espruino Pico is a microcontroller that can be programmed using JavaScript. The specific processor used is an ARM Cortex M4 which the manufacturer says is designed for "motor control, automotive, power management, embedded audio and industrial automation" tasks. In addition, it has very low power usage allowing it to run on a single battery for months.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/Pico.jpg" width="100%" hover="Pico closeup" alt="Pico closeup">

The processor itself is about 1/4 inch square (the white chip numbered 0343 in the photo), and as part of a Pico, it comes with a clock, a button, a couple of lights, a USB interface, a set of pins and a few other odds and ends, but the Pico board ends up less than 1.5 inches long and about half an inch wide - a rather small computer, but plenty for us to work with.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FritzingPicowBB2.png" width="100%" hover="Pico on Breadboard" alt="Pico on Breadboard">

While the Espruino JavaScript interpreter does not recognize all JavaScript commands, it handles all we will need, plus it adds a bunch of functions for us that allow us to program the Pico to do all sorts of things. A complete list of the JavaScript functions available on the Pico can be found in the reference section of the Espruino website [here](http://www.espruino.com/Reference).

You will be assigned a Pico on a breadboard along with a USB cable. Connect your Pico to the USB cable and then to your laptop as demonstrated by your teacher. You should see a small red light on the Pico flash once when the connection is made. The red flash indicates that the Pico is getting power from the laptop via the USB cable.

Now start up the Espruino Web IDE (WIDE) software according to your teacher's instructions. 

![Espruino WebIDE](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/EspWebIDE.png "Espruino WebIDE")

Click the orange Connect button ![ Connect icon](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/connecticon.png "Connect icon") in the upper left corner and choose a COM port. You are now ready to send JavaScript programs to your Pico via the Web IDE (WIDE). For the most part we will type programs in the editor on the right side (white) and then use the send button ![ Send icon](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/sendicon.png "Send icon") to send them to the Pico for execution. Results will appear in the console on the left (black). You can also type instructions in the console at the > prompt, one at a time. When you hit return at the end of the instruction line, the instruction will go directly to the Pico and wait for a response which will appear below your instruction after an equals sign (=). You can clear the left side by clicking the delete button with the X in it.

The first Pico-specific function we will look at is `digitalWrite()`. This function is not part of JavaScript proper - you won't find it at [w3schools](https://www.w3schools.com/jS/default.asp). Rather it is a function written by the developer of the Pico that gives us control of the chip via JavaScript.

![Pico pinout diagram -- espruino.com](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/Espruino_Pico_pinout.png "Pico pinout diagram")

The function has 2 parameters and its syntax is `digitalWrite(pin,value)`. The Pico has 29 pins that we could connect wires to, along with another 14 pins that are already designated for a given function, like the USB connector, the clock and a couple of [LED's](https://learn.sparkfun.com/tutorials/diodes) (*light emitting diodes*). In the `digitalWrite()` function, we specify the pin by it's alphanumeric (A5, B3, etc.) or its function (LED1, LED2, etc.). For this example we will use LED2. The value can be numeric (1 or 0), or boolean (true or false), or string ("on" or "off"). Type `digitalWrite(LED2,1)` in the console and see what happens. Remember that JavaScript is case sensitive, so if you forget to capitalize the W or anything else, it won't work. Don't worry about the Pico returning *undefined*, it's just because the `digitalWrite()` function doesn't return any value. Can you think of a way to turn off the green LED? Now play with LED1.

Here is an example from the Espruino website using a function called `setInterval()`. Paste the code below into the WIDE editor and send it to the Pico.

```javascript
let state = true;
function toggle() {
	state = !state;
	digitalWrite(LED1,state);
}
let blinker = setInterval(toggle,500);
```

You can see on line 6 that the `setInterval()` function calls the toggle function every 500 milliseconds (ms). The `setInterval()` function is the most common way to control events over time. To stop the blinking, type `clearInterval(blinker)` in the console.

This is a straightforward program except for a couple of things: first note the nifty use of the boolean variable `state`. What does `state = !state;` do? We could have accomplished the same thing with an `if else` statement.

Modify the code to speed up the rate of blinking. At what interval can you no longer perceive the light going on and off? Do you suppose there are microcontrollers in police light bars?

Before moving on to more sophisticated work with the Pico, take some time to explore some features of the the WIDE. Go to the Settings menu (gear in upper right) in the About tab. Some of the Editor Key Shortcuts can come in handy. In the General tab you can change the font size and interface size.  Finally you should try to Save and Open a file using the 2 icons in the gray strip between the console and the editor. Your file extension should be .js as in `myFile.js`. 

Complete **P>3.1C**.

<!----><a name="3.2"></a>
## 3.2 Programmable Circuits

> **Target:** Be able to build basic circuits with batteries and switches and use circuits and switches to trigger programmed events in a microcontroller. Be able to output program data to an LCD. 

### *• Breadboard*

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270Connections.png" width="100%" alt="Breadboard connections" hover="Breadboard connections">

To make lights turn on, or speakers to sound, or electric motors turn, you need a flow of electricity from a source, through your device to power it, then back to where it started. This pathway is typically along a metallic surface or wire since metal is a good conductor of electricity. This pathway is called a circuit. Your white breadboard allows us to make connections and circuits without soldering or crimping. When you put a wire into a hole on the breadboard, it makes a connection with any other hole on the same numbered row. In the diagram above, the connected rows have a colored line connecting them. Holes A1 through E1 are all connected, but they are not connected to A2 through E2, nor are they connected to F1 through J1. The positive (+) row running horizontally at the top are all connected, as are the holes in the negative (-) row at the bottom.

### *• Electric Current and Circuits*

Our source of electrical current will either be the USB cable attached to a computer or a [battery](https://learn.sparkfun.com/tutorials/battery-technologies). Both will provide about 5 volts. Think of the wires and metal connections in the circuit like pipes, the current like the flow of water in the pipes and voltage like water pressure.

In the illustration below, the red lead is positive (+) and should always go to the top (+) positive row of the breadboard. The black lead is negative and should go to the (-) negative bottom row. While technically the direction of the flow of electrons is from negative to positive, it is traditional to talk about the flow going from positive to negative. We will do so in this book.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270LED.png" width="100%" alt="LED Circuit" hover="LED Circuit">

The cylinder with bands is a **resistor** and it [reduces the current and voltage](https://learn.sparkfun.com/tutorials/resistors) of electricity, like a constriction in a pipe would reduce the flow and pressure of water. Without the resistor, the LED would burn up. This is a 200Ω resistor (Ω is the symbol for *Ohm*, the unit of resistance). The higher the ohms, the smaller the flow of electricity. Every electrical device has an expected amount of current. Too much and we burn it up, too little and it won't run. The mathematics needed to calculate the size of resistor needed is outside the scope of this course, but there's a nice tutorial [here](https://learn.sparkfun.com/tutorials/voltage-current-resistance-and-ohms-law) if you are interested.

The LED has a long and short wire. The long wire connects to the positive (+) red side and the shorter wire connects to the negative (-) black side. One of the properties of a diode is that it only allows the electrical flow in one direction, so if you have it backwards, it will block the current flow and the light will not turn on.

With the power pack in the OFF position, set up the circuit according to the illustration. This circuit has no connection to the Pico, but we will leave the Pico on the board for now. NEVER MAKE CONNECTIONS TO THE PICO IF IT IS CONNECTED TO POWER FROM USB OR BATTERY. It is easy to fry a Pico. There are a few differences between your actual components and the illustration, but you should be able to set it up correctly anyhow. Fritzing is the software used to make the diagram. It is freely available for [download](http://fritzing.org/download/) on the internet should you want to make your own diagrams.

Make sure you can follow a path of connections or wires from the red battery lead all the way through the circuit and back to the battery back on the black lead. Don't turn on your battery pack until your instructor OK's your circuit.

While we already know how to control the LED's on the Pico, our main interest is in using the Pico to interact with other things. Let's use the Pico to power and turn on the external LED rather than the battery pack switch.

How can we create a circuit with the Pico? Electric current flows into the Pico from the USB cable and can be channeled by the Pico to flow out through nearly any pin in a great variety of ways depending on how the Pico is programmed. We can pick up the current from a pin, pass it through our LED and then we need to send it back where it came from in order to complete the circuit. Where we send the current when we are done with it is often called ground. The ground pin on the Pico is the leftmost pin on the bottom labelled Gnd in Figure 3.6. You can get paper worksheet copies of the Pico pinout diagram from your teacher whenever you need them. After we bring the current in our circuit to ground, the Pico sends it back up the USB cable.

Before you set up this or any other circuit, make sure your *Pico is disconnected from the USB cable* so that it is not powered. It is easy to put things in the wrong place. That won't matter if there is no power, but if the Pico is powered you could short it out. Set up the circuit shown below in Figure 3.7. Notice that it doesn't matter whether the resistor comes before or after the LED, it still limits current in the circuit and protects the LED. When you are sure everything is set up correctly, attach the USB cable and connect to the Pico via WIDE.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270LED2.png" width="100%" alt="LED Circuit 2" hover="LED Circuit 2">

To turn on the light you could use `digitalWrite(A8,1)` as with the onboard LED's, but this time let's use `analogWrite(A8,1)` instead. The analog function gives you the option of setting the value anywhere between 0 and 1. Try putting different values in. What effect does the value have on the LED? This is point at which you should attempt **P>3.2C**.

<!----><a name="3.3"></a>
## 3.3 Sensors & Time

### *• Reaction Timer*

The goal of this unit is to be able to build a self-contained device that can record data from sensors. To achieve this we will need to look at sensors, ways of handling time and ways of storing data called arrays. Our preliminary project however will be to make a reaction timer in which we will learn something about time functions and sensors. A reaction timer is a device that records how long it takes for the user to react, for instance, how long it would take the user to press a button after they saw a light. Since people can get rather competitive about this sort of thing, it is best that we don't use the button on the Pico itself, we don't want them damaging the processor. Instead, we can set up our own buttons on the breadboard in a safer location. A button is a sensor, just a very simple one.

This would be a good point to think through this project and develop an **algorithm**. An algorithm is a sequence of steps used to solve a problem. Watch this [TedEd](http://ed.ted.com/lessons/your-brain-can-solve-algorithms-david-j-malan) video for examples. Our problem is measuring someone's reaction time. You have the following to work with that you can program from your Pico: 1 red and 1 green LED on the Pico, 2 external buttons (button 1 and 2), a stopwatch inside the Pico, and the console for showing results. What would a reaction timer need to do and in what order? How would you use the 2 buttons and the lights?

Now that you have thought through the process, we can get down to the details of buttons and clocks.

### *• Buttons*

![ Tactile switch](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/tactileswitch6mm.png "Tactile switch")

We will use a simple button called a tactile *switch*. They come in all sorts of sizes, colors and shapes. In Figure 3.11, pins that are on the same side of the button (1 and 3, 2 and 4) have no contact until the button is pushed, at which point all four pins are connected. Since the button is square, you have to pay attention to how your are placing it on the breadboard. There should be 2 breadboard holes between pins 3 and 4. Set up a couple of buttons on your breadboard as shown below.

Be sure to have the pins coming out of the switch horizontally, not vertically and be sure that the jumper wire is on the same row as the button pin, not the corner of the button housing. When the button on the left is pushed, it will create a circuit between the Pico pin B6 and Gnd. The other button will connect the Pico pin B7 to Gnd.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ReactionTimer1.png" width="100%" alt="Reaction Timer Buttons" hover="Reaction Timer Buttons">

On the Pico, most pins can be set to *watch* if a circuit between the pin and ground has been closed using just a couple of functions. The first function is `pinMode (pin, "input_pullup")` where pin is the alphanumeric for the pin you are using in the circuit. For instance `pinMode(A8,"input_pullup")` would set up pin B6 to detect if it was connected on a circuit with the Gnd pin. *Pullup* means that the pin is set to a high voltage, that is, it has been "pulled up" and if it gets connected to Gnd the voltage will fall and that change can be detected by the Pico. The second function is `setWatch()`. This function simply watches for some event to happen, like a falling voltage on pin B6, and then carries out some function when it detects the specified change. The syntax is a little tricky but it goes as follows:

```javascript
pinMode(B6, "input\_pullup");
setWatch(function() {
	console.log("B6 BTN");
}, B6, {repeat:true, edge:'falling', debounce:50});
```

The result of these statements is that the Pico watches pin B6 for a falling voltage and if it sees one it sends the string "B6 BTN" to the console. Setting the `repeat` property to true tells the Pico to continue reporting voltage drops on B6. If we set `repeat:false`, it would only do it once. The function that is declared in `setWatch()` is carried out whenever the voltage on B6 drops, that is, whenever there is a circuit to Gnd. You can write as many commands inside the function braces { . . . } as you want. Notice that the function called by the `setWatch()` has no name.  It is known as an **anonymous function**. 

It is also important to understand that we are now dealing with an **asynchronous** event, that is, we don't know when it will happen.  We've already dealt with asynchronous events when we used `prompt()` and `alert()`, but in those cases our programs waited for a user response before executing the next line.  In our present situation, the rest of our code will continue to execute while we are watching for pin B6 to drop. At whatever point B6 drops, the function in the `setWatch` will run.  JavaScript is *single-threaded*, that is, it can only do one thing at a time, so if B6 drops while our program is doing something else, it will run the function as soon as the processor is idle. The function inside the `setWatch` is called a **callback** function. The name callback comes from the idea of asking someone to do something and to *call* you *back* when they are finished.  You don't know how long it will take (asynchronous) but you can carry on with what you are doing while you are waiting.

The debounce is necessary because these mechanical switches tend to bounce and therefore create multiple contacts even though from our human perspective there is only one. As usual, in the curly braces { . . . } you put whatever instructions you want carried out when the button is pushed. Use B6 as a reset button and B7 as the reaction response button.

*Part 1*: set up your board and write the code so that a `console.log()` indicates which button has been pressed.

### *• Date object*

While we still haven't formally studied objects (a topic for Chapter 4), we have been using them and their methods. We will do this again because this is how JavaScript deals with time. In order to create a reaction timer, we need access to the Pico's clock and JavaScript methods that handle time.

JavaScript has a Date object with several useful methods. The Pico recognizes a subset of those, but still plenty for our purposes. Type `Date.now();` into your WIDE console. You get a very large number which is approximately the number of milliseconds since midnight 1/1/1970. And how might your Pico know what time it is? In [non-volatile](http://www.vikingtechnology.com/uploads/nv_whitepaper.pdf) *memory*, the Pico stores what it believes is the number of seconds since the beginning of 1970. An accurate number is put there at the time the Pico is manufactured and it continues to update that number whenever it is under power and its internal clock is going. When the Pico is not powered, its clock is not "ticking" and so it loses accuracy with regard to the date number. Whenever the Pico is connected to a computer, it updates its date based on the computer's date. There is a setting in the WIDE at **Settings → Communication → SetCurrentTime** that toggles this auto updating feature on and off. Make sure it is on. Most of the date methods depend on the stored number being accurate, which means it needs to be updated frequently and any programs that need to know what the real date is need to have the Pico remain powered during the entire execution period of the program.

Now to the Date object and its methods. Most of the Date methods require the construction of a Date object first. You would do something like:

```js
let ThisTime = new Date();
```

The name of the variable is up to you. From there you could use dot notation to access various Date methods like:

```js
ThisTime.getSeconds();
ThisTime.getMonth();
```

Put them in a `console.log()` to see what they give you. Then try `ThisTime.toString()`. Is it correct? Do you know what the parts stand for? GMT is [Greenwich Mean Time](https://en.wikipedia.org/wiki/Greenwich_Mean_Time) which is the time it is in Greenwich, England. For historical reasons, that is now considered Universal Time Coordinated (UTC) and that is the time zone your Pico is set to work in. Our timezone in Washington is Pacific Time and it is 8 hours behind GMT/UTC. To get the correct time and date we can do the following:

```js
let timeZone = -8;
let ThisTime = new Date(Date.now()+3600000*(timeZone+1));
console.log(ThisTime.toString());
```

Using this parameter in the new `Date()` constructor allows us to modify the milliseconds since 1970 to match our timezone. The `+1` in line 2 is to compensate for daylight savings time. Once `ThisTime` is adjusted, we can expect it to reliably produce time and date information in our local time. Can you think of where the 3,600,000 comes from?

Interestingly, the `Date.getTime()` method that we will use in our reaction timer does not require us to use the `new Date()` constructor. This is not universal in JavaScript but to use the `getTime()` method in the Pico environment, you can just do `console.log(getTime());` or let now = `getTime();` without ever creating a `new Date()` object. What you get is the milliseconds since 1970 and if all we care about is keeping track of how much time has passed, it doesn't really matter whether that number is correct or not, or what our timezone is. Your code will be much cleaner in the Pico environment if you do NOT create a `Date()` object. Just call `getTime()` whenever you need a reference to the current time.

Consider this pseudocode:

 - get start time and turn light on
 - watch for reaction button then get button press time
 - reaction time = (button press time - start time)
 - report reaction time
 - watch for reset button then turn off light
 - prepare to do again

In this situation, we really don't care how many milliseconds the start time is, we just care about the difference between the start time and the end time.

*Part 2*: Implement the pseudocode on your reaction timer, and make the left button (B6) a reset button that sets it up again. You will need to somehow make the time of the light turning on random so that we actually measure reaction time and not anticipation or rhythm. You may want to make use of the `setTimeout()` function. It is like a one-time `setInterval()` function. Look it up.

![Nokia 5510 Ad](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/nokia5510.jpg "Nokia 5510 Ad")

*Part 3*: Our goal is to make our reaction timer an independent device. Sending the score to the console is fine if you have a computer handy, but it would be better to have it be part of our device itself. Your teacher will give you a Nokia 5510 screen from an old cell phone. *LCD* stands for [Liquid Crystal Display](http://www.explainthatstuff.com/lcdtv.html). It is a very low power screen ideal for our purposes.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ReactionTimer2_bb.png" width="100%" alt="Reaction Timer with LCD Screen" hover="Reaction Timer with LCD Screen">

Put the LCD pins into breadboard row A just above your Pico. Be sure that the LCD pin marked Gnd is in line with Pico pin A5. We will need some special commands to make this work. An LCD is a fairly sophisticated device. Nearly all of this code has already been written for us and you don't need to understand it all. Here is the code you need to send info to the LCD screen:

```javascript
digitalWrite(A5,0);
digitalWrite(A7,1);
digitalWrite(A6,1);
function writeScore() {
	d.clear();
	d.setFontVector(40);
	d.drawString(score,(d.getWidth()-d.stringWidth(score))/2,0);
	d.flip();
}
let spi = new SPI();
spi.setup({ sck:B1, mosi:B10 });
let d = require("PCD8544").connect(spi,B13,B14,B15,function(){
		writeScore();
	}
);
```

Line 1 drops the voltage on Pico pin A5 to 0 so it can act like a Gnd for the LCD screen. That is why we put the LCD Gnd on pin A5.

Line 2 gives power to the LCD via pin A7. You can see the marking on the LCD for this pin is VCC, or VCC which has a complicated history but most often indicates the connection to the power line when looking at electronics diagrams.

Line 3 gives power to BL on the LCD which stands for backlight. You don't actually need to power up the backlight to see the display. If you were running off of a battery, it would be better to leave this zero. Try it both ways.

The function `writeScore()` is just a demo. There is nothing sacred about the name writeScore, you can make it whatever you want and other variables can be changed as well. The important things are the d.method lines. The last line of code brings in a set of methods associated with something called the d object. We will learn about objects in the next chapter. The methods associated with the d object are:

**d.clear()** clears the screen.

**d.setFontVector(40)** sets a size 40 vector font. You can change the number to get different sizes of font.

**d.getWidth()** gets the width of the screen.

**d.stringWidth()** gets the length of the string.

**d.drawString(string,x,y)** prints the string in the current font starting at (x,y) with (0,0) being the top left corner. The calculation done with the widths is for centering the text on the screen. You could just use 0 for x and y.

**d.flip()** is a special function for the Nokia 5110 that makes the text appear. The drawString() method sets up the text to be displayed but doesn't actually draw it on the screen.

There are many other graphic methods available for the Nokia 5110 to draw circles and rectangles and do rotations, etc. that can be found in the [Pico documentation](http://www.espruino.com/Reference#software).

The line `let spi = new SPI()` sets up a [Serial Peripheral Interface](https://learn.sparkfun.com/tutorials/serial-peripheral-interface-spi). Basically it is an agreement between the Pico and the LCD about how they will talk to each other. It's beyond the scope of this class, but understand that communication between digital devices happens very quickly and has to be precise and they each must follow agreed protocols in order for the data to be received accurately.

The `spi.setup()` says that the Pico will use B1 for it's sck (Serial ClocK) and B10 will be used for its mosi (Master Out Slave In) communication. Again, the full explanation of this is beyond the scope of the course, but it's all necessary for successful communication between these digital devices. In most situations, the microcontroller will be the *master* and the peripheral device will be the *slave*.

Finally in line 12, `let d = require("PCD8544")` etc. employs a Pico function `require()` that has it go on the internet and download a module called PCD8544 in order to create the d object. If you'd like to look at the module, you can see it [here](http://www.espruino.com/modules/PCD8544.js). You will understand some of it. A module is a bit of code written by someone else, in this case the developer of the Pico (Gordon Williams), in order to make it easier for us to build things with the Pico. It contains low level commands and Nokia 5110 specific stuff that would be pretty hard for the average user to come up with, including some hexadecimal things that could be directly turned into those 1's and 0's that all digital devices ultimately understand. This command line further goes on to specify the function of pins B13, B14 and B15 which are also connected to the LCD.

In line 13, you find a call to the function `writeScore()`. You should always call a function that does something with the LCD at the end of the `require()`. Fortunately, you can readily use lines 10 through 15 as boilerplate. If you want to use an LCD, you need these and you don't need to change them. Just use them and forget them.Add to you code whatever necessary to give feedback through the user via the LCD screen. Consider using more than one line on the LCD (Hint: the last parameter (y) of `drawString(text,x,y)` is the vertical location. You might also consider tracking the low time/score.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ReactionTimer3_bb.png" width="100%" alt="Reaction Timer with Battery Pack" hover="Reaction Timer with Battery Pack">

*Part 4*: If you succeeded with getting everything to work in the first 3 parts, you are now ready to cut the umbilical cord and set your reaction timer free. Make sure the latest version of your software has been sent to the Pico and then type the command `save()` in the console (right side) and hit return. You will see "Erasing Flash" and some other stuff and then Done! The `save()` function tells the Pico to store the program in non-volatile *flash memory* which will remain even when the power is off. The Pico has 384KB (kilobytes) of [flash memory](http://www.explainthatstuff.com/flashmemory.html). A typical digital photo can be several megabytes so we can't go storing a bunch of photos or sound files on our Pico, but it's plenty for the text files that we use for programming. HTML files are also text files.

Disconnect your Pico in the WIDE and then physically disconnect your Pico at the USB cable. Attach a turned off battery pack as shown.

Make sure the red battery lead is going to the BAT IN pin on the Pico, it's the first pin on the top left (opposite the GND pin). REMEMBER TO HAVE ALL POWER OFF WHEN ATTACHING THE BATTERY OR CHANGING WIRING. BE CAREFUL NOT TO DRAG THE BATTERY LEADS OVER THE TOP OF THE PICO.

Turn on the battery pack. You should see your Pico give the red power up flash and you should see your LCD screen light up (unless you turned off the backlight). Unfortunately, your program won't make anything change on the LCD screen. Your program is in memory and the Pico is powered up and ready to go, but the Pico doesn't know it's supposed to run the program. You probably have tons of programs on your PC, but your computer doesn't run them unless you tell it to. This is the same situation.

The solution to our problem is the `onInit()` function. The Pico is set up to look for a function called `onInit()` and run it any time after it is powered up, that is, INITialized. To make it run your program you need to wrap your whole program inside `function onInit() {your program goes here}` and then save it to the Pico by typing `save()` into the console. When you run it just on battery power, and you switch the battery on, your program will start running.

Please note that you don't always need to wrap your entire program in the `onInit()` function. In some cases you may need functions or global variables outside the `onInit()` function in order for everything to have the right scope. These variables or functions outside of `onInit()` will still be loaded and available when you `save()` the program to your Pico, but only the `onInit()` function will be run automatically when the Pico is powered up.

Add a battery pack, save your code and take it out and let some users try it. The user interface of a software or hardware product is called its UI, the user experience is called the UX. What sort of user responses did you get that could improve the UI or UX of your design?

Part 5: Enhance your program to use an audio alert.  Perhaps people react faster or slower to sound. Connect a speaker as shown below.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ReactionTimer4_bb.png" width="100%" alt="Reaction Timer with Speaker" hover="Reaction Timer with Speaker">

It doesn't really matter whether the red or black wires are switched, but to be consistent, black should be on the Gnd side. [Speakers](http://www.edisontechcenter.org/speakers.html) work a lot of different ways and ours is called a piezoelectric speaker. For our purposes it's enough to know that if you *oscillate* the voltage on a speaker at a frequency of 500 Hz (*Herz* is cycles per second), then the speaker will vibrate and make a sound at that frequency. 500 Hz would be something like a female voice in pitch. Since our speaker makes a circuit between B3 and Gnd, if we fluctuate the voltage at B3 we can get a sound out of the speaker. The command syntax to oscillate the voltage is similar to lighting LED1:

```javascript
analogWrite(B3, 0.7, {freq:500});
```

Using `analogWrite()` gives us more output options, like frequency. The 0.7 refers to what percent of the maximum output voltage we use for the high voltage in our oscillation. In this case 70%. The maximum voltage is 5 volts, so that means the voltage will oscillate between 0 and 3.5 volts. The higher the maximum voltage, the louder the sound, but you probably won't notice much difference until the voltage is very low. You could improve your volume control by adding a resistor in line with the speaker.

The higher the frequency the higher the pitch. If you want more information about producing sounds on the Pico, take a look at Appendix 3.

<!----><a name="3.4"></a>
## 3.4 Arrays & Data Logging

> **Target**: Be able to create a self-contained microprocessor device that can access sensor data, log it to memory with arrays and retrieve it.

Suppose we wanted to store all of the reaction times rather than just keeping track of the fastest one. The Pico has flash memory that we can write to and we could make a whole bunch of variables and store a value in each one, but that is very inconvenient. Instead, we can make use of a JavaScript object that is specifically designed to store data - the array.  For additional background information on arrays and other data structures, take a look at [Crash Course Computer Science episode 14](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

Follow along with these examples by pasting the code in your WIDE. To create an array you can write something like

```js
let myArray = [];
```

Notice we are using square brackets for the first time. The variable name is up to you and does not need to include the word Array. To store things in `myArray[]` we can write:

```js
myArray[0]="bob";
myArray[1]="sue";
myArray[2]="ted";
```

We have as many slots in `myArray[]` as we want to make and we can put any type of data in the array that we want. It is assumed that our first spot will be the zero spot, so get used to counting with zero as your first number. In computer science we typically start counting with zero not one.

To get the data back out we can write:

```js
console.log(myArray[2]);

> ted
```

There are also array properties and methods that come in handy, for instance

**myArray.length;** The length property returns the number of elements in the array, in our case, 3. If you're following along in your WIDE, you'll need to put this property in a `console.log()` to see the result and avoid an error.

**myArray.push("ann");** would make `ann` the new last element in the array and return the new length which would be 4.

**myArray.unshift("pat");** would make `pat` the new first element in the array and would return the new length which would be 5.

**myArray.indexOf("sue")**; would search the array looking for `sue` and return 2, which is now the location of `sue` in our array. To see the 2, you need to put the method in a `console.log()`.

**myArray.sort();** would rearrange the items in the array in alphabetical order: "ann", "bob", "pat", "sue", "ted"

There are several other interesting array methods that you can look up on w3schools.com or the Espruino.com reference page.

### *• Logging at Set Intervals*

There are many situations where people would like to place a sensor somewhere to monitor something and would like to get sensor readings at set intervals like every minute, hour or second. This is called data logging.  For instance, suppose we wanted to monitor the voltage fluctuations that occur on pin A5 of a Pico when nothing is attached to it.  You could use the following code:

```js
let arrayMax = 10; //size of the array
let pinValArray = [arrayMax]; //this sets up the array
let i = 0;

function pinRead() {
  let pinVal = analogRead(A5); //read the pin
  pinValArray[i] = pinVal;     //put into the next array slot
  console.log(i + " " + pinVal);
  i+=1; //keeps track of how many times pinVal's are put in pinValArray
  if (i>arrayMax) {
      clearInterval(logger);
      console.log("FULL");
}

function dataOut() { //a function to print all the array values
  for (let j=0; j<arrayMax+1; j++) {
    console.log(j + " " + pinValArray[j]);
  }
    console.log("DONE");
}

let logger = setInterval(pinRead,100);
```

The function `pinRead()` puts the value of A5 into the next slot of `pinValArray` and it is called every 100ms by the interval timer called `logger`.  The global variable `i ` is used to keep track of how many times `pinRead()` is called and is used to stop `logger` when the array is full.

The function `dataOut()` simply loops through pinValArray[] and prints the values to the console.  It is never called in the code above, but you can call it directly by just typing `dataOut()` into the the console after running the program.

Go to **P>3.4A** to find this program and try it out and get started on the next project. In this project, you will create a data logger using one of four possible sensors: a light sensor, a temperature sensor, a distance sensor or an IR reflectance sensor. The logger will be placed in some appropriate location for an appropriate length of time, collect the data and then be retrieved and the data reported back. The following sections describe how to manage  the limited memory of the Pico, how to set up the various sensors and get data, but the overall design is up to you.

One feature of the WIDE console that is helpful is that any data that is listed in the console can be copied simply by dragging over it. No "copy" command is required.  Once you've drug over the data, you can paste it into a spreadsheet or graphing program to better display or analyze the data you collected.

### *• Memory Constraints*

The Pico, due its small physical size has very limited memory. While it has 384kb of flash, much of that is used to store the JavaScript interpreter. Then some more of it will be used to store the program to be run. What is left over is often about 80kb. Arrays can eat up a lot of memory depending on the type of data that they contain and the number of elements that they have. In order to decide how big to allow our arrays to get, we need to know a little more about memory.

80kb means 80 kilobytes, which means 80 x 1024 bytes. In computer science *kilo* doesn't mean 1000, it means 1024 ( =2^10^ ). So 80kb is about 82,000 bytes, but we'll just leave it at 80,000 bytes to be conservative and keep the numbers easy.

What can we do with 80kb? Well each byte is 8 bits. A bit stands for **B**inary dig**IT**, which means each of those 1's and 0's that the computer cares about. So we have 640,000 (80,000 x 8) 1's and 0's to work with. But what does that mean practically?

Each character typically requires 2 bytes. So the word "bob" in an array would take up 6 bytes. Let say the average word length in English is 5 letters or 10 bytes, if our array stored 8000 words, we would be in danger of overflowing our memory capacity.

In the reaction timer project, we weren't storing words, we were storing numbers. The Espruino implementation of JavaScript gives us a way to create arrays that store only numbers, and if we use integers, they only need 8 bits or 1 byte each. You can create an Int8Array as follows:

`myArray = new Int8Array(1000);`

This creates an array of 8 bit integers large enough to hold 1000 of them. You don't have to specify the size of the array (in this case 1000) when you declare it, but it's a good thing to think about and doing so also allows us to type the `process.memory()` function in the console to see how much memory will be taken up. Load a program from the WIDE into a Pico, then type `process.memory()` into the console. It will return a "free": 5021 sort of number telling you how much memory is available. The number refers to how many memory blocks are available and each block is 16 byte

8 bit integers can store numbers in size between -2^7^ and +2^7^, that's -128 to + 128 since we need 1 of the bits for the sign. If all your values fall in that range, you can save a lot of memory by storing them as 8 bit integers, rather than as characters in a standard array. For the characters "116" you would need 6 bytes. That's a 6 to 1 improvement.

If 8 bits doesn't store big enough numbers you can use Int16Array or Int32Array. If you need decimal points, then you can use Float32Array and Float64Array, but these start to eat up space too. Create some arrays. Look how the free memory changes with the size and kind of the array.

For additional background information on memory and storage, take a look at [Crash Course Computer Science episode 19](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo)

### *• Light sensor*

The light sensor available is a GM5539 **photoresistor**. It has a high resistance when the light level is low, and a low resistance when the light level is bright. By using a circuit called a voltage divider, we can create a nice range of voltage values that change with the light intensity and are within a range the Pico can monitor. The setup is given below. The resistor shown should be a 10kΩ resistor.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270Photometer.png" width="100%" alt="Photometer" hover="Photometer">

Note that the Pico is contacted at Gnd and the photoresistor is at the VDD/3.3 pin, which is 3.3V. In addition we are using a right end pin for the first time which happens to be A2. We are using this end pin hole since it allows analog input (it is an ADC or analog digital converter pin) and since it will leave the top of our Pico free for the LCD screen later. If you bend the jumper slightly, it will make solid contact in the A2 pin hole.

Now you are ready to write the code to read A2 and output the value to the console. The only function we need is something like

`let lightvolt = analogRead(A2)`

The `analogRead()` function will return a value between 0 and 1, with 1 being something like 100% of the original 3.3 input volts, and 0% being 0 volts. I say "something like 100%" because it isn't really a percentage, but the numbers spread out nicely over the 0 to 1 range, so you can think of it like a percentage. Unfortunately the numbers are not very friendly. We can do better than 8 digit decimals. Use JavaScript to convert the ugly numbers into 2 digit integers that range from 0 to 99. Note that `analogRead(A2)` will never return full 1.0 since there will always be a slight bit of resistance on the line.

### *• Temperature Sensor*

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/DS18B20.png" height="250px" title="DS18B20 thermistor" alt="DS18B20 thermistor">

We can detect changes in temperature using a sensor called a *thermistor*. For this project, instead of a simple thermistor, we will use a small chip called a digital thermometer. It has it's own program in memory, and integrated components including a thermistor. The model we will use is the [DS18B20](http://datasheets.maximintegrated.com/en/ds/DS18B20.pdf).

There is an Espruino module that we can require in the code to make it easy for us to get data from the thermometer. The following 3 lines of code will send the current centigrade temperature to the variable temp if the data line of the DS18B20 is connected to pin A8 of a Pico.

```javascript
let ow = new OneWire(A8);
let sensor = require("DS18B20").connect(ow);
let temp=sensor.getTemp();
```

The first two lines only need to appear once in the program. The last line can be called as often as you want to check the temperature. The breadboard layout would be as shown below.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ThermometerDS18B20.png" width="100%" alt="Thermometer" hover="Thermometer">

There are a couple of aspects of the layout that require caution:

First, the DS18B20 must be facing the correct direction or you will fry it. Notice that it has a flat side with microprint and a rounded side opposite. The flat side must be facing toward the ground side of the bread board, that is, it must be facing you as you look at the breadboard oriented as it is in the diagram. If you have it backward and apply power, it will fry the DS18B20. If you smell something burning when you power it up, yank out the USB cable immediately.

Second, you need to notice the 4.7kΩ resistor connected between the 3.3 volt power line and the data line going to pin A8. This functions as a pull up resistor as you used in the Loop game in section 3.2, but this time we use an external one rather than programming the Pico to create an internal one. This is a requirement of the DS18B20.

Third, the data is floating point decimal which can take up quite a bit of space depending on how many data points you take. You may wish to round the data off and store it in an Int16Array. Can you come up with a way to maintain 1 or 2 decimal places even though you use an integer array?

### *• Distance Sensor*

To measure distance we can use an infrared reflectance sensor called a [Sharp GP2Y0A21YK0F](http://www.sharpsma.com/webfm_send/1489). It can give reasonably accurate distances between 4 and 24 inches. The distance accuracy depends on the surface, shape and color of the object since the sensor is measuring the strength of the energy being bounced back to determine its distance. If you are trying to sense an object that will be moving horizontally, it is best to mount the sensor vertically. *In order to adequately power the sensor, you need to have the battery attached and on*, even if you are still using the USB cable. Make sure you have the black wire to ground and the red wire to power -- if they are reversed you will fry your sensor.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270IR2Y0A21.png" width="100%" alt="IR Distance Sensor" hover="IR Distance Sensor">

The diagram shows a breadboard set up to read pin A5, but you can use any ADC (**A**nalog to **D**igital **C**onverter) pin you like to read the output from the sensor. Check your Pico diagram to see which pins are ADC.  You need to use an ADC pin because they are the only pins on the Pico that can read analog input voltage and convert it to a digital signal for processing by the Pico.

The following function can be used to convert the output from the sensor roughly to inches. The conversion formula is a little scary because the output of the sensor is not linear.

```javascript
function getIr() {
	let raw = analogRead(whichever pin you use);
	let dist = -138.05*Math.pow(raw,3) + 293.98*Math.pow(raw,2) - 210.28*raw + 54.4;
	return dist;
}
```

You can write your own conversion function. If you've had Precalculus, try taking raw data from A5 and make a table on a TI graphing calculator in the form L1=voltage and L2 =distance, and then do a cubic (or some other) regression. Note that the voltage from the sensor at A5 will always be between 0 and 1 and will increase as the sensor gets closer to the object. Also note that the sensor doesn't actually measure distance, rather it reports the amount of IR energy reflected back to it, which gets less as distance increases. But, the color and substance that is reflecting the IR can also affect the energy, and therefore the perceived distance.

The data from the sensor is floating point decimal which can take up quite a bit of space depending on how many data points you take. You may wish to round the data off and store it in an Int16Array (see Memory Constraints section earlier in this chapter). Can you come up with a way to maintain 1 or 2 decimal places of information even though you use an integer array?

### *• IR Reflectance sensor* 

Sometimes we don't need to know how far something is, we really just want to know if an object is close or not, for instance whether a sheet of paper is in a tray or not, or whether a door is closed or not. In these cases we can use an IR reflectance sensor. Like the IR distance sensor above, it sends out an IR beam and watches for how much light is bounced back. Unlike the distance sensor though, it is only useful for close range detection, typically less than 1 cm. It is also often used to distinguish between light and dark colors since light colors reflect more than dark colors. The advantage of these sensors over the IR distance sensor is their small size and low cost. If you have seen Mini-sumo bots or line-following robots, they use these simple sensors to distinguish between the black of the out-of-bounds or line and the white space.

The following functions can be used to poll a Pololu QTR-1RC sensor on pin A5 every half second. Any pin can be substituted for A5, not just ADC pins. The output of the QTR-1RC is already digital. The `getLight()` function works by pulling pin high using `pin.set()`. Then it reads pin until the voltage drops using `pin.read()`. The `pin.read()` function is either 1 or 0. While waiting for pin to drop, c is incrementing. If an object is close, the reflectance will be brighter, which makes pin drop faster. This will result in a smaller value for c. So a small c value means an object is present or has a light color and higher c value means nothing is close or it is dark.

```javascript
function getLight(pin) {
	let c=0;
	pin.set();
	while(pin.read()) c+=1;
	return c;
}

function report() {
	let IRval = getLight(A5);
	console.log(IRval);
}

setInterval(report, 500);
```
<!----><a name="3.5"></a>
## 3.5 Motors & Robots
-------------------------------

> **Target**: Be able to control motion and motors by programming a microcontroller using asynchronous techniques.

### *• Motors*

In Chapter 3 we have been using the Pico microcontroller. So far we have used it to control speakers, lights and an LED screen, as well as using it to collect information from various sensors. In this section we will use JavaScript to program the Pico to control motors so that we can create motion.

The kind of [motor](https://learn.sparkfun.com/tutorials/motors-and-selecting-the-right-one) that we will use is a DC brush motor. These are the cheapest and simplest motors available. To make one run, all we need to do is connect it to an appropriate power source. Since it is DC (**direct current**), connecting it to a wall outlet would be a bad idea. Power coming from wall outlets is AC (**alternating current**). Instead, we can use our battery pack. Batteries produce direct current.

Get a robot chassis. The word **robot** is an English corruption of a Czech word *roboti* coined by K. Čapek in his 1921 play *R. U. R.* Čapek's roboti were not so much mechanical devices as organic androids, but the play was popular and the term became part of the global language meaning *something that is constructed by people but that can act on its own to some degree*.

![Robot comic](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/robotcomic.jpg "Robot comic")

Get your battery pack and a wheel/motor unit. Connect the battery pack to one of the wheel motors using your breadboard: red to red, black to black. You should see the motor spin when the battery pack is switched on.

One of the problems with this sort of motor is that it creates an electromagnetic field when it is running and then when it stops, that field collapses and shoves electric current back the other way through the power wires. This is not a problem when the motor is connected to just a battery, but if the motor is connected to a microcontroller, it can damage the IC. So we can't just hook up the motor to a Pico pin and turn the pin on and off to drive the motor. It would work, but we'd likely damage the Pico in the process. Instead we will use a separate IC that is designed to drive motors. It has diodes and other circuitry to protect the Pico. The chip we will use is the [L293D motor driver](http://www.robotix.in/tutorial/auto/motor_driver/). The L293D actually has 4 different power outputs so it could drive 4 different motors, but we will set it up so that each of our motors uses 2 outputs: one for forward and one for reverse.

Use the following layout to connect your Pico, the L293D, the battery and the motors on the robot chassis. Take your time and be careful. This is the most complicated wiring you have done. **Make sure the <u>notch end</u> of the L293D is pointed <u>toward</u> the Pico**. Use plain wire to make short jumpers for all of the connections to the power and Gnd rows on the breadboard - these are the red and black jumpers on the Fritzing layout below. Install these first, it will keep the spaghetti to a minimum.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270Robot.png" width="100%" alt="Motors and L293D Driver" hover="Motors and L293D Driver">

Note that the yellow motor leads in the diagram are red on the motor and the green motor leads in the diagram are actually black on the motor

In addition to the layout, it is helpful to know what the pins on the L293D are doing. As you can see in the diagram below, the L293D has 16 pins. They are split up into 4 equal sections each containing an INPUT in , an OUTPUT pin and a GND pin. The INPUT is connect to a Pico pin which can turn on and off the OUTPUT by going high or low. In addition, there is a Vss pin which is the power for the L293D chip and an Vs pin which is linked to the power supply of the microcontroller (Pico in our case). The Vss and the Vs pin can be linked to the same source, which in our case is the battery pack. Finally there are ENABLE 1 and 2 which enable the left side (pins 1 - 8) and the right side (pins 9-16) respectively. We want to enable the entire chip so we will keep both ENABLE pins high.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/L293DPinOut.png" alt="L293D pinout" hover="L293D pinout" height="225px">

If we connected one lead of our motor to an L293D output and the other lead to battery Gnd, we could turn on and off out motor. But one nice feature of our motors is that they can run in reverse if we reverse the voltage. For that reason, we will connect both red and black leads to OUTPUT's and by making one high and the other low and vice versa, we can turn the motor both directions.

The simplest way to control motors is to send a voltage high to the INPUT corresponding to the OUTPUT you want to activate. Remember, you have the red of a motor connected to one OUTPUT and the black of the same motor connected to another OUTPUT. You need to have one INPUT/OUTPUT high and other low. If they are both high, nothing will happen.

The first function you need to write is a `stop()` function that sets all the OUTPUTS to low. There are several ways to do this, but this will work:

```javascript
function stop() {
	digitalWrite(A6,0); //A6 is right reverse
	digitalWrite(A7,0); //A7 is right forward
	digitalWrite(B6,0); //B6 is left reverse
	digitalWrite(B7,0); //B7 is left forward
}
```

Put the robot up on its rack and turn on the battery. Wheels may begin to turn. Send the stop function to the Pico from the editor. Whether the wheels are turning or not, type `stop()` into the console to verify things are wired correctly and the function works as expected. Then figure out what a `go()` function would look like and send it along with `stop()` to your Pico. When you type `go()` in the console, both wheels should go forward. Note that the `go()` function simply sets the pins high once, but they will remain high, and the wheels will continue to turn until you set them back to 0 with the `stop()` function. Type `stop()` in the console to stop the wheels. Write and test functions for `reverse()`, rotate `right()` and rotate `left()`. Turning can be accomplished by stopping one motor while driving the other, or you can turn even quicker by reversing one motor while the other is in forward. It is better to be able to get reproducible and precise movements than to get fast but inconsistent ones.

Put your robot in forward and disconnect it from the USB cable. Let it drive along the floor. You may notice that it pulls to one side or the other. Check to see if the wheels/motors are aligned and tightly secured to the chassis. You'll have to deal with the idiosyncrasies of your robot as best you can. As long as they are predictable, you can build in compensations.

Having a robot that drives in a straight line is advantageous. You also know that stopping a wheel on one side makes the robot turn. What would be nice is a way to slow down one motor slightly so that we could compensate for a pull to the right or left. We can do this by using `analogWrite()` rather than `digitalWrite()`. The Pico pins that we are using can work either way. An analog version of the `go()` function would be:

```javascript
function go() {
	analogWrite(A7, 1);
	analogWrite(B7, 0.9);
}
```

Use `analogWrite()` and voltage adjustments if needed to make your robot run as straight as possible and turn as consistently as possible. Traction and slippage is a factor especially on turns. Slowing things down often improves traction. Consider writing a `goslow()` and `gofast()` function.

For additional background on robots, take a look at [Crash Course Computer Science episode 37](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

### *• Preplanned Behaviors*

A good first programming problem is to get your robot to go out a certain distance, turn around, and come back to the starting location. If you try something like . . .

```javascript
go();
right();
go();
stop();
```

your robot won't do anything, since it only takes a fraction of a second to go through each function. The motor wouldn't even have a chance to start turning before all the functions have finished. What we need is a way of controlling the timing of each instruction. The simplest way to do this is with a series of `setTimeout()` calls. For instance:

```javascript
setTimeout(go, 2000);
setTimeout(stop, 3000);
```

This code would cause the robot to go forward after 2 seconds and then stop 1 second later. Keep in mind that `setTimeout()` calls are are *asynchronous*, that is, the next line of code can be run before the `setTimeout()` finishes. In this case, you can consider that both lines of code begin almost simultaneously. If you had 7 setTimeout's in a row, you could consider that all of them would start their execution simultaneously. Remember, we don't use parens after the function name inside the setTimeout because we don't want it to execute immediately.

### *• Robots and Sensors*

At this point our robot is blind. We can use sensors to give it eyes. The most useful sensor for a traveling robot is a distance sensor. Get a Sharp GP2Y0A21YK0F distance sensor and  bolt it to the *left* side of your robot chassis and facing *left* but slightly forward. Incorporate the code from the previous section on [IR reflectance sensors](#*•-ir-reflectance-sensor*) into your robot driving code. You may need to make the variable connected to the distance being sensed a global variable.  Make sure you connect the sensor to an ADC pin (A5-A7, B1) on the Pico.

Now write code that will have the robot drive parallel to a wall on its left side for 16 feet and maintain a range between 8 and 12 inches from the wall.   If your team members string together your USB cables, you can keep your robot on a "tether" so you can see console info during your trial runs, or you can have the red and green lights of the Pico turn on/off given certain sensor information so you can see what's going on. As algorithms get more complicated, sometimes pseudo-coding with a flowchart can be helpful. 

Continue with **P>3.5A**.  The section on interrupts below may be useful but is not required.

### *• Interrupts*

When programming complex autonomous robotic behaviors, it can be very helpful to have an interrupt, that is, a way of stopping one function, starting another and letting it run until it finishes, then going back to the original function. Having the interrupt run until it is finished can be tricky. 

<iframe height="100%" width="100%" src="https://repl.it/@jeffseely/Interval-Interrupt-Demo?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Consider the code above. The variable `sensor`declared in line 1 will increase in value as the program runs, starting at 0.  It is just providing changing data for the program to look at.  The `run()` function's main job is to console.log the sensor value in line 17.  But before doing that it checks for any condition that would require it to abort.  It checks for these conditions in lines 5 and 11.  In the case of line 11, if sensor is greater than 50, the whole program will terminate.  In the case of line 5 where sensor is divisible by 11, an interrupt is implemented.  Notice that in line 7, the interval timer that is calling `run()` is cleared and then an interval timer that calls `adjust()` is initiated.  If you look at the `adjust()` function starting on line 20, you can see that it has very similar code which clears the interval timer that is calling it and starts the interval timer that is calling `run()` again.  In this way functions can interrupt themselves when some condition is encountered and transfer program control to some other function, which may or may not give it back.

For another example, send the code below to your Pico. Can you see how lines 27 - 30 call the interrupt function whenever `sensor` is greater than 9? Note that the interrupt shuts down the main interval timer on line 15. Can you see at line 21 that the interrupt will continue to run for `duration`? Can you see at line 10 that the last thing `greenOff()` does is to restart the main timer?

```javascript
let state = true;
let sensor = 0;
let mainTimer = null; //needs to be a global since called by 2 functions
let interruptTime = 3000; //length of interrupt

function greenOff() { //ends the interrupt and restarts mainLoop
	console.log("greenOff");
	console.log(" ");
	digitalWrite(LED2,0);
	sensor=0;
	startLoop();
}

function interruptGreen(duration) { //turns on green LED2 for duration ms
	clearInterval(mainTimer);
	digitalWrite(LED1,0);
	console.log("redOff");
	digitalWrite(LED2,1);
	console.log("greenOn");
	console.log("for "+duration+" ms");
	setTimeout(greenOff, duration); //calls its shutoff in duration ms
}

function mainLoop() { //alternates red LED1 on and off
	sensor+=1;
	console.log(sensor);
	if (sensor>9) {
		interruptGreen(interruptTime);
		return; //Keeps mainLoop from executing during the interrupt
	}
	if (state) {
		digitalWrite(LED1,0);
		state=!state;
	} else {
		digitalWrite(LED1,1);
		state=!state;
	}
}

function startLoop () { //calls a mainLoop every 500ms
	console.log("startLoop");
	digitalWrite(LED1,1);
	console.log("redOn");
	mainTimer = setInterval(mainLoop, 500);
}

setWatch(function() {
	console.log("BTN");
	setTimeout(startLoop, 2000);
}, BTN, {repeat:false, edge:'rising', debounce:50});
```

### *• Servo Robotics*

Not all robots are mobile, most stay in one place and do a particular task. Many of these robots use something called a *servo motor*. You've used plain DC motors, but what makes [servos](http://www.jameco.com/jameco/workshop/howitworks/how-servo-motors-work.html) special is that their position can be precisely controlled and held. The servos we will use only turn 180º, but we can precisely determine where in that 180 degree range the servo moves to and how long it stays there until moving somewhere else. Servos have many applications in manufacturing as well as remote control cars, planes, DVD players, automobile accelerators. Here's a little [video](https://www.youtube.com/watch?v=bu3SPwzcocU) that gives you some additional information although not all of it applies to the servos we will used.

Unlike the plain DC motor you've been using, the servo has 3 leads: a red for power and black (brown) for Gnd and a yellow (orange) for position control. Get a servo and add it onto your breadboard as shown below. Connect the yellow control line to Pico pin A8 (or any other PWM pin you choose).

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FPicoBB270Servo2.png" width="100%" alt="Servo motor" hover="Servo motor">

The Pico is not powering the servo, it is only controlling its position via the yellow control line. The control line does not pose an electromagnetic threat to the Pico. Because of this, we don't need to use the L293D to control servos with the Pico. In order to control the position of the servo, we send pulses from B4 every 20 ms (which is 50 Hz). By varying how long each pulse lasts, we can communicate to the servo what position it is supposed to be in. Varying the width of the pulse is called Pulse Wave Modulation or PWM and most of the pins on the Pico have the capacity to do PWM The servo has its own little IC inside that is listening for PWM and knows what to do with it. For most small hobby servos, a pulse width of 1.5 ms tells the servo to go to its middle position, think of that as zero. The servo can then turn 90º clockwise and 90º counterclockwise from there. Here's the syntax for sending a 1.5 ms pulse every 20 ms:

```javascript
setInterval("digitalPulse(B4,1,1.5)",20);
```

This line sets up an interval timer to fire every 20 ms (50Hz). What it fires is a pulse on pin B4 of value 1 (high) for a length (or width) of 1.5 ms. The reason for the quotes is that we don't want the digitalPulse() function to be called immediately which the parens would require, yet we want to predetermine what the parameter of digitalPulse() are. The quotes allow us to work around this problem. Another work around would be to assign the digitalPulse() function and its parameters to a variable name outside of the setInterval() and then just call the variable name without parens. What we would like to do, however, is be able to easily change (*modulate*) the width of the pulse, so the following would be even more helpful:

```javascript
let pw = 1.5;
setInterval("digitalPulse(B4,1,pw))",20);
```

Paste this into the WIDE and send it to your Pico. Now you should be able to type `pw=0.6`, etc. into the console and move the servo. Now we have a couple of problems. One is that it is easy to put too large or too small of values in for pw which is not good for the servo, and the other is that it is hard to see where the servo is rotated by just looking at its shaft.

To solve the first problem we can build some protection into our setInterval() call as follows:

```javascript
setInterval("digitalPulse(B4,1,E.clip(pw,0.6,2.4))",20);
```

The `E.clip()` method is not standard JavaScript. **E** in this situation stands for **Espruino** and `E.clip()` is one of a number of methods written specifically to deal with issues that arise with microcontrollers. One of the advantages of JavaScript is that there are many libraries of functions and modules that have been written for the various environments in which it is used. What the `E.clip()` method does is to confine the value of the first parameter `pw` between the values of the second two parameters, in this case 0.6 and 2.4. `E.clip()` "clips" off anything that is outside the range that we want and so this protects our servo from inappropriate values. The normal values for small hobby servos would be between 1.0 and 2.0 with 1.5 being the middle, however by experimentation with our particular servos, the 0.6 to 2.4 range has been established as safe. A challenge for this section is to create an interesting robotic application of a servo motor. You are encouraged to use sensors and LED's. You may also use a DC motor if there are some extras available.
