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

[Replit.com](https://Replit.com/): is an online programming environment we use for beginning programming and for submitting assignments. It is not browser specific and there is nothing to install.

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

------

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

Our computers though, don't know JavaScript or any other human language.  Computers really are sets millions of carefully arranged [switches (transistors)](http://www.explainthatstuff.com/howtransistorswork.html).  Switches can be either on or off. One or more switches can be connected to other switches to turn them on or off.  By creatively configuring these switches, computer scientists have found ways of getting them to do mathematical calculations like adding.  Furthermore, they have found ways of getting them to do logical calculations, such as `IF A > B, then do C`.  By sequencing logical and mathematical instructions, computer scientists have created programs that can do amazing things.

If you are interested in the guts of a computer - how it physically works, watch the [Crash Course Computer Science series](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo) episodes, especially 1 thru 8.  They are only about 10 minutes each so you could easily binge them on a weekend.  Specific episodes will be noted throughout this text.  While they cover topics not required for this course, they do provide useful background that can help you better understand what is going on.

> *In one sense a computer is only the transistors and the connections between them, but describing it like this loses something in the process. You can't really understand the computer unless you understand its functional relationships, what it's trying to accomplish, and the purpose that it serves to its human creators.*
>
> *--Bill Newsome*

Using the building blocks of mathematical and logical instructions, computer scientists have found ways to get switches to do amazing things, but since it all comes down to switches being on or off, we have to program computers in on's and off's.  We often call these on's and off's 1 and 0 and refer to them as [**binary**](https://learn.sparkfun.com/tutorials/binary) code.

![Translating a High Level Language Into Binary](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/languagelevels.png "Translating to Binary")

We will write programs in JavaScript using English words and mathematical symbols that we are familiar with. JavaScript is called a high level language since it is far removed from the actual 1's and 0's that computers run on. Our JavaScript program will be handed off to another program that turns it into binary for the computer to actually execute.  In JavaScript, this conversion program is called an [*interpreter*](http://voidcanvas.com/is-javascript-really-interpreted-or-compiled-language/).  In other languages, it may be called a *compiler*, as in the diagram above.  For more information on this whole process, there's a wide ranging but very interesting article on coding/programming by Paul Ford [here](http://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/#grabbag). Chapter 2 of the article is the most relevant part.  You can also watch [Crash Course Computer Science episode 11](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

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

> **TARGET**: Be able to use the Espruino WebIDE to write and run a program

Follow your teacher's instructions to install the Espruino WebIDE and connect your Espruino Pico.  The Espruino WebIDE is a software environment that allows you write programs in JavaScript.  It then turns your program into something a computer can understand, sends to the code to the Pico and gives the results back to you. The REPL in the name Replit.com stands for Read Evaluate Print Loop. REPL's are simple programming tools that programmers use, and while Replit.com started out as being fairly simple, it has developed into an integrated development environment (IDE).  It is quite possible to write programs with just a text editor, but REPL's and IDE's are very useful.

The WIDE will give you 3 windows.  On the right you will find the assignment instructions from your teacher. The top left window is the *editor* where you write your program, and the bottom left window is called the *console* and it is where you can get information back from your program run.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/EspWebIDE.png" width="100%" alt="Replit.com window">

The 3 line hamburger menu in the upper left corner gives you choices mostly about how your screen looks. The green submit button at the upper right is what you press when your program is working properly and you are ready to turn it in.

It is traditional for a first program to be something called "Hello World". Type the following statement in the console (bottom left).

```javascript
"Hello" + " " + "World";
```

This is a program. It doesn't do much, but it's a start. In this book, code examples like `"Hello" + " " + "World";` will be set in a monospaced font similar to what is used in Replit.com and also placed in a light grey box. It will make the examples easier to follow and it will make them easier to copy and paste.

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

> **Target**: Be able to use the Replit IDE to create proper variables, request user input and provide output to the user. 

Follow your teacher's instructions to log in to Replit.com.  The REPL in the name Replit.com stands for Read Evaluate Print Loop. REPL's are simple programming tools that programmers use, and while Replit.com started out as being fairly simple, it has developed into an integrated development environment (IDE).  It is quite possible to write programs with just a text editor, but REPL's and IDE's are very useful.

Replit.com has an IDE similar to the Espruino WebIDE: files on the far left, code in the middle, console on the right. Complete project 1 according to your teacher's instructions.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/ReplitHello1.png" width="100%" alt="Replit.com window">

To this point we've been poking around at a computer as though it is some sort of calculator with a full [QWERTY](http://gizmodo.com/why-we-still-use-qwerty-keyboards-even-though-theyre-a-1643855077) keyboard and a big screen. Not too useful. In order to write useful programs, we need **variables**. Variables in computer programs are pretty much like variables in algebra. They "contain" values and those values can change. It is perhaps a better metaphor in computer science to say that the variable *points to* a value rather than to say it *contains* a value, but for an introductory programming course, "contains" works just fine and it keeps it consistent with your math class concept of variables.

In JavaScript programming there are a variety of ways to create variables. This is the standard way:

`let firstNumber = 7;`

`let` is a **reserved** word that JavaScript uses to indicate that the word after it is a variable name. Don't try to use `let` for anything else. It is a reserved word and JavaScript will complain if you do. Look at the list of reserved words [here](https://www.w3schools.com/Js/js_reserved.asp). The "=" puts the number 7 into the variable `firstNumber`. If you don't assign a value to the variable, JavaScript will assign the value `undefined`. It is much better to assign an initial value because it tells us what type of variable you intend it to be and it helps us find errors as we read through the program. Let's take it a little farther with the four line program below. Go to **P>1.3AB Full Name** in Replit.com and paste the first 4 lines below into the editor.

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

Copy and paste the following in the Replit.com program window for **P>1.4C Next Age**:

```javascript
let age = prompt("What is your age?");
let nextAge = 50 + age;
alert("In fifty years you'll be " + nextAge);
```
Notice that the colors are not the same between this text and Replit.com. There is no standard color scheme for *syntax highlighting*, you just have to get used to however your environment does it, unless you are allowed to personalize it.  At present, Replit.com does not let you choose the syntax highlighting colors. Run the program, but first, try to predict what it will do.

Replit.com shows you a dialog box asking for your age. If you respond, the program will continue and tell you that in 50 years you will be `nextAge`. But it will say you are over 5000 years old! What is going on here?

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

Replit.com provide some nice editing and formatting features.  If you right click on a selected section of code, you have the option to format it, that is, it will automatically indent correctly.  This is very helpful when trying to find errors.  If you right click a variable name, you have the option of changing all of them.  There are many other helpful options as well in the command palette.

Finally, please understand that while we are using the Replit.com environment to learn programming, if we were to use the same code on a webpage, the web browser would also produce prompt and alert boxes for input and output.  The code we learn in Replit.com will be useful in more realistic situations like web pages.

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

will produce the value true. Why? Experiment in Replit.com to see if your reasoning is correct. There are other logical operators such as >= which is "greater than or equal to", and != which is "not equal to", and == which is "equal to". The reason for the double equal sign is that the single equal sign is already used as the assignment operator.  In many cases the triple equal sign is preferred since it checks not only value but type. Try making some true or false statements with those operators.

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

------

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

In Replit.com, open **P>2.1C** and paste in the **birthYear** code. Use this code as a template. Make your own variations on the program that ask the user for input and respond in different ways depending on what input the user gives.

<!----><a name="2.2"></a>
## 2.2 The WHILE statement

Another way to control programs is by using a while statement. Suppose in the previous program, we were concerned that the user might not put in a reasonable year of birth. We could use a `while` and an `if` statement combination to check and repeat until the user did enter a reasonable year.

![ Figure 1.C Replit.com sample program](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/fig2.2sample.jpg "birthYear program part 2")

Carefully type the program into **P>2.2C Input Checker** in Replit.com (you can copy and past it). Pay attention to the colors. If they aren't similar to what is in the example, you've typed something wrong.  If you have a black background editor, you can switch to white for this example. Change all the 2015's to the current year. Run the program and respond that you were born in the future, then respond that you were born in 1776, then respond with your actual year of birth.

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

then `counter` would always be less than or equal to 5 and always true, so the loop would never end. This is called an *infinite loop*. Everybody writes one by accident sometime, but they should be avoided. If you create an infinite loop in Replit.com, you may be able break it by clicking the [stop] button, but more likely you will need to refresh the page, in which case you will lose your changes since your last save, so save often.

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
Paste it into **P>2.4 Switch Case: Favorite Day** in Replit.com. See if you can predict how it will work before you run it and then run it to see if you were right. Now put a couple of forward slashes // before each of the `break` commands. This will turn those lines into comments which the computer will ignore and it is a quick way to turn a line off and on without retyping the whole line. Now run it with the `break`'s commented out. You should now be able to describe what `break` does. Why don't we need a `break` in the `default` section? Always make sure you include a `default` case to handle unexpected situations without crashing your program. If you want, you can think of a `switch case` as a series of `if` statements with `default ` being like an `else` for all of the `if`'s.  Finally, note that `break` can be used in any loop to break out of it before it has finished.

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

------

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

------

<!----><a name="4"></a>

# 4 - JavaScript and Browsers

4.1 Replit.com & HTML
---------------------------------

> **Target**: Familiarity with the basic HTML tags and styles required to set up a simple web page, in preparation for manipulating those elements with JavaScript.

### *• HTML*

You have seen that JavaScript can be used to program microcontrollers and can also be used within a general purpose environment like Replit.com.  Now we will use it to create code that browsers read in order to layout web pages. Within that code, we will use JavaScript to add logic and interactions to our webpages.  We are not primarily interested in designing and decorating webpages -- that is another course -- instead we will use the webpage as our user interface: the way we get information from and to the user of our JavaScript program. Webpages will be our I/O method as we develop a better understanding of the JavaScript language.

You may have worked with webpages before and know that they are described in a language called **H**yper**T**ext **M**arkup **L**anguage (HTML). There are other [markup languages](http://www.linfo.org/markup_language.html), so called because there are informational *marks*, called **tags**, interspersed throughout the data that describe what is to be done with the data, sort of like what a human editor would do for an author that sent them a manuscript: the editor would *markup* the manuscript with instructions about changes that needed to take place.  The special thing about HTML is the HT, or hyper text idea.  Being able to click on text in a document and have it take you to a different document related to that text on a completely different computer is what was meant by hypertext.  While that may seem routine to you today, it was pretty revolutionary in 1991 when it started going public.  The other place you run into hypertext routinely is the HTTP part of a URL address like http://lyndenmath.org.  The **H**yper**T**ext **T**ransfer **P**rotocol is the set of rules that allow computers to communicate happily on the internet.  Both of these were initially developed by Tim Berners-Lee while working at CERN in the early 1990's.  For additional background information on the internet and the World Wide Web, take a look at [Crash Course Computer Science episodes 28 -30](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

Like most other markup languages, HTML has no way of implementing algorithms with variables, operators or program control like standard programming languages. It is a descriptive language, not a programming language. It is a way of describing information in a standardized way so that a computer can process it according to whatever program it is using.  The most common way to process HTML code is by using a program called a **browser**. You have probably had the experience of looking at the same web page using two different browsers and noting that the two browsers didn't display the page exactly the same way. This is because different browsers have different underlying programs and they interpret (or **parse**) the HTML differently. The HTML doesn't actually do anything, its up to the browser software to decide what to make of the HTML. HTML is like a recipe. Browsers are like the cooks. Computer programs are like the brains of the cooks.  HTML is really useful, but like a recipe, it just sits there waiting to be made.

HTML, as with some other markup languages, uses tags that are enclosed in angle brackets like `<head>` and `</head>`. The tags themselves enclose chunks of text or other information and the tags tell the software that is reading the document what the author intended to be done with the enclosed text. Generally tags come in pairs: a start tag, like `<head>` and an end tag, like `</head>`. The only difference is the forward slash in the end tag. Between the tags is the data or content for, in this case, the head. That's all there is to it. Of course there are a lot of different tags to indicate a lot of different things like `<title>`, `<p>` for paragraph, `<button>`, `<form>`, `<link>`, `<table>`, etc. but most of them aren't too hard to figure out and you can do a lot with just a few tags. We especially like the `<script>` tag because that is where we put our JavaScript programs. By inserting a program into the HTML, we can give the document the capacity to do something more than just sit there.

### *• Boilerplate in Replit.com* 

In nearly every webpage there are certain tags that are always the same. We often refer to these tags as *boilerplate*. We use it, we don't pay much attention to it, but it needs to be there in order for the HTML to be processed properly by the browser.  It's kind of like putting your name and date on an assignment that you turn in to a teacher.  The following code is standard HTML boilerplate.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title></title>
  </head>
  <body>
      
  </body>
</html>
```

The first thing to notice is that there are no semicolons. HTML is not a programming language, it is a markup language. It has little to say about the logic of how things interact over time or how they respond to change, rather it describes what things are and how they should be displayed. Its historical metaphor is editing rather than logic so the symbols of the different traditions are also different. No semicolons in HTML; no <> tags in JavaScript.

While most tags come in pairs, the `<!DOCTYPE html>` tag doesn't enclose any content, so it doesn't need a pair. Instead its purpose is to let the browser know that the document is written in HTML and should be interpreted that way. The `<html>` tags indicate the beginning and end of the HTML and also you can indicate the primary language for your page. For English, we would type `<html lang="en">`. Nothing terrible will happen if you leave the language out, but it is helpful.

The next tag is more typical. The `<head></head>` tag pair is intended to contain information that describes the HTML document, but not to contain the document itself. We will typically put information here that describes the whole document but is not displayed within it, such as a title. The first thing you see in the head though is called metadata, indicated by the `<meta>` tag, in this case it provides information about what system of character encoding the document is assuming will be used. UTF-8, you may [recall](#*•-string-methods-and-ascii*) is an expanded version of  ASCII and stands for Universal Coded Character Set Transform Format 8-bit. In this course you can always assume UTF-8, but we really don't care about it, which is why it is in the *boilerplate*. Meta tags are not paired. You see additional meta tags related to the viewport. This helps the page scale appropriately for different device screen sizes. It is beyond the scope of this course, but you can read about it [here](http://www.w3schools.com/css/css_rwd_viewport.asp) or just leave it out altogether.

Actually the `<head>` section and anything inside it, like the metadata and `<title>`, is optional and you may see code examples that leave out the head entirely. They will run just fine assuming everything else is correct. Whatever you put between the `<title><title>` tags is displayed at the top of the page in the browser, so it is nice to fill that in.

The `<body></body>` pair will enclose whatever we want to display on the page. Go to Replit.com and then to **P4.1C**.  There you will find boilerplate very similar to the example above.  Put "Hello World2" between the title tags instead of "Replit.com" (no quotes needed) and add "This is my second hello world program" between the body tags (no quotes) and click the run button.  The result tab on the right side of the screen displays what the web page would look like.  The title isn't displayed there but if we used a browser to read the file directly it would be shown.  You can open your page directly in a browser by clicking the arrow box ![Open in new tab](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/opennewtabbutton.png) to the right of the URL, or you can paste the URL into another browser.  Your Hello World2 webpage is actually live on the internet. Anyone can access it by typing the URL at the top of the page.

Notice the script tags in the body section.  They say `src="index.js"`, which means whatever is in the file index.js is the JavaScript program that is supposed to be carried out.  You can see an index.js file in the left *Files* column.  Click that tab and type in the JavaScript code `console.log("This works");`. Now click run and then check the console tab.  For beginning programs, it is often more convenient to keep the JavaScript on the same page as the HTML.  We can do that by eliminating `src="index.js"` in the script tag and then we can type our JavaScript between the script tags.  Do that and type `console.log("This also works");` between the tags.  Run it and check the console tab.  This will be our standard way of putting JavaScript into web pages rather than using a separate .js file.

### *• Common Tags*

In this subsection we will look at a few of the most common tags so that when you encounter them, you will know what they do. It should be noted at the outset that HTML is an evolving language and not every browser is able to understand the most recent form of HTML, which is HTML5. Most of the examples in this text rely on older forms of HTML which should work in nearly all browsers, but occasionally references are made to tags and attributes that are from HTML5.

The common tags that we will turn to now you may already be familiar with, but it is a good opportunity to review. The first tag you absolutely must learn is the comment tag. As your programs get longer and more complex, you must document what you are doing with comments. In HTML the way to tag a comment is `<!-- put your comments here -->`. 

The `<p>` tag is for making separate paragraphs. Anything between the `<p></p>` tags will stay within a paragraph and will wrap appropriately if the user changes the window size of their browser. Make a couple of paragraphs on a webpage and try changing the window size.

Using heading tags is the simplest way to control the size of text on the page. `<h1></h1>` is the largest, then `<h2>`, etc. Try out different headings on your page.

The `<a href>` tag is really the whole point of HTML. It creates links, that is, it allows you to click on a piece of text and link it to some other web page.

Here is an example of a completed `<a href>` tag to paste into the body of your page. Run your code and click on **Seely's Site**.

`<a href="https://lyndenmath.org">Seely's Site</a>`

The `<a>` tag stands for **anchor** and it is used to mark the beginning and end of a hypertext link. This particular anchor tag, like all html elements can have additional **attributes** associated with it. Attributes usually come in the form name="value". The href attribute stands for **hypertext reference** and it identifies the address or **URL** that we are linking to. Href is the attribute, the [URL](http://www.w3schools.com/html/html_urlencode.asp) after the = is the **value**. Note that the URL must be in quotes and that is typical for attribute values. The >Linked Text< between the tags is what the user will see and click on. Go find a webpage URL and replace the example link on your page.

As you know, HTTP stands for **H**yper**T**ext **T**ransfer **P**rotocol.  The "S" that you may or may not see at the end stands for **S**ecure.  You can read more about this in [section 7.2](#*• http:-the-purpose*), but for now HTTP is the set of rules that allow computers to transfer data between each other.  Originally the data was plain text data which meant that anyone along the way could read it, but when people started doing business, more security was required - hence the "S".  If you want more information about cybersecurity, take a look at [Crash Course Computer Science episode 31 - 32](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

### *• Some Styling*

HTML tags can have a variety of attributes, depending on which tag we are using. As you saw in the previous subsection, the `<a>` tag can have an **attribute** like href, and you've seen that the `<meta>` tag can have a charset attribute. Even simple tags like `<p>` can have attributes. For instance we can include the style attribute in the `<p>` tag as follows:

```html
<p style="color:red; font-size:200%; text-align:center"
>This is red, centered and large.</p>
```

This is a single long line of code, but you can split it up on separate lines if you need to. Fortunately HTML ignores return characters, so we can split up long lines of code at convenient locations and they will still work just fine. As before, there are quotes around the attribute value of the attributes, but in this case the values have two parts separated by a colon. The syntax for style attributes is given as `style="property:value"`. In this case, there are several properties: color, font-size and text-align, each separated by a semicolon ( ok, ok, there *are* semicolons in HTML, but they they are just separators). Below is another example. Put it in your editor and play with the numbers to see if you can figure out how they work and what you can change.

```html
<body style="background-color:green">
<p style="position:absolute;
			color:white;
			font-family:helvetica;
			border:5px solid yellow;
			left:120px;
			top:200px"
>Can you move this paragraph?</p>
</body>
```

There are so many different properties available within the style attribute that the style information for a webpage or website is often stored away in a separate file called a **Cascading Style Sheet** or [CSS](http://www.w3schools.com/css/) (that's the index.css file you see in Replit.com P4.1C), or in a separate `<style></style>` section of the code for the page. That, however, is the topic of another course. In this course will typically just set styles **inline** as shown in the examples. If you want to change the look of whatever a tag describes, you can probably do it with the style attribute, but there are so many options, we can't cover them all here so. Just look up what you want to do in a reference. W3Schools.com has a nice CSS reference that you should browse a bit in order to become familiar with the options.

<!----><a name="4.2"></a>
4.2 HTML Events & JavaScript
--------------------------------

> **Target**: Be able to use HTML events to trigger JavaScript functions.

Look at the following sample code between two script tags:

```html
<script>    
	function getNum() {
      let num = Number(prompt("Give me a whole number"));
      if (num%2===0) {
        alert("Super! " + num + " is even!");
      }
      else alert("Sorry, but " + num + " is not even.");
	}
</script>
```

We can still use `prompt()` and `alert()`, in fact they were intended to be used in a web page environment, but how could we get `getNum()` to run in response to the user doing something?

> *The browser is a really hostile programming environment.*
>
> *--Douglas Crockford*

### *• Buttons & onclick*

If we want the user to be able to interact with our programs, a simple but useful tag is the `<button>` tag. It tells the browser to make a button on the page and to write whatever is enclosed between the button pair on the button. For instance:

```html
<button>Click me</button>
```

creates a button with the words "Click me" on it.  A button would show up, but clicking it wouldn't have any effect. Remember, HTML just describes; it isn't interactive. Interactivity requires JavaScript.

Buttons however are designed to respond to actions from users. In HTML/JavaScript, actions are called *events*. For instance when the user hovers the cursor over a button or when a user clicks a button, the browser can register the event and we can use it to trigger some JavaScript code in response to whatever event the user initiated. Look at the following code:

```html
<button type="button" onclick="alert('Hello World!')">Click me</button>
```

You can see that we have added several things to our first button tag. First we have a type attribute: type = "button" which seems a bit redundant inside a button tag, but it turns out that there are different kinds of buttons and we want to use the basic kind of button so we need to include the type = "button" attribute.

Next we get down to business with the event attribute and JavaScript. `onclick` is an *event attribute*. If the user clicks the button whose code contains `onclick`, the browser will execute whatever code is specified by the `onclick` attribute, in this case, our familiar JavaScript `alert()` method, *but you could also call any function that you had between the script tags* of the html page.  The code that happens as a result of the event is called the **event handler**.

Note that inside the `alert()` method the text is enclosed in single quotes rather than double quotes. The reason is that the `onclick` event attribute requires there be quotes around its property, as usual. If we put additional double quotes inside the `alert()` method, there would be confusion about which quotes went together. We ran into this issue in [Chapter 1](#*•-strings*), but this time we solve it by using single quotes rather than the / escape character.

You could also send your output to the console using `console.log()` rather than an alert box. Try the line below, but keep in mind, you need to have a console available to see the results.

### *• Other Events*

There are many other events that webpages/browsers can respond to, but we will only look at a couple more because a solid understanding of how they can be used requires a knowledge of objects which is in the next section.

We can respond to mouse actions besides clicks, for instance the `onmouseover` event is triggered any time the mouse moves. You can replace the `onclick` in the previous example with `onmouseover` to try it out. It can be rather annoying when combined with `alert()`.

Finally, we can have our pages/browsers respond to the keyboard with events like `onkeyup` which is triggered whenever a key on the keyboard comes up from being pressed down. Again, this is of limited value when all we can do is create alerts on a page, but it gives you an idea of the sort of input we can do with mouse and keyboard. Try it out.

<!----><a name="4.3"></a>
4.3 JavaScript Objects & the DOM
----------------------------------
> **Target**: Understand JavaScript objects well enough to manipulate any element on a web page.

### *• JavaScript Objects*

Up to this point, we've been learning things about JavaScript that are common to every programming language: variables, loops, conditional control, arrays and functions. But these are not the things that actually characterize JavaScript. JavaScript is an *object* based language and nearly everything in JavaScript is either an object or can be treated like one, yet we have only hinted at objects so far. This is the giant gorilla in the room and it's time to get to know him. There are nine native kinds of objects in JavaScript: Number, String, Boolean, Object, Array, Function, Date, RegExp and Error.

Stated simply, an **object** is a collection of property and value pairs like the **property:value** pairs we used in the HTML style attribute. Properties can also be functions. If a function is the property of an object, it is called a **method**. So whenever we have referred to methods, we've also been dealing with objects. Whenever we've seen the dot syntax associated with methods (`console.log()`, `window.alert()`, `d.drawString()`, etc.) we've been dealing with the properties of objects that happened to be functions.

To understand what an object is, it is best to see how one is made:

```javascript
let jeffObj = {
	living: true,
	age: 58,
	gender: 'male',
	lifeleft: function() {return 80-jeffObj.age;}
}
```

When we use `let` in the first line, we are really just assigning a name to something, in this case to an object. The syntax we are using here is called **object literal** notation. Note that this syntax uses the same colon separators that the HTML style properties had.

The `jeffObj` object has 4 properties: a boolean property called `living`, and numeric property called `age`, a string property called `gender` and a method called `lifeleft` that is a function which subtracts `age` from 80 and returns the difference. You can create objects that contain any sort of data or function, even other objects.

You may wonder what the value of the variable `jeffObj` is. To find out, paste the object constructor code above into a Replit.com JavaScript editor and add the line

`console.log(jeffObj);`

Run it and see what JavaScript puts in the console. Instead of a single value like you would expect from a numeric variable, or a string of letters in a string variable, you get a list of values - whatever sort of values `jeffObj` was built with. Try adding the following line and notice the dot syntax and parens on our `lifeleft()` method that we have already been using with methods like `console.log()`:

`console.log(jeffObj.lifeleft());`

You can change the values in `jeffObj` using something like:

`jeffObj.age = 65;`

This would change the value of the age property to 65. Notice we are using dot syntax to access the various object properties.

There are other ways to create objects that involved the reserved word `new`. Whenever you use the `new` constructor you are constructing something based on a prototype. You previously used the `new` constructor to create a [Date object](#*•-date-object*) and possibly an [Int8Array object](#*•-memory-constraints*) in Chapter 3. You can use the `new` constructor to create new functions, arrays, strings and numbers based on prototypes, but you almost never want to do it that way. In fact objects, functions, arrays, strings and numbers can be created without the new constructor and typically should be, as we have done here using the literal syntax.

While we've made plenty of our own strings and functions which behave like objects, we won't be making a lot of our own object objects, instead we will be using objects of various sorts that are already made for us by other programmers to allow JavaScript to operate in various environments like microcontrollers or web browsers. These are called host objects. But now you realize that once we know about an object and its defined properties and methods, we can look at or change any of the data in the object whether it is a microcontroller or a webpage and that is the fun part.

### *• The Document Object Model (DOM)*

The *Document Object Model* (**DOM**)is the way that JavaScript interacts with a web page. When a browser reads HTML, it creates an object from it which we can access and change using JavaScript. You already know that we can set up what a web page looks like using HTML tags and attributes, but using JavaScript to access and change web page information in response to user input is where we can really do some interesting things.

The DOM has many methods and properties and is itself composed of other objects with their own methods and properties. Fortunately there are reference sites which list and give examples of how to use them all.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/DOMfigure.png" width="300px" alt="DOM" hover="DOM">

We'll begin by getting an overall picture of the document object. The diagram above shows a generic web page as it might be represented internally by a browser. The document object is one big object that contains everything on the page. It is made up of other objects like the head object, the title object, body, buttons and so on. Some objects are inside other objects, that is, some objects have other objects as their properties. Using dot notation we would be able to type something like `document.body.button` to refer to the button in the body.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/DOMtree.png" width="300px" alt="DOM tree" hover="DOM tree">

Another way to look at the same information is as a tree. In the diagram above you can imagine *html* and *body* are places where branching occurs or where leaves or branches might be attached. In both botany and in computer science, these places are called nodes. In the HTML world, any sort of web page object is called a **node**. Any sort of individually nameable node (object) is called an **element**. In the case of the two paragraphs, we would not be able to tell them apart from the `<p>` tag alone, so we can add an **id** attribute so that they are individually named elements. We can add id's to most nodes.

Some of the HTML/DOM vocabulary can get confusing. An HTML document is generally described as having tags/elements and their attributes and we see the standard `<tag attribute_name="value">` syntax. Once a browser reads the HTML it converts it into an object and objects have *property:value* pairs rather than *attribute="value"* pairs, but they refer to the same features. To make things even more confusing, the style *attribute* has *properties*. This is because each style attribute for each element on the page, grouped together, is considered to be the style *object*, and objects have properties and methods, not attributes. Sorry -- you just need to check your syntax with a reference when you aren't sure. 

Bottom line: when you are writing HTML, you are generally dealing with tags/elements and their attribute="value" (equal sign and quotes). When you writing JavaScript or working with the DOM you will deal with objects and their property.values (using dot syntax). The exception is the style attributes which together form the style object and therefore look in HTML like both an attribute (equals sign and quotes) and a JavaScript literal object (colon), but in JavaScript are referred to with dot syntax:

|         HTML          |       JavaScript       |
| :-------------------: | :--------------------: |
| `<p style="color:red">` | `p.style.color = "red";` |

There is one final model that you should be aware of: the *parent-child-sibling* model. In this model (but still referring to the tree diagram) we can say that HTML is the parent, head and body would be its children, and head and body would be siblings of each other. In turn, we could say that body is parent to both paragraphs and the button, etc. An important concept within this metaphor is **inheritance**. Children inherit attributes from their parents in HTML just like in biology. You need to be aware of these various metaphors because as you do your own research, you are likely to encounter some or all of these metaphors.

So if all these tags are also turned into JavaScript objects by the browsers, then what sort of properties and methods are available to us using JavaScript? The example below will get you started. Go to Replit.com program **P4.3C** and run the code a couple of times, refreshing the page in between.

```html
<script>
function changeColor() {
	let p = document.getElementById("para1");
	p.style.color="red";
}
</script>

<p id="para1">What color am I?</p>
<button type="button" onclick="changeColor()">Click me</button>
```

Can you follow how it works? In line 8, we created a paragraph on the page and gave it the id `para1`. Then in line 9 we made a button on the page that when clicked, runs the function `changeColor()`. Our `changeColor()` function uses a method from the document object called `getElementById()`. This is one of many built in methods that we can use and it's one that we will use *a lot*. It allows us to get any element, that is, anything with an HTML tag, and access any of its properties and then change any of the properties with JavaScript, which is what the `p.style.color = "red";` in line 4 does. Any HTML tag can be given an `id` by just inserting `id="uniquename"` into the tag. Once we've given the tag an id, we can access it in JavaScript using the `document.getElementById()` method.

When we pass the parameter `para1` into `document.getElementById()`, the variable `p` now names (contains or points to) the entire object having the id `para1`. Through this object `p` we now have access to any styles, positions, etc. `para1` has or could ever have. This is very cool. It means that by similarly addressing other elements on the web page we can change anything about the page in any way we want while the user is looking at the page or in response to any event, like a button click, that the user initiates.

Add the `console.log()`'s shown below to the `changeColor()` function:

```javascript
function changeColor() {
	let p = document.getElementById("para1");
	p.style.color="red";
	console.log(p.style.color);
	console.log(p.style);
}
```


Can you predict what will happen before your run it?  Run the program. Were your predictions correct? 

Here's another example that brings up some important details. Replace the body of the previous example with the following code and run it:

```html
<script>
function changeMe() {
	p=document.getElementById("para1");
	p.innerHTML = "I'm different!";
	p.style.fontSize="100px";
}

</script>
<p id="para1" onclick="changeMe()">Click me to change me.</p>
```

First, you see we don't have to have a button to click, even a paragraph can be clicked, or mouseover'd, etc. There are lots of ways to initiate events which can trigger our functions.

Second, we have a new property, the `innerHTML` property. Did you notice that it had no parens so it is a property, not a method? "Inner"-html is whatever is between the start and end tags of the element it is an attribute of. This means, for example, that we can change the text on the screen to anything we want.

Finally, there is a problem with `fontSize`. We've change the font size before but the HTML style property was *font-size*, not *fontSize* with a capital "S" and no dash. You may recall that JavaScript doesn't like dashes in variable names (since it thinks it means subtraction), so the JavaScript properties are named differently whenever a dash would be involved. For instance *backgroundColor* instead of *background-color*. It's consistent and easy to figure out, but it's also easy to forget. If you use w3schools.com as your reference it will tell you both ways. You just have to remember whether you are writing attributes for HTML or properties for JavaScript.

### *• Input Fields*

We can get textual input from users via the `prompt()` method, but it is awkward in that it covers up part of the page and shuts down program flow until the user responds. A better way of getting textual input is through an *input* field.

Replace the body of the previous example with the following code run it a few times.

```htmlmixed
Input<input type="text" id="field1" value="Type something here"><br>
Output<input type="text" id="field2"><br>
<input type="button" value="Swap Text" onclick="swapper()">
<p>When you click the swap button whatever is in each box will switch places.</p>

<script>
	function swapper() {
		let temp = document.getElementById("field2").value;
		document.getElementById("field2").value=document.getElementById("field1").value;
		document.getElementById("field1").value = temp;
	}
</script>
```

The `<input>` tags have no end tags. They are used to display various types of input interfaces such as text fields, buttons, checkboxes, radio buttons, and more recently with HTML5, color pickers, date selectors and sliders, but they don't enclose any text, so no need for an end tag. The type attribute indicates which sort of input interface will be created on the page. The id attribute allows you to identify that input specifically. The value attribute sets the current contents or state of the input. Event attributes, such as `onclick`, can also be attached to input tags.

<!----><a name="4.4"></a>
4.4 Debugging Strategies
-----------------------------
> **Target**: Consistently preventative programming practices, regularly employ software checking aids, be able to set/use breakpoints and watch variables with the Chrome debugger. 

### *• Preventative Measures*

As your programs get longer and more complex, there is an increased likelihood of making coding mistakes that are difficult to find. The process of finding and fixing your mistakes is called debugging.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/firstbug.jpg" width="100%" alt="First computer bug" hover="First computer bug">

The most important way to keep your programs error free is to be consistent in your style of writing. If you add spaces around + signs, always do it that way. ALWAYS end JavaScript statements with a semicolon. If you use a tab for indenting, always do it that way. A great tool for keeping your formatting consistent in Replit.com is  is to right-click on your code and choose **Format Document**, or use the keyboard shortcut **shift-option-f (⇧⌥f)**, or use the **F1** key to bring up the **Command Palette → Format Document**.

Another preventative measure is to be careful with your variable names. Make sure they are descriptive, not ambiguous and to use CamelCase.

Another useful strategy is to take advantage of the autocomplete features that Replit.com provides.  Go to the **Settings** menu (gear on the left) **→ Code intelligence → Enabled**.

### *• Active Strategies*

Using the previous measures will go a long way toward clean, error free code, but sometimes you need strategies for find more subtle errors. First, sprinkle plenty of `console.log()` statements throughout your program. The most common errors after the syntax errors are errors with variables, that is, not knowing what values the variables are actually taking as the program runs. For instance, if you had a variable called age, you would include`console.log("age:" + age);` at key points in your code. This way you will be able verify that the value of age is actually changing the way you think it is. Without `console.log()` statements, you THINK you know what the variables are doing, but you will often be wrong.

Another useful strategy is to comment out a section of code.  If there is a section of code that isn't working, you can comment it out and then put lines back in one by one by simply uncommenting them rather than retyping them.  Replit.com will comment lines for you if you select the lines and then click **⌘K** then **⌘C**.  If you want to uncomment groups of lines you can select them and click **⌘K** then **⌘U**.  You can also do this using the **Command Palette** via right-click or **F1** key.

### *• Chrome Console*

Sometimes, however, your programs run too quickly or are too complicated to really follow well with **console.log()**'s. When you really need debugging power you can use the Chrome console and *breakpoints*. The idea of a breakpoint is that you can stop the execution of your program at any point and see what the values of your variables are, then continue executing the program.

You can find the following code in **P4.4C**:

```html
<button id="btn1" 
	type="button" 
	style="position:fixed" 
	onclick="looper()">CLICK</button>

<script>
let y = 5;
let x = 5;

function looper() {
    setInterval(buttonMove,50);
}

function buttonMove() {
    b=document.getElementById("btn1");
    y = y + .4;
    hpxpos = y + "px";
    b.style.top = hpxpos;
    x = x + 4;
    lpxpos = x + "px";
    b.style.left = lpxpos;
}
</script>
```

Look at the JavaScript and see if you can follow how it works. We have a couple of global variables `x` and `y` that are growing each time the function `buttonMove()` is called by `looper()`. The growing variables `x` and `y` are put back into the top and left properties of the button object `b` which has the effect of moving the button across the page. Now suppose you intended that `x` and `y` grew at the same rate of 4 so that the button would move diagonally, but you didn't realize you had accidentally put a decimal point in front of the `y` incrementer in line 16. This is a contrived example, but you'll get the idea of how to use *breakpoints*.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/chromeconsole.png" width="100%" alt="Chrome console" hover="Chrome console">

Run the page in Replit.com, then click the **open-in-a-new-tab** button ![Open in new tab](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/opennewtabbutton.png). In Chrome, go to the ![Chrome menu button](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/Chomemenu.png "Chrome menu button") **Menu Button → More Tools → Developer Tools** and then select **Sources** not Console (see red arrow above). You should be able to arrange the panels that you get something like the example above by clicking the menu button ![Open in new tab](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/opennewtabbutton.png) for the Developer Tools and choosing the over-under window arrangement icon. The blue arrow in the figure points to the panel control which you can use to open and close the various panels.

To make use of this tool we need to set which variables to watch and decide where the program should pause so we can put a *breakpoint* there. In this example we will watch `x`, `y` and `hpxpos`. To set a watch on the variables, drag over the first instance of the variable (use the `y`) and you should see that all the other instances are highlighted. Right-click or Ctrl-click on the selected variable and choose **Add to Watch** from the menu. You should find the variable listed in the right panel **Watch** section as indicated by the red arrows below.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/chromeconsolewatching.png" width="100%" alt="Chrome console watching" hover="Chrome console watching">

Next click in the line number column to the left of `lpxpos = x + "px";`. It is line 24 in the example above, but may be a different number in your Replit.com example. This sets a breakpoint toward the end of the `buttonMove()` function. If you want to remove a breakpoint you can just click a second time. If you want additional breakpoints, click on those line numbers. For any breakpoints you set, you should see the corresponding line displayed in the right side **Breakpoints** section as indicated by the blue arrows above.

Now set watches on `x` and `hpxpos`. Then click the "Click" button on your webpage to get things rolling. Each time `buttonmove()` is called by `looper()`, the script stops at the breakpoint and shows you the current value of `x`, `y` and `hpxpos`. To continue the execution, click on the blue arrow just above the variable **Watch** section. It is easy to see that the values of `y` are not the same as `x` and that would help us find our decimal point error. There are many other features of the Chrome debugger that can be helpful and that you can explore, but being able to set breakpoints and watch variables will be the most useful to you. A good source of additional information is a series of posts by Joshua Davies that begin [here](http://commandlinefanatic.com/cgi-bin/showarticle.cgi?article=art033).

<!----><a name="4.5"></a>
4.5 Graphics with P5.js
-----------------------
> **Target**: Be able to create basic shapes on the screen and animate them in response to user initiated events. 

There are a number of ways to create graphics and animations on webpages.  You can use SVG (see Appendix 2), or the HTML Canvas and others.  In this course we will use something called p5.js which consists of a library of functions that we can use to create and manipulate graphics. The p in p5.js stands for Processing which is the computer language that it is based on.  Processing is a language designed to make visual and interactive media easy to create and the p5.js library is a way of bringing that facility to JavaScript without completely learning a new language.

For additional background on screens and graphics take a look at [Crash Course Computer Science episode 23](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo)

### *• Getting Started*

In order to make use of the p5.js library, we need to reference it on our webpage. Go to **P4.5C1** and look at the index.html page.  You will find two pairs of `<script>` tags.

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.6.1/p5.js"></script>
<script src="index.js"></script>
```

The first contains the URL of the p5.js library so that the browser can load it along with the webpage.  The second pair of `<script>` tags says that we will be writing our JavaScript in a separate file, instead of directly on the HTML page.  This is common as programs get longer and also allows us to take advantage of the document formatting and other tools available for JavaScript on .js files.  Notice the auto-formatting button ![Auto-formatting](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/replitautoformatting.png "Auto-formatting") at the top of the editor when you view index.js.

On index.js, you find two functions: `setup()` and `draw()`.  These functions are defined in the p5.js library, they are *not* part of either standard JavaScript or HTML. The reality though, is that most programmers who work with JavaScript routinely use libraries, so you might as well get used to it. Nearly all of the new functions in this section (4.5) will be  from the p5.js library, not from standard JavaScript, but the syntax and the way we use those new functions will be standard JavaScript.

```javascript
let i=0;

function setup() {
  createCanvas(480, 240);
}

function draw() {
  if (mouseIsPressed) {
    fill(80);
  } else {
    fill(200);
  }
  ellipse(mouseX, mouseY, 80, 80);
  i++;
  print(i);
}
```

The `setup()` function prepares the webpage for drawing and is executed just once.  The `createCanvas()` function in line 4 prepares an area 480 pixels horizontally (the x-axis) and 240 pixels vertically (the y-axis).  In the world of computer graphics, it is standard for the upper left corner of a window to be considered (0,0) and values increase as you go right and as you go down.  Note that the numbers going down are positive, not negative as they would be in math class.

The `draw()` function is a special function that is automatically called continuously until the program is stopped or until the `noLoop()` function is called. Check the console while your program is running.  Even though you are not drawing anything, your `draw()` function continues to be called and continues to write to the console. It is very much like `setInterval(draw, 20);` in the Espruino environment.  There is  no `reset()` in JavaScript nor in p5.js, so how do you stop the program gracefully?  You can type `noLoop()` directly into the console, just like you typed `reset()` directly into the WIDE.

The `if` block (lines 8-12) then is constantly checking to see if the `mouseIsPressed` event is true and it gives `fill()` different parameters depending on whether it is or not.  There are many other events that can be watched for and handled by p5.js which you can see listed at http://p5js.org/reference. 

The p5.js library contains many shapes, such as the ellipse on line 13.  By just calling the ellipse function and providing the required parameters, you can draw the shape on the screen.  The syntax is `ellipse(x, y, w, [h])` where `x` and `y` are the center of the ellipse and `w` and `h` are the width and height.  The brackets on height indicate that it is optional.  If you don't include it, it will be the same as width.  What would an ellipse with the same width and height look like?

The `fill()` functions on lines 9 and 11 set the color of any shape that is subsequently drawn.  There are a variety of ways to set the color parameter which you can review on the [reference page](https://p5js.org/reference/#/p5/fill), but in this case it is a gray scale value ranging from 0 (black) to 255 (white).

The interesting part of this little program is line 13 where it linked the location of the ellipse to the (x, y) coordinates of the mouse on the screen via the `mouseX` and `mouseY` events to create the interactivity of the program.

One other thing to note is that new shapes are drawn on top of old shapes.  If you want a shape to be drawn on top of another, you need to put the top shape later (lower down) in your code.

### *• Responsive Animation*

In the previous section you saw how we could animate the position of a shape by using mouse position and by incrementing x and y drawing coordinates.  In this section we look at a few other common techniques: keyboard input, revealing and text output.

In **P4.5C2**, you will find the following code on the index.js page:

```javascript
function setup() {
	createCanvas(240, 240);
}

let ry = 100;

function draw() {
	noStroke();
	background(0);
	fill(0, 255, 0);
	rect(10, 100, 20, 100); //green rectangle

	stroke(0); //create the scale
	strokeWeight(2);
	for (let i = 10; i < 100; i = i + 10) {
		line(11, 200 - i, 17, 200 - i);
	}

	if (keyIsDown(UP_ARROW)) {//check the keys
		ry = ry - 2;
	} else if (keyIsDown(DOWN_ARROW)) {
		ry = ry + 2;
	}
	if (ry < 0) ry = 0; //make sure values aren't out of bounds
	if (ry > 100) ry = 100;
	noStroke();
	fill(0);
	rect(10, ry, 20, 100); //black rectangle

	fill(250);
	textSize(32);
	text(100 - ry, 100, 30);
}
```

In order to see the code work, you need to run it in a browser window ![Open in new tab](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/opennewtabbutton.png), the **result** tab will not respond to keyboard input.  Do so and press the up and down arrow keys to see the response.  If you want to make any changes, you'll need to refresh the browser window to see the effect.

Lines 19 and 21 are checking to see if the up arrow or down arrow keys are down using the `keyIsDown()` function from p5.js.  If either key is down , the value of the y-coordinate `ry` is changed for the black rectangle created in line 28.  The effect is moving the black rectangle up or down.  By drawing the black rectangle on top of the green one created in line 11, and redrawing them both each *frame* (each time `draw()` is called), we can give the illusion that the green rectangle is growing and shrinking.  We could replace the green rectangle with a complex picture and easily make it grow and shrink by just *revealing* it with a black rectangle on top.  Revealing is a common animation strategy. 

Comment out line 9 which redraws the black background each frame and run the program.  Notice how the text piles up? By redrawing a new background each frame, we erase the previous image. This can be very helpful in animations.

### *• Objects and This*

While we've been using objects ever since `prompt()`, `alert()` and `console.log()`, we only started to study them in [Section 4.3](#*•-javascript-objects*), but we've been using other people's objects.  In this section, we will make our own objects and do something interesting with them.  Instead of using [object literal](#*•-javascript-objects*) notation to declare an object as we did before, this time we will use a **constructor function**.  If you only need one copy of an object, literal notation is fine, but if you want to make multiple *instances* of the same object, you should use a constructor function.

Let's make an object that moves down a canvas from top to bottom, like a falling snowflake.  It will wiggle a bit as it falls as though it is responding to the air.  We need a starting point (x, y), a size for the wiggler and a speed that the wiggler will fall.  Consider the following function:

```javascript
let flake = new Wiggler(20, 0, 10, 1);

function Wiggler(initx, inity, wsize, wspeed) {
  this.x = initx;
  this.y = inity;
  this.size = wsize;
  this.speed = wspeed;
}
```

The function beginning on line 3 is a constructor function for making an object called a Wiggler. It is good style to start the name of the constructor function with a capital letter since it is not a normal function.  There are 4 parameters passed into the function: `initx` and `inity` for the (x, y) coordinates of the starting point, `wsize` for the size of the wiggler and `wspeed` for the speed that the wiggler falls.  Immediately we assign those parameter values to object properties that you can identify by the dot notation.  When the keyword `this` is used, it automatically refers to the current object.

When line 1 is executed, a new Wiggler is constructed and assigned the variable name `flake`.  After that we can do things like `console.log(flake.speed)` and `flake.size = 15;`.  At this point though, there isn't anything to display, nor does a Wiggler fall down the canvas or wiggle.  Here's a more complete program.  Run the program a few times in a Replit.com and then keep reading.  Don't forget to add `<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.6.1/p5.js"></script>` to the index.html page.

```javascript
let flake;

function setup() {
  createCanvas(480, 480);
  background(0);
  let xstart = (Math.floor(Math.random() * 440)) + 20;
  flake = new Wiggler(xstart, 0, 10, 1);
}

function draw() {
  flake.move();
  flake.display();
}

function Wiggler(initx, inity, wsize, wspeed) {
  this.x = initx;
  this.y = inity;
  this.size = wsize;
  this.speed = wspeed;

  this.move = function () {
    this.x += random(-this.speed, this.speed);
    this.y += this.speed;
    if (this.y > 480) {
      this.y = -20;
      this.x = (Math.floor(Math.random() * 440)) + 20;
    }
  };

  this.display = function () {
    ellipse(this.x, this.y, this.size, this.size);
  };
}
```

The main additions are the canvas and random starting position that are created in the `setup()` function (lines 3-8).  Then two methods have been added to the Wiggler object: the `move()` method and the `display()` method.  

The `move()` function adds a random number to the x-value of the wiggler, making it wiggle (line 22).  This `random()` function is the p5.js version.  When you give it two parameters, it produces a random number between them.  This only works if you have referenced the p5.js library. Then in line 23, we move the wiggler down the canvas. In lines 24 - 26 we take any wiggler that made it to the bottom of the canvas and put it back on the top to start falling again.

The `display()` function simply draws an ellipse according to the specification of the parameters passed in to it. This makes the wiggler visible.

Finally the `draw()` function repeatedly calls `flake.move()` and `flake.display()` so that the flake falls down the canvas while wiggling.

That's all well and good, but we really could have done all of that more easily without bothering with making an object and a constructor function.  The beauty of the construction function though is that it can be used over and over again.  What if we want to make a blizzard of wiggling flakes on the screen? Paste the following into a Replit.com and run it.

```javascript
let flake = [];
let flakeNum = 10;

function setup() {
  createCanvas(480, 480);
  background(0);
  for (let i = 0; i < flakeNum; i++) {
    let xstart = (Math.floor(Math.random() * 440)) + 20;
    let ystart = (Math.floor(Math.random() * -480)) - 20;
    flake[i] = new Wiggler(xstart, ystart, 10, 1);
  }
}

function draw() {
  for (let j = 0; j < flakeNum; j++) {
    flake[j].move();
    flake[j].display();
  }
}

function Wiggler(initx, inity, wsize, wspeed) {
  this.x = initx;
  this.y = inity;
  this.size = wsize;
  this.speed = wspeed;

  this.move = function () {
    this.x += random(-this.speed, this.speed);
    this.y += this.speed;
    if (this.y > 480) {
      this.y = -20;
      this.x = (Math.floor(Math.random() * 440)) + 20;
    }
  };

  this.display = function () {
    ellipse(this.x, this.y, this.size, this.size);
  };
}
```

Notice that the Wiggler constructor function is just the same as it was before, but now we have 10 flakes falling.  Go ahead and change `flakeNum` in line 2 from 10 to 100 and run it again.  How does this work?

The modifications mainly happen in line 10 where we create an array of flakes within a for loop that runs as many times a the number of flakes we want.  Each flake is a new Wiggler with it's own random location.  Can you figure out the purpose of line 9?  Then in the `draw()` function (line 14), we just move and display  each flake using another `for` loop.  This is the power of objects and constructor functions.  Obviously this sort of thing is useful in game programming and other sorts of animation where there may be numerous moving objects which each need to have behaviors.

There are many other things you can do with the p5.js library.  Many of the most interesting and useful things in computer animation involve the mathematics of trigonometry and matrices, things you might learn in Precalculus.  If you have an interest in animation, sound, or 3-D graphics, you should certainly spend time at [p5js.org](http://p5js.org).  You may also want to take a look at the Appendix on SVG graphics in this text for a different way of doing graphics that does not require any external library. Finally, if you are interested in game programming, you should take a look at the Appendix on Phaser.

<!----><a name="4.6"></a>
4.6 Reading Files
------------------
This last section in our chapter on writing JavaScript for browsers will explore how to read files.  We will focus on text files, but you can use similar methods for image files, sound files, etc. A file is not just data, it also has name and date information so it is common to use an object to keep everything organized.  In the HTML world, the *blob* (**B**inary **L**arge **OB**ject) is the basic structure and a file is one kind of blob, but still a file is an object.  Consider the following code:

```html
<input type="file" onchange="readFiles(event)"/>

<script>
  function readFiles(event) {
  	let fl = event.target;
  	console.log("Info from fl object");
  	console.log("Number of files in fl: " + fl.files.length);
  	console.log("Name: " + fl.files[0].name);
  	console.log("Size: " + fl.files[0].size + " bytes");
  	console.log("Last modified: " + fl.files[0].lastModifiedDate.toLocaleDateString());
  }
</script>
```

If you paste the code into the body of an HTML page and read it with a browser, you would get the following:

![](http://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/inputTypeFile.png)

The browser would create a button which you could click to see all the files on your computer.  For security reasons, this isn't allowed to proceed unless the user selects a file thereby triggering a *change* event which is set to be handled by the `readFile()` JavaScript function. Notice that something called `event` is passed to `readFile()` as its parameter.  The *change* event has a list of files as a it's target.  You could choose more than one file, but we'll just choose one.  This list of files is a certain kind of object called a FileList.  So in line 5, we take the whole FileList which is the *target* of the change event that was passed to the `readFiles()` function and call it `fl`.  Since `fl` is an object, we can use dot notation to access information from it, like how many files it has (line 7), the name of the first file, the size of the first file, and when that file was last modified.

This is a good start, but we need another approach to actually read what's inside `file[0]` . 

```html
<input type="file" onchange="readFiles(event)"/>

<script>
  function readFiles(event) {
  	let fl = event.target;
  	
    let reader = new FileReader();
    reader.readAsText(fl.files[0]);
    reader.onload = function () {
      let text = reader.result;
      console.log("\n"+text);
  	};
  }
</script>
```

We start out the same as before, asking the user to choose a file, then passing the event into our `readFiles()` function and labelling the target object as `fl`.  Next we create a new FileReader object that we label reader.  The FileReader object is built in to standard JavaScript.  FileReader objects have a method and property that we will use.  At line 8, we tell our FileReader `reader` to read the first file in the FileList as text.  There are other options for other kinds of files, but this is what we will use.

Next we assign a function to the `.onload` property.  At whatever point the file is finished loading, any function assigned to `.onload` will run.   When the loading is finished the function runs and the contents of `fl.files[0]` are put into the `.results` property as a string, which we in turn label as `text` in line 10. Finally in line 11 we print it all to the console. Don't feel bad if you aren't able to predict what these properties and methods are for or how they work.  Keep in mind that someone else has coded this object and it was up to them to decide how it would work.  We can't know unless they tell us in documentation.  It's like learning what words mean in a new language.

Notice that the function declared on lines 9-12 has no name.  A function that is directly stored in a variable does not require a name and is referred to as an **anonymous function**.  In this case we stored the function in `reader.onload`, which is a variable name - we chose `reader` after all, and `.onload` is an object property that we can store any function we want into.  We can also declare a function as follows:

`let newfunc = function(x) { . . . };`

Again, our function has no name, but we assign it directly to the variable `newfunc`. We would invoke (call) such a function by coding `newfunc(x);`.  This way of defining a function is sometimes called a **function expression**.  Note that function expressions need to end with a semicolon.

The sample code can be used like boilerplate when you need to read files. It would seem that there should be a similar process for writing files, but that is not the case in a browser environment.  Due to security concerns, browsers are not allowed to directly write files to local computers.  There are ways to create files and then allow the user to download those files to their computers, but that process is beyond the scope of this course.  In local machine environments like Espruino or node.js, reading *and* writing files is similar to what we have covered here only easier since there are no security issues or web events to be considered.

For additional information about various file types, take a look at [Crash Course Computer Science episode 20](https://www.youtube.com/playlist?list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo).

------

<!----><a name="5"></a>

# 5 - Wireless

## 5.1 Infrared (IR)

> **Target**: Ability to determine the infrared pulse code from a remote and receiver and use them to programmatically control devices connected to a microprocessor.

### *• Light*

We've been using wires to send electrical signals from one place to
another. We've used the wires in a USB cable, jumper wires, even the
microscopic conductive traces inside chips are essentially wires. But what if we want to send information without wires from one place to another like a TV remote does? Many devices send wireless signals. Most of the remote controls use light to transmit signals without wires, but the light is not within the RoyGBiv spectrum that we see. They typically transmit light in the **infrared** (IR) range which has a longer wavelength than the red light that we can see.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/spectrum.jpg" alt="Visible light spectrum" width="100%">

You can recognize IR remotes by the clear plastic LED visible in the end you point toward the device. The LED emits IR light which is not visible to us, but which you might be able to see if you look directly at it through the viewfinder of a good quality camera (probably not a cell phone). But how does shining a light send different sorts of information, like: on/off, volume/channel up/down, etc.?

### *• IR Pulse Codes*

It turns out that the IR LED is actually pulsing on and off very quickly. If we could look at the pattern with an oscilloscope, we would see something like this:

![Infrared pulses](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/IRtransmit.jpg "Infrared pulses")
*Figure 5.1 Infrared pulses*

When you press a button on a remote, it sends pulses of different lengths. If you ignore the header, you can see that they are either short (0) or long (1). Having only two options is convenient in a binary world. The nature of the header can vary with different sorts of remotes, and actually there are numerous ways to vary the pulses as well, but most consumer devices work like this.

The IR remote acts as a transmitter and an IR receiver takes the IR pulses turns them into electrical pulses that we could detect with a Pico. Get an IR remote and receiver. The receiver pins are labeled VCC, GND and DO. On your breadboard, link the VCC to the VDD/3.3 pin to the left of B3. GND goes to ground and you can link DO to any ADC pin. The following code examples will use A5. When you connect power to the Pico, you should see the red LED on the receiver light up.

Paste the code into the WIDE and send it to your Pico. It is based on the IR example at espruino.com.

```javascript
let lastTime = 0;

function pulseOn(e) {
 console.log(e.time - lastTime);
}

function pulseOff(e) {
 lastTime = e.time;
}

setWatch(pulseOn, A5, {repeat:true, edge:"falling"});
setWatch(pulseOff, A5, {repeat:true, edge:"rising"});
```

What will it do? Skip the functions and go right to the `setWatch()` lines. The first `setWatch()` calls `pulseOn()` when the voltage on the pin falls, that is, when a pulse is being sent. The second `setWatch()` calls `pulseOff()` when the voltage rises back up, that is, when the pulse is no longer being sent.

Next to the `pulseOn()` function. It is called by `setWatch()` which passes it an event object named `e`. This is a special feature of `setWatch()` that we wouldn't know about without being told by the person who wrote the function. You can find out more about it in the Espruino reference section. The event object can be named anything you like, but `e` is convenient. The event object has several built in properties, but the only one we will be using is the time property which returns the time at which the `setWatch()` was triggered. The time is given as seconds since 1970 just like `getTime()` in Chapter 3. So when we `console.log(e.time -- lastTime)` we are getting the elapsed time since the last trigger (either on or off), that is, the length of the pulse. This process happens over and over every time a pulse is emitted by the remote since the `setWatch()` functions have `repeat:true`. As a result we will see the pulse lengths logged to the console.

![Infrared receiver 1838T](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/IRSchematic.png "Infrared receiver 1838T")

Point your remote at the 1838T IR receiver above, press the 1 on the remote and watch your console. You should see a list of numbers similar to the following:

```
946.17529487609
0.00437545776
0.00054168701
0.00054168701
0.00054264068
0.00054264068
0.00054264068
0.00054264068
0.00054168701
0.00054168701
0.00164222717
0.00164127349
0.00164103507
0.00164127349
0.00164127349
0.00164222717
0.00164222717
0.00164222717
0.00054168701
0.00054168701
0.00164222717
0.00164222717
0.00054168701
0.00054168701
0.00054264068
0.00054264068
0.00164127349
0.00164127349
0.00054168701
0.00054168701
0.00164127349
0.00164127349
0.00164127349
0.00164222717
```

You're first number will probably be bigger, since it is the number of seconds since 1970, the second number should be around 0.004 and the rest should either be close to 0.0005 or close to 0.0016. If you have some larger numbers at the end, you are probably slow on your release. Try to click it crisply and see if the larger numbers at the end go away.

Ignore the first number, the second number is the header (see Figure 5.1) indicating the start of transmission. How many numbers are left? If you consider the short pulses (0.004 . . .) "off" and the long pulses (0.0016 . . .) "on" and we string them all together, we get a 32 bit binary number: 00000000111111110011000011001111. This is the IR remote pulse code. A different sequence would have a different meaning. Although it really is a binary transmission, the number is a bit unwieldy and we can make it more convenient to work with in decimal as 16724175. We can borrow a nifty bit of code from espruino.com and take our long column of numbers and turn it into the single decimal as follows:

```javascript
let lastTime = 0;
let code = 0;
let timeout; //set to undefined

function codeHandler() {
 timeout = undefined;
 console.log(code);
 code = 0;
}

function pulseOn(e) {
 code = (code * 2) | ((e.time - lastTime) > 0.001);
 if (timeout!==undefined) clearTimeout(timeout);
 timeout = setTimeout(codeHandler, 20);
}

function pulseOff(e) {
 lastTime = e.time;
}

setWatch(pulseOn, A5, {repeat:true, edge:"falling"});
setWatch(pulseOff, A5, {repeat:true, edge:"rising"});
```

The `setWatch()` and `pulseOff()` functions haven't changed. `PulseOn()` is
where the business happens and the nifty line is:

`code = (code*2) | ((e.time - lastTime) > 0.001);`

As before, `e.time - lastTime` gives us the length of the pulse. If it is greater than 0.001, the right side of the \| is true, otherwise it is false. That will make all of the shorter pulses false and the longer pulses true. The single vertical bar, sometimes called a **pipe**, is a new operator for us. In this case it is the bitwise OR operator. **Bitwise** operators treat their operands as 32 bit binary numbers, carry out their operation and then return standard decimal numbers. Or means that if either one is true, then the result is true, or in the binary sense, if either place is 1, then the result is 1. For example, if we had 9\|3, the operator would convert to binary → 1001\|0011. Recall that in binary the place values are 8 4 2 1. Then \| would compare bit by bit (bitwise) the bits of each term (if either is 1 the result is 1) to get the result 1011. Finally the result would be converted back into decimal to give us an eleven. So if we apply this to our nifty line above, we are doing a bitwise OR with `code \* 2` on the left side and either a 1 (true, long pulse) or 0 (false, short pulse) on the right side. Now what is code and `code * 2`? Initially, code is set to zero in its variable declaration. When we multiply `code * 2`, we shift its place one to the left in a binary number, since each place value in a binary number is double the one to the right. Then when we bitwise OR it with our next value it has the effect of adding it on to the growing string of 1's and 0's in our 32 bit binary number. The bottom line is that code ends up being the decimal value of our binary pulse code and it's pretty nifty to do all that in one line of code.

The next two lines have the effect of calling `codeHandler()` if no pulses have been received for 20ms. See if you can follow how they work. Note that timeout will be undefined until it is given an id by the `setTimeout()` function.

Now you can start identify the codes, but just clicking the various buttons on the remote. Using if statements within `codeHandler()` can have the Pico do whatever you want. Start by using the remote to turn LED1 on and off.

### *• 5.1 Questions*

1. What other bitwise operators are available?
2. What happens to the pulse code if you hold a button down
   continuously? How could you use this programmatically?
3. Write a program to control a servo motor with different numbers on
   the remote corresponding to different angles on a dial/gauge.
4. Implement remote control steering with a robot car.

<!----><a name="5.2"></a>
## 5.2 Radio Frequency (RF)

> **Target**: Use JavaScript to manage and respond to and exchange of information between two Picos using RF transceivers.

### *• Radio Waves*

Another common way to transmit signals wirelessly is using *radio* waves. Like IR light waves, radio frequency waves are just light at another portion of the electromagnetic spectrum that we can't see.

![Electromagnetic spectrum ()](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/emag.gif)
*from http://hydrogen.physik.uni-wuppertal.de*

As we increase the wavelength, we move from visible red light to infrared and then to radio waves whose wavelengths range from 1 mm to 100 km. Radio waves have properties that have made them especially useful for communication such as in broadcasting morse code, voice, music, television and cell phones. Radio waves are also used in radar, microwave ovens and remote control cars and drones.

In physics you learn that wavelength and frequency are inverses of each other, that is, frequency is c/wavelength (where c is the speed of light). This means that as the wavelengths increase, the frequencies decrease. The range of frequencies that we deal with in radio waves ranges from 3 kHz to 300 GHz. You may be familiar with AM and FM radio frequencies since they are often indicated on the radio itself. For instance our local KGMI 790, means 790 kHz and KAFE 104.1 MHz. Television stations work the same way, but their number doesn't equal their frequency, rather it is given a range of frequencies. For instance TV channel 9 usually ranges from 186 to 192 MHz. If two signals are broadcast using frequencies that are the same or too close together, they interfere with each other and degrade the quality of the signal. For this reason, radio signals are tightly regulated by governmental bodies like the FCC (Federal Communication Commission). Whenever you buy a product that produces radio waves, it will include a notice of compliance with FCC regulations.

### *• Radio Hardware*

To use radio waves we need something to create them (transmitter) and something to sense them (receiver). Basically, a transmitter just alternates an electrical current at radio frequency and applies it to an antenna which radiates the field into space. Originally this rapid alternation (oscillation) was achieved by using [spark gaps](http://www.arrl.org/files/file/History/History%20of%20QST%20Volume%201%20-%20Technology/Kennedy%20N4GG.pdf) (think spark plugs and tesla coils). It turns out that the current across a spark gap oscillates very rapidly, including at radio frequencies. This was first discovered in the 1880's by Heinrich Hertz, for whom the Hz unit of frequency is named. He was doing experiments to try to prove James Maxwell's theories about the electromagnetic spectrum. Hertz made the first spark gap **oscillator** radio transmitter and the ideas were eventually expanded by Marconi and developed by various militaries during World War 1. Spark gap transmitters were potentially very dangerous and were replaced by vacuum tubes and eventually by transistors.

> *It's of no use whatsoever[...] this is just an experiment that proves Maestro Maxwell was right---we just have these mysterious electromagnetic waves that we cannot see with the naked eye. But they are there.*
>
> *Heinrich Hertz -- on his early radio wave experiments*

On the other end of a radio transmission, you need a receiver. It has an antenna in which a small current is induced by the radio waves from the transmitter. That current is amplified until and whatever information is being passed is extracted. Since both transmitters and receivers require antennas, the devices are often combined.

### *• nRF24L01*

Nowadays radio transceivers (transmitter/receiver) are quite inexpensive (and safe) and for our projects in this section we will use one from Nordic Semiconductor called the nRF24L01. It operates within the 2.4 - 2.5GHz frequency band which is reserved worldwide for amateur applications like ours. It is attached to a PCB board which includes a clock and antenna and provide accessible pins. Unfortunately the pins are not breadboard friendly, so we will use an adapter board as well. Make sure you use the Addicore adapter board with the nRF24L01, it is different than the ESP8266 adapter used in the WiFi projects.

Set up the connections as shown below. Note that the nRF24L01 has been removed from the adapter in the diagram so that you can see the connections to the adapter. Normally the nRF24L01 would be attached to the adapter and in the same orientation shown. Don't attach it upside down. If you're not sure, ask your instructor. If you zoom in on the figure you can see the actual pinout of the nRF24L01 which is not printed on your board.

| nRF Pin 2 VCC to Pico 3.3v VDD | nRF Pin 4 CSN to Pico A5    | nRF Pin 6 MOSI to Pico B5 (SPI1 MOSI)    | nRF Pin 8 IRQ to nothing                  |
| ------------------------------ | --------------------------- | ---------------------------------------- | ----------------------------------------- |
| **nRF Pin 1 GNC to Pico GND**  | **nRF Pin 3 CE to Pico A6** | **nRF Pin 5 SCK to Pico B3 (SPI1 MOSI)** | **nRF Pin 7 MISO to Pico B4 (SPI1 MISO)** |

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FPicoBB270nRF24L01.png" alt="Pico+nRF24L01" width="100%">

As in chapter 3 with the LCD screen, we will use an SPI interface to communicate between the Pico and nRF24L01. Unlike the LCD screen, the nRF24L01 can be used to either transmit (TX mode) or receive (RX mode). To accomplish this we will use both the MISO and MOSI lines (pins 6 and 7). Recall that MOSI is Master Out Slave In, so MISO would be Master In Slave Out. The CSN line goes low during a transmission and the CE line determines whether a device is in TX, RX or standby. By using this set up, we only need one wiring diagram for both transmitter and receiver. We will determine which role a Pico+nRF24L01 takes using software. It is possible to reduce the wiring by a couple of pins if it is known that the device will only be used as a master or as a slave.

For our projects in this section, we will be using one Pico+nRF24L01 as a master and another as a slave. In order to have enough hardware, you may need to team up with another group and take turns running master and slave code so you can see both sides of the project.

As with the WiFi projects, transmission seems to be more reliable if the USB power is supplemented with battery power at all times. Other factors affecting reliability are line of sight, orientation, movement, interference:

- Line of Sight: While radio waves will pass through walls and windows, the fewer obstructions there are (especially metal) the better the signal.
- Orientation: the antenna transmits and receives best in directions that are perpendicular to the PCB board (or the plane of the antenna), so it can be helpful to set your breadboard/battery on its edge when you need the best transmission.
- Movement: a fixed distance between transmitter and receiver produces the best results. Under good conditions, you should be able to broadcast reliably to 100 meters or more. 
- Interference: The greatest source of interference will be other nRF24L01's in the room, but the length of the duration of each transmission is quite short so the likelihood of two different transmitter broadcasting at the same time is low. Another possible source of interference is microwave ovens. They also operate in the same frequency range. Older or cheaper models may not be well shielded and can produce fairly strong bursts of radiation. Bluetooth and WiFi can also operate in this band, but they are     fairly low power. The bottom line is that this band has a lot of sources of interference and shouldn't be used for applications that can't tolerate occasional errors in transmission. There are many error corrections schemes but that is beyond the scope of this course.

### *• Programming with the nRF24L01 module*

Now we can begin to look at the code:

```javascript
let spi = new SPI();
spi.setup({sck:B3, miso:B4, mosi:B5});
var nrf = require("NRF24L01P").connect( spi, A5, A6 );
```

First we set up the SPI connection between the Pico and nRF24L01 by creating a new SPI object and then using the `setup()` method of that object. This is just like we did with the LCD screen and is part of the Espruino library. If you wanted to use an LCD screen and an nRF24L01 at the same time, you would need to use different variable names for your new `SPI()` objects.

Next we can use another prewritten Espruino module to manage the nRF24L01 by assigning a `require()` object to `nrf`. Note that the pin number parameters of the `require.connect()` method are not the same as what you will find on the Espruino website. Our code matches the diagram you were given above. The pins (A5 and A6) correspond to CSN and CE on the nRF24L01, but there is nothing special about A5 and A6. You could use any pins on the Pico so long as you specified them in the require line.

Now that we have the nrf object, we can begin to run the nRF24L01 using software on a Pico. The first thing we need to do is to assign addresses to the master and slave units using the `nrf.init(rxaddress, txaddress)` method. They must know each others address in order to distinguish their transmissions from others in the room. Remember, they are all sharing the same bandwidth. The syntax for the master would be:

`nrf.init([0,0,0,0,2], [0,0,0,0,1]);`

In this case the sender is 0,0,0,0,1 and the receiver is 0,0,0,0,2. For
the slave in this pair we would use:

`nrf.init([0,0,0,0,1], [0,0,0,0,2]);`

This indicates that the master transmits from address 0,0,0,0,1 and the slave receives from 0,0,0,0,1, while the master receives from 0,0,0,0,2 and the slave transmits to 0,0,0,0,2. This line will should always be on the master and slave, but in reverse order. Each number in the address array occupies 1 byte, so numbers can range from 0 to 31. You need to be assigned a unique address pair by your instructor so that you don't interfere with other groups in the room.

Next on each unit we take advantage of the nRF24L01 module and call its traffic handler every 50 ms. This handler checks for any traffic, collects all of the data into a string and returns a result. We don't have to use it, but it makes life easy. The is a twin handler for the slave unit called `nrf.slaveHandler()`. Everything else is the same.

```javascript
let handler = setInterval(function() {
  nrf.masterHandler();
}, 50);
```

At this point we have all the code we need to communicate between the slave and the master. We can wrap it all in an onInit() function and save() it to the Pico so that we can take if off USB and move it around the room. Do this with the slave unit. You may not ever need to add any additional code to the slave unit.

Let's send information from the master to the slave. With the slave unit on battery power, and the master connected via USB, load the master code we have so far. Then type the following line in the console.

`nrf.sendCommand("digitalWrite(LED1,0)");`

You should see the slave light LED1. The `nrf.sendCommand()` method transmits a command string to the receiver that the receiver carries out. Along with turning on the LED, you may also get error messages. The error messages are because the `sendCommand()` method is expecting to get information back from the slave and it is expecting to do something with that information. The actual syntax is `nrf.sendCommand("cmd", callback)` where the callback function receives data from the receiver. Run the following code on the master unit (substituting your assigned addresses in line 4):

```javascript
let spi = new SPI();
spi.setup({sck:B3, miso:B4, mosi:B5});
let nrf = require("NRF24L01P").connect( spi, A5, A6 );
nrf.init([0,0,0,0,2], [0,0,0,0,1]);

let handler = setInterval(function() {
  nrf.masterHandler();
}, 50);

function resp(r) {
  console.log("OK r is "+r);
}

function toggle() {
  on = !on;
  nrf.sendCommand("digitalWrite(LED1,"+on+")",resp);
}

let on = false;
let blinker = setInterval(toggle, 1000);
digitalWrite(LED2,1);
```

The first 7 lines are what you already have had. Jump down to `blinker` on line 20. The interval timer `blinker` calls `toggle()` every second. The function `toggle()` toggles the value of on back and forth between true and false every time it is called and transmits to the slave the command to make LED1 either true or false, that is, on or off. This has the effect of making LED1 blink on the slave. The `toggle()` function also has `resp()` as its callback. The `resp()` function is designed to accept the response from the slave and display it on the console attached to the master unit. This way we can see the sort of information that the slave will transmit in response and we get rid of all the error messages. In many cases, we will just get the same "undefined" response as when we send a command directly to the Pico via USB. On the other hand, if we replace the `digitalWrite()` function with an `analogRead(B1)` function, the response will be the voltage level on pin B1 every second. Give it a try. You will see that the voltage on B1 fluctuates slightly even though there isn't anything connected there, and occasionally data doesn't get transmitted at all, but for the most part we get good responses from the slave. Attaching a sensor to B1 would make this a useful device.

As you can see, using a pair of Pico+nRF24L01's and a bit of code, we can set up both remote sensing and remote action applications.

### *• 5.2 Questions*

1.Set up a remote photo or temperature on a slave that transmits levels to the master.
2.Set up a remote buzzer. When you press a button on the master, it sounds a buzzer on the slave.
3.Work with other groups to figure out how to manage a swarm: one master, lots of slaves. Start with just 2 slaves and get them to blink reliably, then come up with something you want a bunch of slave units to do in unison under the timing control of the master.
4.Determine the range of transmission for a pair of Pico+nRF24L01's. What were the most important factors affecting transmission reliability?

<!----><a name="5.3"></a>
## 5.3  Bluetooth & RFID

>**Target**: Be familiar with Bluetooth and RFID technologies.

There are two other wireless technologies in common use: Bluetooth and RFID. Both have relatively short range transmission, often less than 10 m. They have costs involved that push them beyond the scope of this course, but that doesn't mean they are expensive or difficult to use. You should be aware of them since you may wish to use them in a personal project at some point in the future, and because you will likely encounter them routinely in devices like phones, audio equipment and in-store retail products.

### *• Bluetooth* <img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/bluetoothlogo.gif" width="25px" hover="Bluetooth logo" alt="Bluetooth logo">

Bluetooth is a UHF (ultra high frequency) radio wave technology initially developed to allow cell phones to communicate with computers, but has been applied to headphones, speakers, keyboards and many other devices. It was developed by Swedish engineers and named after the medieval Viking king Harald Bluetooth and the runes for his initials HB form the logo for the technology. Its main advantages are its low cost, low power requirements and ease of making connections between devices.

Bluetooth operates in the 2.4 GHz frequency range and while it typically connects a pair of devices, it can be employed to form a network of up to 8 devices. It uses a technology called frequency hopping spread spectrum which is beneficial both from a security standpoint as well as improving the resistance of the signal to interference and noise. Data is transmitted in packets spread across 79 designated channels. Since 2014, new versions releases (4.2 & 5.0) have focussed on providing features specifically for IoT (Internet of Things) applications. Typically Bluetooth chips look similar to RF and chips and the programming required to use them in with microcontrollers is also similar. They can often be purchased for as little as \$5.00.

### *• RFID* <img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/rfidlogo.png" width="40px" hover="Rfid logo" alt="Rfid logo">

Radio Frequency Identification (RFID) is a technology that is typically used to identify a tag at a short distance. These tags can be on a key fob, injected into a pet, attached to clothing in a store, shoes in a marathon, or taped into a library book. The tags typically are passive, that is, they require no power to transmit their identities. Their capacity to be small and operate without power are the great advantages of the technology. While there are powered tag applications, they are typically military, and work more like bluetooth devices but at greater distances.

The original concept for the technology was developed by the Soviet inventor [Leon Theremin](https://www.youtube.com/watch?v=w5qf9O6c20o) (Lev Termen), who was most famous for inventing one of the first [electronic musical instruments](https://www.youtube.com/watch?v=MJACNHHuGp0) in 1928 (think Beach Boys - Good Vibrations or [this](https://www.youtube.com/watch?v=_YYABE0R3uA)). His RFID-like device, however, was intended for espionage. It was concealed inside a gift given by the Soviets to the US in 1945 and it functioned as a bug (listening device) in the office of the US Ambassador. It was known as The Thing.

The basic idea of RFID technology is that the tag is designed to collect and retransmit the energy of the radio waves that it encounters via its antenna. The retransmitted waves are modulated (modified) in such a way that they contain retrievable information which is used to identify the tag. Imagine a mirror with a pattern molded into it. The mirror produces no light (signal) by itself but when light shines on it, the difference between the original light and the reflected light could be used to identify the mirror. None of this requires contact between the tag and the radio transmitter/receiver, but the transmitter needs to be a fairly high power device in order to empower the tag, or, the tag has to be very close to the transmitter.

### *• 5.3 Questions*

1. Compare RF, bluetooth and RFID technologies. What are their primary uses, advantages and disadvantages.

------

<!----><a name="6"></a>

# 6 - Internet of Things
###### tags: `apcsp txt` `cs`

## 6.1 The Internet

>**Target**: Be able to configure a Pico to request web pages from the internet via a WiFi connection.

### *• Computers Talking to Computers*

Our goal for this chapter is to be able to communicate with a Pico over the internet from another computer. Nowadays, computers communicate with each other all the time and it seems like a simple thing, but once upon a time the only way that computers got information from each other was when a programmer or data entry operator physically brought the data on paper and typed it in, or fed it in on cards. In the 1950's, the U.S. military's desire to [link computers in its air defense system](http://www.historyofcomputercommunications.info/Book/1/1.1-BeginningsModemCompetition-CodexMilgo56-67.html) led to the development of the *modem* (**mo**dulator-**dem**odulator). Here is a great little [video](https://www.youtube.com/watch?v=kXsodL1HkuE) that gives you a sense of how advanced things had become by 1982, but it will still seem like the dark ages to you. [Modems](https://en.wikipedia.org/wiki/Modem) take digital information, such as that produced by a computer, and encode it into an analog signal by *modulating* the signal in some way (recall using pulse wave modulation PWM in Section 3.D on servos). The resulting analog signals are produced in such a way as to make them easy to transmit. Modems also do the reverse, taking the analog signal and *demodulating* it to reconstruct the original digital information. Modems are often categorized by how much data they can encode or decode per unit of time. One such unit is *bits per second* (bps) and another is pulses per second, referred to as the *baud* rate. While bps and baud are technically not the same, there are many situations in which they are used interchangeably. Much of the communication with the Pico is at either 9600 baud or 115200 baud. You may have a cable modem with the capacity to transmit 50 to 100 times faster.

Most long distance computer to computer communication is done as [*serial*](https://learn.sparkfun.com/tutorials/serial-communication/rules-of-serial) communication, that is, bit by bit, one at a time in a single file line, or series. Protocols have to be established about the baud or bps rate, as well as about which end of the binary data to send first. For instance the binary number 10110110 could be sent with the most significant digit first (the left 1) or the least significant digit first (the right 0). Either way will work, but there needs to be a prior agreement about which way is being used or the data will become garbage. Which end goes first is called [*endianness*](https://en.wikipedia.org/wiki/Endianness). It's either going to be big-endian if the most significant (greatest place value, left side) digit goes first or little-endian if the least significant (smallest place value, right side) digit goes first. Both forms are common for various reasons. These prior agreements about how computers will communicate are called **protocols**.

### *• Protocols*

One protocol we care about in this course is the Transmission Control Protocol/Internet Protocol, **TCP/IP**, although any sort of communication between machines needs a [protocol](http://www.protocols.com/). Cell phones have their protocols, computers on a local network have their protocols, but it is TCP/IP that governs communication over the *internet*. The internet, as you know, is a network that allows several billion computers and microprocessors to communicate with each other. Anything that has enough processing power to adhere to TCP/IP can get on the internet, and even microprocessors with less power than a Pico can do that.

TCP describes a way of breaking information up into **packets**. Each packet has a header, with information like where it came from and where it's going, and a data section, which contains the information to be transmitted. The packets are passed from machine to machine until they get to their destination at which point the are reassembled and the entire message is received, and hopefully understood. There is much more going on, but this is the basic idea.

IP describes the addressing scheme that packets use in their headers, what we call the **IP address**. An IP address is assigned to each device in a network using the Internet Protocol for communication. It was originally a 32 bit number, but 128 bit address are being phased in. The address is written in 4 dot separated blocks like 192.168.1.127 (the 32 bit form). IP's on home networks often start with 192.168.x.x as you might have seen if you've played around with your router and connected devices at home. While you may have seen IP numbers while on the internet, you are likely more familiar with addresses that look like www.coolsite.com that are easier for us to remember. On the internet, there are computers called **domain name servers** (DNS) that keep track of what human readable name goes with what IP number so that you can use either one and still connect to the site that you want. If you want to know the IP address of the computer you are using, just Google "get ip". You may notice that this number can change from day to day. Again, there is much more going on, but this is the part we need to know. Together TCP/IP makes the internet work smoothly.

Another protocol that we care about is *Hypertext Transfer Protocol*, HTTP. You have seen http:// many times while surfing the web and it specifies how computers that are transmitting web pages identify each other and how they request and send pages to each other. HTTP will be the topic of the next section.

### *• LAN*

A *Local Area Network* (LAN) is a network which may or may not be connected to the internet. It may or may not use TCP/IP but most LANs do use TCP/IP and do have a connection to the internet. The IP addresses on a LAN may be fixed (static) but often are variable (dynamic) based on negotiations between the LAN's *router* and the *Internet Service Provider* (ISP) that connects the LAN to the internet. The whole process is typically managed by yet another protocol: **D**ynamic **H**ost **C**onfiguration **P**rotocol (DHCP). Here's a scenario of how it might work in your house.

You have a couple of computers and a printer. You buy a wireless router and set up a home network so that both computers can print to the printer. During the setup process, the router assigns IP numbers to each connected device using DHCP. Then you decide to get an internet account and you contact an ISP, like Xfinity, PogoZone, Clearwire or some other company that provides internet service. They bring in a modem that is connected to their internet line and connect it to your router. Then when your router is turned on, it asks the ISP server, what the IP number of your home router should be for that session, using DHCP, and then your router translates each of your home devices IP's so that they are valid for internet communication. Since the IP number assigned to the router by the ISP can change, so can the IP numbers of the connected machines on your LAN. It's more complicated than this, but hopefully you get the general idea.

### *• Wi-Fi*

Most home LANs now are wireless. Wi-Fi refers to a wireless LAN or WLAN. Wi-Fi is actually a trademark of an organization that certifies that the devices on a WLAN will play well together. There are more protocols describing how this wireless communication is supposed to happen. At present, IEEE 802.11 is most common. This is similar to, but not the same as, mobile phone standards like 3G, 4G and LTE. IEEE 802.11 currently comes in several flavors:

-a: which uses the 5 GHz band giving less interference but shorter range.
-b and g: which use the 2.4GHz band of frequencies which give longer range but are subject to interference by microwave ovens and bluetooth devices. b has a higher potential data rate than g.
-n: which can use either the 2.4GHz or the 5GHz band.

If you have a wireless network at home, see if you can find out which flavor(s) of IEE802.11 it has.

Both LAN's and WLAN's identify the network, that is, all the devices that are locally connected. If you've used connected to the WiFi at a friends house or a coffee shop you've probably seen a variety of network names. Linked to the name is a number called the SSID (Service Set IDentifier) which typically contains the network name translated into ASCII.

One issue with wireless networks is security. Since the device doesn't have to be physically connected to a network, anyone within range could potentially get on to your WLAN, which may not be a good thing. To deal with this issue, several authentication protocols have been devised. The oldest is WEP (Wired Equivalent Privacy), followed by WPA (WiFi Protected Access), and the current and best is WPA2. WEP is not very secure: its passwords can often be cracked with software tools in minutes, however older hardware may not be able to be updated to WAP so it is still in use.

### *• ESP8266*

To allow your Pico to access the internet wirelessly, it needs a device that can transmit and receive information according to the IEEE 802.11 protocol. We will be using the [ESP8266 WiFi module](https://nurdspace.nl/ESP8266). It uses IEEE 802.11b/g/n and TCP/IP, it functions as a modem, it has a built in antenna, and can to some extent be programmed as a microprocessor with assignable pins like the Pico. For simple microprocessor applications that needed WiFi, you could probably use the ESP8266 all by itself. Espruino JavaScript has even recently been installed onto ESP8266's but we will pair the Pico and the ESP8266 so we can continue in our familiar environment and have more microprocessor options. There are other similar modules, but the ESP8266 is one of the newest, smallest and cheapest.

![Figure 6.1 ESP8266 with adapter + Pico](https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/FBB270ESP8266.png "ESP8266+Pico")

*Figure 6.1 ESP8266 + Pico*

Get an ESP8266 and the yellow/blue adapter. The ESP8266 is not breadboard friendly and requires a capacitor to run reliably. The adapter provides the capacitor as well as breadboard friendly pins. Set it up according to Figures 7.1 and 7.2. The purpose of including the battery is that the ESP8266 needs more power than is typically provided by a USB cable in order to run reliably. Turn on the battery whenever using the ESP8266. In addition, communication between the Pico and ESP8266 is very sensitive to interruptions due to loose connections. You may need to wire up your breadboard with hand cut jumpers from lower gauge wire rather than using the standard machine-made ones.

<img src="https://28f7110b-3ce8-49d6-b340-8c67add3b3e0.id.repl.co/CSAssets/ESP8266wAdptr.JPG" alt="ESP8266 adapter" width="100%">

*Figure 6.2 ESP8266 + adapter*

The actual pinout is via the adapter is:

| ESP8266 | PICO | Battery |
|---|---|---|
| GND | GND | GND |
| VCC | 3.3 |  |
| CHPD | 3.3 |  |
| TXD | A3 |  |
| RXD | A2 |  |
|  | BAT | V+ |

Connect it via USB to your WIDE and send the following code:

```javascript
function test(serial, baud, pins) {
  serial.removeAllListeners();
  let l="";
  serial.on('data', function(d) {l+=d;});
  serial.setup(baud, pins);
  serial.write("AT+GMR\r\n\");
  setTimeout(function() {
    console.log(JSON.stringify(l));
  },1000);
}

test(Serial2, 115200, { rx: A3, tx : A2 });
```

Run the program and see what you get. Hopefully in the console along with some other things you will see something like `AT+GMR\r\r\nAT version:0.25.0.0`, which is an echo of what you sent, followed by the software version your ESP8266 is running.

We won't spend too much ink on how and why this code works, rather we will just use it to make sure the Pico is talking to the ESP8266 properly. There are a few features that should be familiar to you. Notice in the first line that the function test() has the parameters serial, baud and pins. When in the final line we call `test()`, we pass in Serial2 for serial, 115200 for baud and A3 for the rx pin and A2 for the tx pin. Serial refers to the fact that this modem device is going to be communicating sequentially, bit by bit on a single line, that is, in series. The rate at which this communication will be going on is 115200 baud (pulses per second), and the pins are those that we specified on the pinout (Figure 7.1).

The next line to notice is line 4:

`serial.on('data', function(d) {l+=d;});`

In this line we pass a function to the function `serial.on()` as a parameter. This is actually quite common. When we pass a function to a function as a parameter, it can be called at any point in the function. But the technique to consider here is that the passed in function is called when `serial.on()` is finished. It's like saying "I call you and tell you to do something, you call back when you are finished." In this case, `function(d) {l+=d;}` is called any time the 'data' event happens. When there is no data coming, our function is idle and the processor can be doing other things. We use *callback* functions to force JavaScript to carry out events in a particular sequence, while allowing the processor to be busy doing other things while waiting for outside events to complete. This is called *asynchronous* programming. Note that this function we pass in is defined as we pass it in rather than being a named function defined somewhere else. Either sort of function can be passed in, but this sort of unnamed function is called an *anonymous* function. What is this anonymous function doing? It is concatenating any data it is receiving onto the string variable `l` that was defined in the previous line so that at the end, the string `l` contains all the data, which at the end of the program is sent to the console. Also note that `serial.on()` is an Espruino function that has replaced `serial.onData()`. See the Espruino reference.

Another line to notice is `serial.write(\"AT+GMR\r\n\");` In this line, the Pico is sending (writing) information to the ESP8266 using something called the *AT command set*, which is commonly used to communicate with modems, and is based on a system developed for the Hayes modems described in the granny modem ad you may have viewed earlier. We still use it. AT stands for attention and GMR stands for Generic Modem Revision. Sending GMR has the effect of asking what software revision is being used by the ESP8266. There are MANY other AT commands. The \\ before the r and n is exactly what it was back in Section 1.3. It is an escape character that allows the modem to read r not as the character r, but as a carriage return, and the n as a line feed. Carriage return and line feed? Those terms come from typewriters which you may have only seen in pictures. Carriage return means that you go back to the beginning of a line and line feed means you drop down to the next line. While these concepts may seem very archaic to you today, much of the software that you depend on still has those concepts buried deep inside.

If you decide to get your own ESP8266 to play with, you will want to know how to change its firmware. There are numerous resources, but a good place to start is [here](http://www.allaboutcircuits.com/projects/update-the-firmware-in-your-esp8266-wi-fi-module/).

### *• 6.1 Questions*

1. Who was the first person to use the term "big endian" and to what did it refer
2. What is the carriage of a typewriter? What would a carriage return and line feed mean in the context of your console?
3. Do some research and describe some issues in WiFi security.
4. Try modifying the `serial.write(\"AT+GMR\r\n\");` line by replacing GMR with CIFSR. What do you get? Research the CIFSR AT code to find out what it does. Please don't mess with other AT commands, you can brick your ESP8266 if you don't know what you are doing.

<!----><a name="6.2"></a>
## 6.2 Clients, Servers & AJAX

>**Target**: Be able to use AJAX strategies to control a Pico from a webpage and to modify a webpage based on data coming from a Pico.

### *• HTTP: the purpose*

Recall that our goal in this chapter is to be able to set up communication over the internet between two computers, one of which is a Pico. We have most of the pieces already:

- We can use a browser to get onto the internet with a regular computer.

- We can use JavaScript to control the webpages in a browser.
- We can use a Pico plus an ESP8266 to get it onto the internet.
- We can program our Pico to do a lot of things.

But even though we can get both computers onto the internet, how do we use a webpage to communicate information between the Pico and the other computer? It turns out our computers can't communicate via web pages without **HTTP**.

HyperText Transfer Protocol (HTTP) is yet another set of rules about how communication happens between computers. Given the speed at which this communication takes place and the security risks involved, these protocols have to be very specific. This protocol specifically governs the transmission of web pages, but since most of us view web pages on computers, or pads, or phones that have simple GUI's, we are usually oblivious to the underlying text-based protocols. You've been using HTTP throughout this course every time you've used Brackets with a webpage or typed a URL into a browser. Even if you didn't type http:// before the URL, the browser would have added it before it actually sent the address out on the internet.

An HTTP session is a sequence of request and response transactions between a **server** (computer 1) and a **client** (computer 2). The session is initiated by the client while the server listens. Typically, a client requests a web page and the server responds by sending the requested web page. A server can serve all sorts of things besides web pages and a client can request all sorts of things besides web pages, but for our purposes, we will just work with web pages. A server can serve the same page many times to many clients. Think of a waitress in a restaurant. She may serve the same meal to many customers and she may be serving many customers at the same time, but not actually at the exact same time, rather she takes care of multiple customers, but each one at a time and they can finish their meals and request their bills at different points. This is just how things are with computer servers and clients too, but the meal is a web page.

>*You can't get into callback hell if you don't go there.*
>
>*Isaac Schlueter -- CEO of npm, formerly head of node.js*

### *• The Pico + ESP8266 as HTTP Client*

Our Pico + ESP8266 can function as a client. Paste the following code in your WIDE. Check with your teacher about the values of netid and pw, since they may have changed recently. Send the code to your Pico. Sorry for the small font size, I wanted to keep the lines unbroken as much as possible.

```javascript
Serial2.setup(115200, { rx: A3, tx : A2 });
let SSID = "Temp-Student";
let PASSWD = "TempStu1";
let WiFi = require("ESP8266WiFi_0v25").connect(Serial2, function() {
  WiFi.reset(function() {
    console.log("Connecting to WiFi");
    WiFi.connect(SSID, PW, function() {
      console.log("Connected");
      require("http").get("https://lyndenmath.org/CSAssets/wifitest.html", function(res) {
        console.log("Response: ",res);
        res.on('data', function(chunk) {
          console.log("--->"+chunk);
        });
      });
    });
  });
});
```

The first line sets the parameters for the Pico to communicate via the ESP8266 using pins A3 and A2 at a baud rate of 115200.

The `require()` function (line 4) creates an object, WiFi, based on a module from Espruino.com that allows the Pico to talk to the ESP8266 and connect to it according to the Serial2 parameters in line 1. Note that it is getting the library via the USB cable and the internet connection of the laptop, not via WiFi. The WiFi connection hasn't been established yet. The newly created WiFi object has methods like `reset()` and `connect()` that we will use.

The `WiFi.reset()` method is used to reset the ESP8266, which isn't strictly necessary but it's a good idea to start a session clean.

The rest of the process for connecting the client is written in the `reset()` methods's callback. Remember that callback functions are functions that are passed in to other functions as parameters (Section 7.1) and which are typically called when the rest of the function has completed. In this case the callback function is an anonymous function defined within the parameter section. If you look over the code you can see that not only `WiFi.reset()`, but `WiFi.connect()`, `require.get()` and `res.on()` all have callbacks and are all nested inside each other. This sort of callback inside callback inside callback, etc. is often referred to as [Callback Hell](http://callbackhell.com/). There are cleaner ways to write this code, but professional programmers are usually more interested in compactness and you need to get used to reading them.

The first `console.log()` reports that our device is beginning the WiFi connection process as soon as the reset is complete. The special Espruino ESP8266 module method called `WiFi.connect()` actually starts the connection process using the SSID and password for the WLAN. The second `console.log()` which displays "Connected" is in the call back of `WiFi.connect()`, so will only be displayed in the console after the connection has succeeded.

The `require("http")` (line 9) gets the module/library for HTTP communication from Espruino.com and uses it to request or `get()` an HTTP message (in this case the webpage wifitest.html) from whatever server is managing lyndenmath.org. When the server responds with a response message, the response message is sent to the console by the callback function as the variable `res` (response), which is a particular sort of HTTP object we will look at in more detail shortly.

The next `console.log()` displays the word "Response" followed by the properties of the res object. In our case, the properties of the `res` object are various pieces of information related to the cs1test HTML page most of which browsers normally don't display for us but which are transmitted anyhow. You should see things like the date, content type, content length, etc.

There are many details that have not been explained, but at this point you should be able to follow the logical flow of the process even without understanding how all of the code works. Most of the code we can just use as boilerplate any time we want our Pico+ESP8266 to act as a client via WiFi. This code depends on special functions written for the Pico to use specifically with the ESP8266 and they depend on the particular hardware characteristics of both devices. You can see the code module/library [here](http://www.espruino.com/modules/ESP8266WiFi_0v25.js), but we can also just call the library with `require()` and use the code as boilerplate without fully understanding it. For instance if you scroll down through the code module you can find the `.reset()` function which was called in our code, and you can see that it employs some AT commands described in Section 6.1. But it's all rather complicated, which is why a professional has written them for less experienced people like us to use.

Now back to the `get()` method. As stated earlier, `get()` requests a response from a server. The response is really a three part text string. The first part consists of a status line followed by `<CR><LF>`. The second part consists of [header fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields) separated by colons. After the header section there is a blank line made by sending `<CR><LF><CR><LF>`. The optional third section is the message data, which for our purposes is the HTML for a web page. This string can be parsed into something that looks more like a multi-property/field object, such as what you should see in the console.

The syntax of the `http.get()` function is `http.get(options, callback(res))` where options is typically a URL in quotes as it is in our example, but can also specify any number of header fields that are being requested from the server. `res` is the response object itself which is passed directly to the callback function. It is considered to have arrived as soon as the headers have arrived, that is, the callback will run even before the data arrives. Servers will typically send some default header fields even if none were requested in the `get() options`, for instance Content-Length. The data (webpage HTML) will eventually come in chunks, typically about 64 characters in length. The `get()` method automatically ends when all the data has been received.

The `function(res){}` callback is an anonymous function with the response object as a parameter. It sends `res` to the console which displays all the headers, although using something like `res.date` instead would give only that specific field. The callback uses `res.on('data', callback)` to send the data to the console as each chunk arrives. `res.on('data', callback)` happens "on" the data event, that is, when each chunk of data arrives. This means the res.on() function continues to be called until all the data arrives. The callback of `res.on()` automatically receives the data as its parameter.

Much of the preceding code is dependent not only on HTTP functions like `get()` but on nonstandard JavaScript functions like `res.on()` derived from the node.js environment. This makes it especially confusing, but also opens up additional avenues of discovery for you. With the knowledge you have so far, you should be able to manipulate this code to do what you need it to do.

### *• The Pico + ESP8266 as HTTP Server*

The Pico+ESP8266 can also function as a web server on a LAN, providing webpages to clients that request them. This gets us to our goal of communicating with a Pico across the internet because we can use any internet connected computer to interact with the webpages that the Pico serves up and in so doing, send information to the Pico and receive information from the Pico. Because these devices are small and limited, the web pages to be served can't take up much memory and they can only serve 5 clients at a time. However, that is still plenty for our purposes.

To set up the Pico+ESP8266 as a server, we can use code very similar to the client code we used before (see code block below). If you compare this code to what we used before, there are only three changes. The first is the use of the `WiFi.getIP()` method (line 9) which determines the server IP and sends it to the console. We need to know the server IP in order to point the client browser to it.

The second change is that instead of the `require("http").get()` method that we used for the client to get a page, we use the `require("http").createServer().listen()` method (line 10) to set up the server to listen for a page request and designate that the function pageHandler be carried out when a request arrives. Note that the parameter 80 set in the `listen()` method indicates which port the server will listen to. Ports became necessary when computers began running more than one internet accessing program simultaneously. Computers generally only have one physical connection to the internet, but since more than one program can be using that connection, they keep the data separate by specifying different port numbers in the TCP data header. 80 is the standard port number for HTTP data. Email is often moved on ports 25, 110 and 143 depending on the kind of email. Secure HTTP, known as HTTPS uses port 443. Since the numbers are 32 bit, port numbers can range from 1 to 65535. You may have set the port number in Chapter 6 when you connected to an Android device with DroidScript. The port number was after the colon.

```javascript
Serial2.setup(115200, { rx: A3, tx : A2 });
var SSID = "Temp-Student";
var PASSWD = "TempStu1";
var WiFi = require("ESP8266WiFi_0v25").connect(Serial2, function() {
  WiFi.reset(function() {
    console.log("Connecting to WiFi");
    WiFi.connect(SSID, PASSWD, function() {
      console.log("Connected");
      WiFi.getIP(console.log);
      require("http").createServer(pageHandler).listen(80);
    });
  });
});
```

The third code change was that we didn't need to collect incoming data for display, so nothing about the `res` object here. Instead, the server receives a request object, `req`, from the client and it will need to be able to send a `res` object back to the client. Both of these objects are automatically passed to the `pageHandler` function by the `createServer()` method.

The response from the server should be a webpage. We will use the simple webpage below that creates a couple of buttons.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>LED Buttons</title>
</head>

<body>
  <button type="button" onclick="ledon()">LED ON</button>
  <button type="button" onclick="ledoff()">LED OFF</button>
  <p id="ledstat">LED Status: OFF</p>
</body>

<script>
  function ledon() {}
  function ledoff() {}
</script>

</html>
```

We will send this page as our response via `pageHandler()`. In addition to the HTML we also need to send the HTTP status number 200 in the header, which means the requested page was found OK. If we used 404, it would indicate the page was not found. We can send it all line by line as follows in the partial example:

```javascript
function pageHandler(req, res) {
  res.writeHead(200);
  res.write('<!DOCTYPE html>');
  res.write('<html lang="en">');

etc.
```

But this is rather tedious. It is more convenient just to put everything in a long string with carriage returns (\r) and line feeds (\n) as needed. Fortunately there are websites that can take our html and do that conversion for us and also properly manage the quotes and other special characters. Use [www.espruino.com/File+Converter](http://www.espruino.com/File+Converter) to try this out. You should get the following result:

```html
"<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n <meta charset=\"utf-8\">\n <meta name=\"viewport\"content=\"width=device-width, initial-scale=1.0\">\n<title>LED Buttons</title>\n</head>\n<body\>\n<button type=\"button\" onclick=\"ledon()\"\>LED ON</button>\n<button type=\"button\" onclick=\"ledoff()\">LED OFF</button>\n<p id=\"ledstat\">LED Status: OFF</p>\n</body>\n <script>\n function ledon() {}\n function ledoff() {}\n </script>\n</html>"
```

You can put a variable name on this and then just `res.write()` the variable name, which gives us a `pageHandler()` function as follows (don't forget to put the semicolon at the end of the long string):

```javascript
let page = "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n <meta charset=\"utf-8\">\n <meta name=\"viewport\"content=\"width=device-width, initial-scale=1.0\">\n<title>LED Buttons</title>\n</head>\n<body\>\n<button type=\"button\" onclick=\"ledon()\"\>LED ON</button>\n<button type=\"button\" onclick=\"ledoff()\">LED OFF</button>\n<p id=\"ledstat\">LED Status: OFF</p>\n</body>\n <script>\n function ledon() {}\n function ledoff() {}\n </script>\n</html>";

function pageHandler(req, res) {
  res.writeHead(200);
  res.end(page);
}
```

Add this above your server setup code and send it all to your Pico. When it has connected to the WiFi, use a browser to go to the url in your console and view the page. The buttons won't do anything yet, but we're getting close. Note that `res.end()` is just like `res.write()` but we use it to indicate that it contains the last piece of data to be sent. Since we're sending it all at once, all of it is the last data to be sent, so we use `res.end()`.

Finally, we need to be able to interact with the Pico from the webpage. Specifically, we would like to be able to push buttons on the page, have lights turn on and get status reports back from the Pico onto the webpage. To do this we will use AJAX.

### *• AJAX*

**AJAX** is short for Asynchronous JavaScript + XML. AJAX isn't really one thing, rather it is a strategy of using several technologies to allow clients and servers to exchange information in the background, without reloading webpages. The specific technologies involved are HTML, the DOM, JavaScript, HTTP and the XMLHttpRequest object. Since we've already worked with the first four, we only need to focus on the last one here.

The XMLHttpRequest object defines a programming interface for transferring data between a client and a server and despite the name, we don't need to use **XML** (which is another markup language similar to HTML). Such interfaces are often referred to as API's (**Application Programming Interface**).

The way we will implement AJAX on our webpage is by creating a new XMLHttpRequest object whenever the ON or OFF button is pressed. At present the `ledon()` and `ledoff()` functions don't do anything so we will put the new object there as follows:

```javascript
function ledon() {
  var req=new XMLHttpRequest();
}
```

The code for `ledoff()` would be the same except wherever there is a ledon, you would put ledoff.

We create the XMLHttpRequest object with the new constructor, which is something we've mostly avoided but we need it here, and we name it `req`. The `req` object has a number of properties that we can make use of. The `onreadystatechange` property stores a function which is automatically called whenever the state of the request changes. There are four possible states of the request:

-0 means nothing has happened yet
-1 means the server connection has been established
-2 means the request has been received by the server
-3 means the server is processing the request
-4 means the response to the request is ready

We can access the state number through the `readyState` property. The point of `onreadystatechange` is that we don't know how long we will need to wait for the server and we can monitor the changes as they take place. The `req` object also has a status property that will contain the HTTP status number, hopefully 200. Finally the `req` object has a `responseText` property that contains whatever data string the server sends. We can use these properties along with two methods: `open()` and `send(`)` to set up the exchange of information as follows:

```javascript
function ledon() {
  var req=new XMLHttpRequest();
  req.onreadystatechange = function() {
    if (req.readyState==4 && req.status==200) {
      document.getElementById("ledstat").innerHTML = req.responseText;
    }
  }
  req.open("POST","ledon", true);
  req.send();
}
```

Again, just replace the ledon's with ledoff's for the `ledoff()` function. Let's work through the logic. First we create the XMLHttpRequest object `req` in line 2. Then we set up a way to monitor the progress of any requests in line 3. Then `if` the request has been processed and is ready and there haven't been any problems with the webpage, we change the contents of the `<p id="ledstat">` paragraph to be whatever string has been sent from the server in line 5. In this way we get data from the server whenever we press one of our buttons. The `req.open()` specifies the type and content of the request. It has several possible parameters in the form of `open(method, url, async, uname, password)`:

-*method* can be "GET" or "POST", the former is standard, the latter
is more robust.
-*url* is supposed to be the location on the server of the requested
information. It is NOT the url the request is sent to. We can
actually put any string here that we want, it doesn't have to be a
url, the request will still go to the server we have already
connected to.
-*async* should always be "true"
-*uname* and *password* are strings. Again, we could put whatever
string we wanted here.

With the exception of method and async, the other parameters provide us with places to send info to the server. In this example, we are sending information "ledon" about which button has been pressed on the webpage. The `send()` method sends the request to the server.

Now we need to look at the server side of things. At present, our `pageHandler()` function only knows how to send back our webpage. It isn't looking for a POST or any other information contained in the `req` object and it isn't sending back a responseText. Consider the following additions to `pageHandler()`:

```javascript
function pageHandler(req, res) {
  var status = "na";
  if (req.method=="POST") {
    if (req.url=="/ledon") {
      digitalWrite(LED1,1);
      status = "LED Status: ON";
    }
    if (req.url=="/ledoff") {
      digitalWrite(LED,0);
      status = "LED Status: OFF";
    }
    res.writeHead(200);
    res.end(status);
  }
  else {
    res.writeHead(200);
    res.end(page);
  }
}
```

When `pageHandler()` gets a request (`req`) it checks to see if its method is POST (line 3). If it is, we are receiving our XMLHttpRequest `req`, otherwise (`else`) it's just a standard page request `req` and we send the page. 

Now if `req.method` is POST we check the value of the `req.url` property (lines 4 and 8). It will either be /ledon or /ledoff. The / gets attached to whatever is in the `req.url` property because it's assumed to be a path name. We then turn on LED 1 if `req.url==/ledon` and turn off LED1 if `req.url==/ledoff`. Finally, we put some text in the string variable status that was declared at the top of the `pageHandler()`. We then send it back to the client as a response, but not a webpage, using `res.end(status)`. The client receives this information as the value of the `req.responseText` property, that is, the text response of the request. The webpage has been listening and waiting for the response, and when it arrives, it displays it on the page as either LED Status: ON or LED Status: OFF. In this way we can send information from the server to the webpage any time an XMLHttpRequest is sent. You might think that it would be easier to just have the webpage change its own ON/OFF status whenever the button was pushed, but then the page would display ON immediately even if it took several seconds for the request to arrive at the server or even if the request never arrived at the server. By doing it the way we did, we know ON isn't displayed until after the `digitalWrite(LED1,1)` command has been processed by the Pico.

By using similar AJAX techniques, you can exchange any sort of information between a webpage and a Pico and using JavaScript you can have the webpage and the Pico to respond to that information. This sort of internet based communication between webpages and everyday devices with embedded microcontollers is what the **Internet of Things** is all about. To put it in perspective, an ESP8266 can run Espruino JavaScript all by itself and it has pins that can work with sensors or motors. It costs less than \$2 and would be small enough to incorporate into nearly any device (Thing). In turn it could send data via WiFi to a LAN or the internet. And there you have the Internet of Things (IoT).

New tools to make IoT projects easier are coming out all the time. One free tool that could be used with JavaScript and an ESP8266 is called [Mongoose](https://www.cesanta.com/products/mongoose-iot). [Here's ](https://vimeo.com/161664749)an interesting example of IoT developed with Mongoose. Hopefully you have enough background with JavaScript, Android apps and microcontrollers that you can imagine how IoT projects like that one could be pulled off. 

### *• Section 6.2 Questions*

1. Rewrite the client connection code in the **The Pico+ESP8266 as HTTP Client** subsection so that it doesn't use so many nested functions. Can you get rid of callback hell? Go to [callbackhell.com](http://callbackhell.com/) for suggestions.
2. Use Ajax strategies to control a motor from a webpage.
3. What are some IoT projects that you can imagine?

<!----><a name="a"></a>
# Appendices

## Appendix 1 - Syntax Quick Reference

### **alert( );**

Requires string in quotes or a variable containing either string or number.

`alert("In fifty years you'll be " + nextage);`

### **array = [ ];**

The best way to declare an array is using the literal syntax below, either with or without elements. Finally, the third example is a common structure to traverse the array and report each item.

```javascript
firstArray = [];
secondArray = ["bob", "carol", "doug", "elizabeth"];

thirdArray = ["a","b","c"];
for (var i=0; i<thirdArray.length; i+=1) {
  console.log(thirdArray[i]);
}
```

### **button**

Note the change to single quotes inside the alert( ) when JavaScript is used in an HTML context.

`<button type="button" onclick="alert('Hello World!')">Click me</button>`

### document.**getElementById( )**

You must have something with an id before you can access it using getElementById( ).

```html
<script>
var changeColor = function() {
  var p = document.getElementById("para1");
  p.style.color="red";
}
</script>

<p id="para1">What color am I?</p>
<button type="button" onclick="changeColor()">Click me</button>
```

### **for**( )

`for (where it starts; how long it goes; how it increments) {what happens}`

```javascript
for (var i = 0; i < 9; i+=1) {
  console.log(i);
}
```

### **form**

The name attribute does NOT need to be "inputbox", but you DO need to use the keyword "form" as demonstrated. The function name is up to you.

```html
<script>
var inputdemo = function(form) {
  alert("You typed " + form.inputbox.value);
}
</script>

<form>
Enter something in the box:
<input type="text" name="inputbox">
<input type="button" value="SEND IT" onclick="inputdemo(this.form)">
</form>
```

### **function( )**

Functions can be declared several ways; you should be familiar with all of them. As demonstrated below, the first form is a *function statement* using the function constructor to create a function named `square()`. Note the lack of ending semicolon. The second for is a *function expression* where an anonymous (unnamed) function is assigned to the variable `square`. Note the semicolon ending. The third form also creates an anonymous function but it is typically used in a callback structure as shown. Functions can have as many parameters as necessary. When a function contains a `return`, the function is exited as soon as the `return` is encountered.  If the function does not have a `return`, it gets the value *undefined*.

```javascript
function square(x) {
  return x * x;
}

var square = function(x) {
  return x * x;
};

setTimeout(function() {console.log("square")}, 1000);
```

### **if**( )

Can have multiple boolean conditions inside the ( ).  Whatever is in the curly braces that follow a true condition are carried out.

```javascript
if ((school == "LHS") && (city == "Lynden")) {
  alert("Your colors are green and yellow");
  alert("Your mascot is a lion");
}
```

### **if( ) { } else( ) { }**

An `else` could also be followed by a nested `if`, or even a series of them.

```javascript
if ((school == "LHS") && (city == "Lynden")) {
  alert("Your colors are green and yellow");
  alert("Your mascot is a lion");
} else {
  alert("You aren't from LHS");
}
```

### **innerHTML**

You must have an object (HTML element) assigned to a variable (probably using getElementById) before you can use .innerHTML with it:

```html
<script>
var changeMe = function() {
  p=document.getElementById("para1");
  p.innerHTML = "I'm different!";
}
</script>

<p id="para1" onclick="changeMe()">Click me to change me.</p>
```

### **input fields**

Input fields can be used on webpages to get user data. They can have various attributes

`<input type="text" value="Type here" size=30>`

### **layouts (DroidScript)**

The basic organization of a DroidScript layout works for buttons and fields just like for images. First `app.Create` the layout, then `app.Create` the objects to go on the layout, then `.AddChild` the objects to the layout, then `.AddLayout` the layout to the app. Order matters.

```javascript
lay = app.CreateLayout( "linear", "FillXY" );
imgThing = app.CreateImage("Img/rocket.png");
lay.AddChild (imgThing);
app.AddLayout( lay );
```

### **Number( );**

Requires quoted string that looks like a number or variable containing string that looks like a number.

`var actualNumber = Number("10");`

### **onkeydown**

Waits for a key to be pressed and can be attached to a handler function.  The key event is passed to the function as its parameter.

```html
<script>
document.onkeydown = function(k) {
  alert(k.keyCode);
}
</script>
```

### **oscillation**

VAL oscillates continuously between 1 and 10, incrementing every time the oscillate() function is called. In this case, oscillate is called 100 times by a for loop.

```javascript
let VAL = 1;
let D = 1;

function oscillate() {
  console.log(VAL);
  if ((VAL >= 10)||(VAL <= 0)) D = -1*D;
  VAL = VAL + D;
}

for (i = 1; i < 100; i += 1) {
  oscillate();
}
```

### **random numbers**

How to create a random number between 1 and 6.

```javascript
var rolldice = function() {
  var dice = Math.ceil(Math.random()*6);
  return dice;
}
```

### **setInterval(function, ms);**

The first example shows how to set `timer1` to call `somefunc()` every 500 ms. Notice we don't include the parentheses after `somefunc()` inside `setInterval()`. The second example shows how it would look to define an anonymous function inside the `setInterval()` which you may commonly see. The `clearInterval()` function would terminate `timer1` but not `timer 2`.

```javascript
var timer1 = setInterval(somefunc, 500);
var timer2 = setInterval(function() {
  line 1;
  line 2;
}, 500);

clearInterval(timer1);
```

### **setTimeout(function, ms)**

This is generally a one use timer used to delay the execution of a function call. Do not use parentheses after the function name inside `setTimeout()`.

`var timer = setTimeout(somefunc, 500);`

### **string methods**

How to slice off a first name.

```javascript
var fullname = "Jeff Seely";
spaceloc = fullname.indexOf(" ");
firstname = fullname.slice(0,spaceloc);
```

### **svg elements**

Showing viewport definition inside `<svg>` tag. Showing event handling for the `<g>` group. Showing text on top of (first item is in back) circle. Showing `attribute="value"` syntax.

```html
<svg width="100" height="150">
  <g onmousedown="btnDown()" onmouseup="btnUp()" cursor="pointer">
    <circle id="btn1"
            cx="50" cy="40" r="35"
            fill="yellow" stroke="green" stroke-width="6" />
    <text x="20" y="47" 
          style="fill:green; font-size:20px; font-family:Helvetica;"
          CLICK</text>
  </g>
</svg>

```

### **switch case**

```javascript
let answer = prompt("What is your favorite color?");
switch (answer) {
  case "red":
    alert("hearts, strawberries");
    break;
  case "blue":
    alert("ocean, jeans");
    break;
  default:
    alert("nice color");
}
```

<!----><a name="a2"></a>
## Appendix 2 - SVG Graphics

### *• SVG*

While we can make visually interesting things on webpages with buttons, they are rather limiting. We need more visual tools. There are two main graphics display systems available to us. One is Scalable Vector Graphics (SVG) and the other is the HTML5 Canvas. The Canvas is something you are likely to learn about in a web design class although it is completely dependent on JavaScript and only folks with a JavaScript background can do anything more with it than copy and paste other people's code. It has advantages and disadvantages when compared to SVG. In this course, we will focus on SVG, which is used not only in a webpage environment but in other forms of publishing and animation. Once you know SVG, you can teach yourself Canvas if you want.

SVG, like HTML, is another markup language, but it was developed primarily for graphics rather than text. Also, as with HTML, JavaScript can access the various markup elements and change them over time or in response to user events. In this course, our primary use for SVG is to build *graphical user interfaces* (GUI's) although it can and is used for non-interactive graphics. Before we do much with JavaScript, we need to know what some of the elements are and how to work with them. I will only introduce a few. If you need more, you can look them up at w3schools or MDN for details. All the basic elements work in a way that should seem familiar to you by now.

### *• Some SVG Elements*

Let's start with a circle. We didn't have any circles with HTML. The following SVG code is all you need to create a circle on a webpage. Pop it into some boilerplate in a Real.it.

```html
<svg>
<circle cx="50" cy="50" r="40"
        stroke="green" stroke-width="4" fill="yellow" />
</svg>
```

The `<svg>` tags tell the browser that we are using SVG inside them. The `<circle>` tag is really one long line that I've chopped up grouping related attributes on their own line. Like HTML, SVG doesn't care about carriage returns. There is no end tag for most SVG elements, rather they have a forward slash on the right end of the single tag (/>). The attributes are self-explanatory, but play with the values to see what can be done. If you make the radius really big, like 400px, you discover that there is a rectangular box in which we are viewing our graphics. This box is called the viewport and it is normally set by adding width and height attributes into the `<svg>` tag as follows: `<svg width="200" height="200">`. This creates a port through which the elements we create can be viewed. The (0,0) point of the viewport is in the upper left corner of the browser display window as usual. If any of our elements are too big to be viewed through our viewport, we won't see the whole object. In that case we will need to either make the viewport bigger or the object smaller. Think of the viewport as a window through which you are viewing your object which exists behind the window. Try out different viewport dimensions and different circle centers and radii. Note that this SVG viewport is not the same thing as the HTML viewport that is referred to by your HTML boilerplate.

Look up the `<rect>`, `<ellipse>` and `<line>` elements, try them out and make sure you can use them.

You can make as complicated a shape as you want in SVG using the `<path>` element, but the contents of the tags can get really ugly. [Joni Trythall](http://svgpocketguide.com/book/#section-2) does a fine job of explaining the details (without the math!) if you want to create and modify more complex shapes. For now we will look at basic shapes since whatever you can do with the basic shapes you can also do with more complex ones.

One element in SVG that does have start and end tags is the `<text>` element. Here's an example to paste between some `<svg>` tags:

```html
<text x="0" y="40"
      style= "fill:none; stroke:#00cc00; font-size:48px;">I love SVG!</text>
```

This single long line of code brings up a couple of points. First, most of the style properties that we have seen already can be used with SVG elements and text. Second, colors can be specified by number rather than name in order to get a greater variety. The numbers we use are base 16, otherwise called **hexadecimal**, or hex for short. They are distinguished from base 10, or decimal numbers, by the # to the left of the number. They not only use the digits 0 through 9, but 10 would be a, 11 would be b, 12 would be c, and so on until 15 would be f. What we write in decimal as 16, would then be 10 in hex. So 3b in hex would correspond to (3 x 16) + 11 = 59 in decimal numbers. Having a hex number with 6 places like these, provides 16^6^ = 16,777,216 different color options.  If you Google "hex color picker" you get a nice little app that helps you with the hex value for any color you want.

### *• Events and SVG*

SVG objects can be effected by user initiated events just like HTML buttons can be. Paste the example below inside the body of some boilerplate and run it. Then we'll look at how it works.

```html
<svg width = "100" height = "150">
  <circle id = "disc" cx="50" cy="40" r="35" fill="green" />
  <g onmousedown = "btnDown()" onmouseup = "btnUp()" cursor = "pointer">
    <circle id= "btn1" cx= "50" cy= "40" r= "35"
            fill = "yellow" stroke="green" stroke-width="6" />
    <text x = "20" y = "47" 
            style="fill:green; font-size:20px; font-family:Helvetica;">CLICK</text>
  </g>
</svg>

<script>
let level = 40,
d = document.getElementById("disc"),
b = document.getElementById("btn1");
function dropdisc() {
  level = level + 20;
  if (level>180) level=60;
  d.setAttribute("cy",level);
//d.cy.baseVal.value = level;
}

function btnDown() {
//b.setAttribute("fill","green");
  b.style.fill = "green";
}

function btnUp() {
  b.style.fill = "yellow";
  dropdisc();
}
</script>
```

First we need to deal with a few things you've never seen before. We'll start with the pair of `<g></g>` tags in lines 3 and 8. This tag stands for *group* and it groups together any SVG elements between the tags as though they were one object. If we want all of the objects to move together or for a click on any of them to cause the same response, we should group them this way. The elements in the group are a circle and some text. These two elements form the yellow "CLICK" button.

The next new thing is `cursor="pointer"` at the end of line 3. Take out that attribute and see what happens if you move the cursor slowly onto the text of the button. This is just one of a zillion commands available in the language. English has a lot of words too.

The last new thing is in the `<script>` section. Since there is an SVG object model in the DOM we can use JavaScript to change whatever we want. To change the properties of SVG objects we can use either an object method like `setAttribute()` (line 18) or we can use dot notation (line 19). Both methods are shown although one or the other is commented out. You can use either method or both, but you have to pick one method for any particular property. For the sake of avoiding bugs, it is advisable to pick one and stick with it. The rule of thumb with dot notation is things that seem like styles probably require style in the dot notation and other values, especially numeric values probably require baseVal.value *after* the property.

It should be noted here that you can't use the `getElementById()` method until after the element is created. So in this case, we need to put our `<script>` section after the SVG code that creates the elements.

Everything else you've either seen before, or seen something very similar before. Can you see how it they all work together? First we create a CLICK button and hide another green circle of the same size behind it. What makes things behind or in front? The order that we create them in the `<SVG>` section. Then we create functions that are triggered when there is a mousedown or mouseup on the CLICK button. Then we create a function that moves the hidden green circle down each time that our CLICK button is clicked until it goes out of the viewport at which point we start it over again behind the button. We put this function that drops the green circle down inside of our mouseup function.

### *• Complex SVG Elements*

Basic shapes are nice, but you may want something a tad more complex. As noted earlier, you can create this with the `<path>` tag, but it's easier to let a computer program do the heavy lifting for us. In a browser (Chrome works best), go to [editor.method.ac](http://editor.method.ac/). This is an application called *Method Draw* that can help you create more complex SVG elements. You can see along the left side tools for freehand drawing, straight lines, rectangles, ellipses, paths, a shape library, and text. Color choices are at the bottom. Try a few of the drawing tools and experiment with changing color. Get familiar with the GUI. You can find an [introduction to *Method Draw*](#*• method-draw*) later in this section.

Now clear your work area and go to the shape library and pick the ![Method shape](https://lyndenmath.org/CSAssets/methodshape.gif "Method shape") shape and draw the shape towards the upper left of the canvas. By dragging down on the **Width** and **Height** boxes in the **Canvas** section on the right side, shrink the canvas so that it is just big enough for the shape. We do this so our shape doesn't have a lot of white space included around its edges when we put it on our HTML page. Go to **View → Source** and it gives you the SVG code for the shape. The important parts are the width and height numbers (make a note of them) and the `<path>` tag which should look something like this (your numbers will vary):

```html
 <path id="svg_4" d="m294.774506,104.176659c-8.835938,0 -16,7.16346
-16,15.999794c0,8.836548 7.164063,15.999756 16,15.999756 c8.835938,0
16,-7.163208 16, -15.999756c0,-8.836334 -7.164063,-15.999794
-16,-15.999794zm-2.570313,26.705956l-3.892578,
-3.896194l6.810547,-6.810944l-6.810547,-6.810463l3.892578,-3.892807l10.705078,10.70327
l-10.705078,10.707138z" stroke-width="1.5" fill="#000"/>
```

Copy your entire `<path>` tag and paste it into some boilerplate, inside `<svg>` tags in your editor. Add the width and height information to the `<svg>` tag. Save it as a .html document and preview your page. You should see the shape on your page. Coming up with the path description from scratch would be a pain, but once we have it, we can treat it like any other SVG element. Notice that Method Draw gave it an id for us at the beginning of the path description. You are free to modify the id name, and the stroke-width and fill colors at the end of the tag.

### *• SVG Transformations*

We have seen that we can change the position of an SVG element by modifying its definition, like changing `cx="40"` to `cx="50"` in a circle element. But another way to modify SVG elements is by including a transform attribute. We'll look at three common transformations but there are others that you can look up.

The first kind of transform is `transform="translate(x y)"`. Put numbers into the `x` and `y` spots to move in the x and y directions (comma between is optional) and place it at the end of an element tag (even a `<g>` tag will work). The position of the element will move accordingly. Don't forget, if your x and y are large, you may move your element past the viewport and no longer be able to see it. Give it a try on your ![Method shape](https://lyndenmath.org/CSAssets/methodshape.gif "Method shape")shape by adding a translate to its `<path>` tag.

One of the advantages of SVG is the scalability of the graphics. We can make them as big as we want and they don't get fuzzy or *pixelated*. The easiest way to scale `<svg>` elements is to use the `transform="scale(s)"` method. Modify the `<path>` tag for your shape to change its scale rather than translate it. Keep paying attention to your view port, or you can just make your viewport really big.

Finally, there is a `transform="rotate()"` method. The rotation is in clockwise degrees, but you have to pay attention to the center of rotation. It isn't the center of your element, rather it is the (0,0) point of the element, that is, the upper left corner. Take out any other transforms and put `transform="rotate(45)"` into your `<path>` tag. It rotates, but not from the center of the element. If you want to rotate from the center you need to add that information into the transform method. Let's say we have an element whose width and height are both 40 (you should have put the size of your element in originally as the width and height of your viewport). The center of a 40 x 40 element would be (20, 20). We can rotate from the center by using `rotate(45 20 20)`. Give it a try.

Suppose you would like to put multiple transformations on an element. Just list them inside the quotes: `transform="rotate(45) scale(2) translate(50, 100)"`. Give it a try. Note that you can get different results depending on what order you do the transformations; in particular, translating first and rotating second does not necessarily give the same result as rotating first and translating second.

### *• SVG Animation*

In a previous example we animated a green disc, but for the disc to move the user had to keep clicking a button. What if we want things to move on their own while the user watches? You might guess that we could put a `setAttribute()` method for some SVG element inside of a for loop and have the loop keep changing the value of the attribute, such as the x or the y. This should cause the element to move across the screen before our eyes. Unfortunately, JavaScript can cycle through for loops much faster than browsers can update webpages. All we would see on the screen would be the beginning state and the ending state, nothing in between. Instead, we should use a `setInterval()` timer as we have in the past. Paste it into an HTML boilerplate body and see how it works. Make sure you get all of the code.

```html
<svg width="100" height="70">
  <g>
    <ellipse id="ring" ry="30" rx="30" cy="32" cx="32"
             stroke-width="2" stroke="black" fill="yellow" />
    <rect id="mark" height="59" width="6" y="2" x="29"
             fill="black" transform="rotate(90 32 32)" />
    <ellipse id="hole" cx="32" cy="32" rx="12" ry="12"
             stroke-width="2" stroke="black" fill="white" />
  </g>
</svg>

<script>
let timer1 = null,
m = document.getElementById("mark"),
mAngle = 90;
function startAnimation() {
  timer1 = setInterval(animate, 20);
}

function stopAnimation() {
  clearInterval(timer1);
}

function animate() {
  let speed = 15;
  if (mAngle>360) {mAngle = speed;}
  mAngle = mAngle + speed;
  m.setAttribute("transform","rotate(" + mAngle + " 32 32)");
}
</script>
<br>

<input type="button" value=" START " onmousedown=
       "startAnimation();" onmouseup="stopAnimation();">

```

First lets look at the SVG group `<g>` in lines 2 - 9. The graphic is made of a larger yellow circle called ring centered at (32, 32) defined in lines 3 to 4. On top of that is drawn a long skinny black rectangle called `mark` (lines 5 - 6) which has a rotate transformation of 90º around its center, also (32, 32), the center of the whole group. On top of that is a white circle called `hole`, also centered at (32, 32) defined in lines 7 - 8. 

Now look at the script. We start by setting up a global variable for an interval timer called `timer1`. We need it to be global so that both our `startAnimation()` and our `stopAnimation()` functions can refer to it. Since we haven't created the interval timer yet, we set `timer1` to null, which is no value, but neither zero nor undefined. Our next variable `m` points to the SVG element/object `mark` that we want to be able to manipulate. Finally we set up a global variable `mAngle` that we will use to keep track of the current rotation angle of `mark`. It starts out at 90 degrees.  

Now consider the function called `animate()` which rotates the graphic. We start with a variable that adjusts how many degrees per call `mark` will rotate. It is named `speed`, since the higher it is, the faster `mark` will rotate. Then we add speed to our current angle and stick it back into `mAngle`, which makes the angle of rotation grow. Next (line 28) we adjust the rotation angle of mark using `setAttribute()`, which has the effect of rotating `mark` on the page. This implementation of `setAttribute()` requires some concatenation. It's ugly, but it works. Finally, can you see the purpose of the `if` statement? (line 26)

Now if we repeat the rotation we have animation. Look at the `setInterval()`. Notice that it calls the function called `animate` every 20 ms. Also understand that the `setInterval()` function returns an ID that is stored in our variable `timer1`. You can have more than one interval timer running in a program, so in order to start and stop the right timer, you need to name them by assigning their ID to a variable, in this case `timer1`. The variable was declared at the beginning of the script, outside the function, so that it could be used anywhere in the script, not just inside the `startAnimation()` function. `timer1` was initially assigned the value null. Null is placeholder value given when a variable has not yet been assigned an actual value. The point of the `startAnimation()` and `stopAnimation()` functions are to start the timer triggering the `animate()` function at a given rate and to stop it, respectively. These same techniques can be used to animate any attribute of any SVG graphic or group of graphics.

As noted at the beginning of the section, SVG is another markup language like HTML, in particular it is a dialect of XML, like MathML and others. Sometimes these dialects use the same tags to mean different things which can cause problems for the browser or whatever software is trying to make sense out of a file that may be composed of multiple dialects of XML. To avoid confusion and processing errors, it is recommended that the dialect or namespace be declared in the SVG tag, or whatever the root tag is in the XML dialect in question. It looks like this:

`<svg xmlns="<http://www.w3.org/2000/svg>">`

and tells the browser that it can find out what the tags mean at the given location. I have not included this in the examples for simplicity sake, but it is good practice for you to do so.

Finally, with the small programs we have been writing, it doesn't really matter whether you put scripts in the head, the top of the body above SVG stuff, or the bottom of the body below everything else, or in a separate file. When scripts get longer and the time it takes them to load becomes noticeable, it is best to either put them at the bottom of the body or in a separate .js file that the HTML file can refer to.

### *• Rotating SVG Groups*

Here's an example of how to rotate an entire SVG group independently from it vertical can horizontal shifting.

```html
<!DOCTYPE html>
<!-- This demo shows how to rotate an SVG group independently from its vertical
and horizontal shifting. Jeff Seely for LHS Computer Science 2017-->

<head>
	<title>SVG Rotation+Shift Demo</title>
</head>

<body>
	<!-- There can be more than one <svg> and more than one <g> nested inside this
	outer <svg>.  You can't manipulate the x and y of this outer <svg> -->
	<svg width="350" height="300">
		<rect x="5" y="5" width = "340" height = "295"
			style="stroke: black; fill: pink;"/>
		<!-- To manipulate x and y with JS the svg block must be inside another.
		This creates an svg frame that can be moved wherever you want-->
		<svg x="0" y="0" id="sframe1">
			<!-- You must determine the center of rotation for the group, in this case (40,40)-->
			<g id="grp1">
		 		<rect x="20" y="20" width="40" height="40"
		           style="stroke: green; fill:green;"/>
				<circle cx="40" cy="40" r="20"
							 style="stroke: green; fill:white;"/>
				<rect x="30" y="30" width="20" height="20"
					     style="stroke: green; fill:green;"
							 transform = "rotate(45 40 40)"/>
							 <!-- This tranform rotate is from the perspective of the group only. -->
							 <!-- The yellow circle below is deliberately offcenter to demonstrate rotation
							 around a center that isn't its own. -->
				<circle cx="60" cy="40" r="10"
							 style="stroke: green; fill:yellow;"/>
			</g>
	 	</svg>
	</svg>
	<script>
		var cx = 40, cy = 40; //initial center of rotation automatically shifted with the svg frame
		var s1x = 0, s1y = 0; //initial svg frame locations
		var angle = 0; //initial angle
		var angspeed = 20; //degrees per interval
		var spin = 1; //1 is clockwise, -1 is counterclockwise
		var xspeed = 8, yspeed = 12; //speed of movements
		var framerate = 30; //ms for setInterval
		var loop1 = null; //initialize the interval timer
		
		var t1 = document.getElementById("test"); //get the svg object to manipulate
		var s1 = document.getElementById("sframe1");
		var g1 = document.getElementById("grp1");

		function move() { //this function sets boundaries and spin direction
			if (s1x > 270) {
				xspeed = xspeed * -1
				if (yspeed > 0) {
					spin = -1;
				} else {
					spin = 1;
				}
			}
			if (s1x < 0) {
				xspeed = xspeed*-1;
				if (yspeed > 0) {
					spin = 1;
				} else {
					spin = -1;
				}
			}
			if (s1y > 220) {
				yspeed = yspeed * -1
				if (xspeed > 0) {
					spin = 1;
				} else {
					spin = -1;
				}
			}
			if (s1y < 0) {
				yspeed = yspeed * -1
				if (xspeed > 0) {
					spin = -1;
				} else {
					spin = 1;
				}
			}
			s1x = s1x + xspeed;
			s1y = s1y + yspeed;
			angle = angle + angspeed * spin;
			s1.setAttribute("x", s1x); //use to set horizontal of svg frame
			s1.setAttribute("y", s1y); //use to set vertical of svg frame
			g1.setAttribute("transform", "rotate(" + angle + " " + cx + " " + cy + ")");
			//use to rotate the <g> around a center that will move within the svg frame
		}

		function runner() { //this is the animation loop
			loop1 = setInterval(move, framerate);
		}
	</script>

	<br>
	<input type="button" value=" START " onmousedown="runner();">
</body>
</html>
```



### *• Animations via SMIL or Snap.svg*

While there are many things that can be done within the SVG specification itself, there may be simpler or more concise ways of doing it, depending on your needs. Two options are [SMIL](https://css-tricks.com/guide-svg-animations-smil/) (Synchronized Multimedia Integration Language) and JavaScript animation libraries like [snap.svg](http://snapsvg.io/). They are both beyond the scope of the course, but that does not mean they are difficult, we simply don't have time to explore every avenue. If you find yourself interested in additional animation projects, you should definitely take a look at these options.

### *• SVG Graphics Questions*

1. Make a vertical gauge that grows taller or shorter in response to a (+) button and a (-) button.

2. Make a rotating gauge that rotates clockwise or counterclockwise in response to right and left arrow buttons.

3. Write a program in which a ball continuously bounces inside a box once a start button is pressed, and stops when a stop button is pressed.

4. Expand your bouncing ball in a box program so that the user has a paddle that they can moved by pressing buttons (or keyboard keys) which can bounce the ball like a wall. If you are interested in keyboard keys, take a look at this example for moving a green ball down with the down arrow:

```html
<html>
<head>
  <title>Keypress Demo</title>
</head>

<body>
<script>
document.onkeydown = function(k) {
  if (k.keyCode == 40) {
    let d=document.getElementById("disc");
    let level=d.getAttribute("cy");
    level = Number(level) + 10;
    d.setAttribute("cy",level);
  }
}
</script>

<svg width="100" height="150">
  <circle id="disc" cx="50" cy="40" r="35" fill="green" />
</svg>
</body>
</html>
```

### *• Method Draw*

*Thanks to Ryan Kussman for this section.*

Need help creating custom SVGs? Well we have access to a free online program called **Method Draw**. Method Draw can create SVG code from custom drawings, and also export pictures as .png, it's basically a version of paint from your computer but 100x built for SVG's and other advanced drawings.

Open Method Draw by going to <http://editor.method.ac/>

![Method screen](https://lyndenmath.org/CSAssets/methodscreen.png "Method screen")

On the right hand column you can edit the width and height of your canvas. Measurements as you notice are measured in Pixels NOT inches, feet, yards etc. To draw simply use any of the tools you see on the left side (Lines, rectangles, text, shapes, eclipses and circles). To draw shapes or text with colors you can use the color pick tool on the bottom toolbar! Now for the part where you actually get to inserting into your HTML document.

Open up a Replit.com, and open your HTML document that you want your SVG drawing in. Go back to your browser that has your drawing open and click on **View → Source**. From this all you need to do is copy your source code that Method Draw spits out and throw it into your body on your HTML document. For now copy the following code into a blank HTML document.

```html
<svg width="580" height="400" xmlns="http://www.w3.org/2000/svg">

<!-- Created with Method Draw - http://github.com/duopixel/Method-Draw/ -->

<g>
  <title>background</title>
  <rect fill="#fff" id="canvas_background" height="402" width="582" y="-1" x="-1" />
  <g display="none" overflow="visible" y="0" x="0"
     height="100%" width="100%" id="canvasGrid">
    <rect fill="url(#gridpattern)" stroke-width="0" 
          y="0" x="0" height="100%" width="100%" />
  </g>
</g>

<g>
  <title>Layer 1</title>
  <rect id="svg_3" height="100" width="113" y="49.5" x="90.5"
        fill-opacity="null" stroke-opacity="null" stroke-width="1.5"
        stroke="#000" fill="#fff" />
  <rect stroke="#000" id="svg_4" height="93" width="113"
        y="52.5" x="396.5" fill-opacity="null" stroke-opacity="null"
        stroke-width="1.5" fill="#fff" />
  <ellipse ry="51" rx="225" id="svg_5" cy="323.5" cx="301.5"
        opacity="0.5" fill-opacity="null" stroke-opacity="null"
        stroke-width="1.5" stroke="#000" fill="#fff" />
  <ellipse rx="1" id="svg_6" cy="374.5" cx="525.5"
        fill-opacity="null" stroke-opacity="null" stroke-width="1.5"
        stroke="#000" fill="#fff" />
</g>
</svg>
```

Then save your HTML document and open and view it in your browser and you should see your SVG drawing on the web page. Now you should be able to draw almost anything that you would like on your web pages. Spend some time and look at the markup that it spit out at you, and see if you can edit what you got and improve it!

Now to remove stuff in the markup that wasn't needed such as website page weight, comments etc.

### *• SVG Paths*

A path can be used to describe the same figures as line, polyline, polygon circle and rect elements. The syntax is a little more complex than those elements, but is also more general. The significant attribute in the path element called 'd'. The 'd' attribute is assigned a string of text which describes the path to be created. The instructions are variations on move (without drawing), draw line, draw curve and draw arc. Each command is one letter followed by parameters. Whitespace is optional except between numeric parameters. First copy this simple example into a blank HTML document, then I'll explain how to write a string for the 'd' attribute.

```html
<svg viewBox = "0 0 1100 400" version = "1.1"> 
<path id = "s3" d = "M 60 0 L 120 0 L 180 60 L 180 120 L 120 180 L 60 180 L 0 120 L 0 60"
      fill = "green" stroke = "black" stroke-width = "3"/>
</svg>
```

### *• Moveto "M"*

The moveto command is given by the single letter 'M' or 'm'. The uppercase 'M' takes absolute coordinates (for the current coordinate system) and the lowercase takes relative coordinates. Relative in this case means relative to the position that the last command finished drawing (also called the "current point"). The uppercase/lowercase distinction also applies to all the other drawing commands for the path element.

The moveto command is given at the start of the path description. No line is drawn when 'M' is processed. It can also be given later on while drawing for discontinuous lines.

### *• Lineto "L"*

Straight lines are drawn with "L", the lineto command. A straight line from the current location can be drawn with the lowercase equivalent "l". "L" is followed by a point, as in "L 200 400". Horizontal and vertical lines can be drawn with "H" and "V" followed by an x or y coordinate.

```html
<svg viewBox = "0 0 1100 400" version = "1.1">
    
<!-- A triangle with absolute coordinates -->
<path d = "M 200 50 L 300 150 L 200 150 L 200 50" 
      stroke = "red"
	  stroke-width = "3" fill = "none"/>

<!-- A triangle with relative coordinates -->
<path d = "M 500 50 l 100 100 l -100 0 l 0 -100" 
      stroke = "green" stroke-width = "3" fill = "none"/>

<!-- Practical use of relative moves -->
<path d = "M 700 50 l 100 100 m 0 -100 l 100 100 m 0 -100 l 100 100" 
      stroke = "blue" stroke-width = "3"/>
</svg>
```

There are many more types of paths, feel free to search some up online at W3Schools.

<!----><a name="a3"></a>
## Appendix 3 - Additional Demos

### *• Connecting 2 Picos together*

In some applications it might be useful to directly wire two Picos together, for instance if you want to have one Pico trigger another Pico.  It appears that in order for this to be successful, the Pico's need to have a common Gnd.  Here's some sample code that works if Gnd of both Pico's are connected.

```javascript
//Make sure Gnds of both Pico's are connected and A5 of sender Pico is connected to A6 of reciever
//This is the code for the sender Pico

let volt = 0;

function blinker() {//toggles A5 between 1v and 0v
  if (volt==1) {
    digitalWrite(A5,0);
    digitalWrite(LED1, 0);
    volt = 0;
  } else {
    digitalWrite(A5, 1);
    digitalWrite(LED1, 1);
    volt = 1;
  }
}

function onInit() {
  setInterval(blinker, 500);
}

//This is the code for the reciever Pico

let state;
function checkv() { //watches A6 for state change of line from other Pico
  state = digitalRead(A6);
  if (state == 1) {
    digitalWrite(LED2, 1);
  } else {
    digitalWrite(LED2, 0);
  }
}

setInterval(checkv, 50); //interval needs to be faster than interval calling blinker
```



### *• 7-segment displays*

In addition to the info at Espruino.com, [this website is](http://www.whatimade.today/programming-an-8-digit-7-segment-display-the-easy-way-using-a-max7219/) useful.



### *• Phaser on Replit.com*

Phaser is a framework for making games that run in a browser.  It integrates nicely with Replit.com and a couple of nice tutorials are available.  The first tutorial is the one on the Phaser.io website, but a Replit.com user, Piotr Muskalski, has nicely set everything up for you [here](https://Replit.com/@pmuskals/Phaser-Tutorial-Example).  If you open up his Replit.com and then follow along with the step by step explanations at http://phaser.io/tutorials/making-your-first-phaser-3-game, you should have your first running, jumping platform game up and running in under an hour.  Another more sophisticated Phaser tutorial you may wish to try second is at https://Replit.com/talk/learn/Making-a-Phaser-Game-with-HTML5-and-JavaScript/7593.  The author, Kaldis Berzins, again provides step by step instructions.  It is a different sort of game than the other tutorial so you can learn new things. You'll still have a lot of questions, especially regarding how to make your own animated sprites and other graphics.  There are many sprite sheets available free online and a lot of information and free software that can help you create your own.



### *• IR Remote Emulating USB Keyboard via Pico*

```javascript
//Code demonstrating use of IR remote through Pico to emulate USB keyboard.
//Espruino documentation indicates a need to unplug the Pico from the computer
//to initiate USB mode, but this does not seem necessary.  Note that you will
//need to shift the focus from the WebIDE to a text editor to avoid the "Uncaught 
//ReferenceError" that comes up if you have the Pico type to the WebIDE console.

//Jeff Seely 2018.  Code based on that found at Espruino.com.  Simplified
//explanations of IR portions can be found in the textbook.

var kb = require("USBKeyboard");
var lastTime = 0;  //these variables need to be global since used in multiple functions.
var code = 0;
var timeout;    

function codeHandler() {
 timeout = undefined;
 if (code<1000000) {   //this eliminates responses to keys held down
   code =0;
   return; 
 }
 //console.log(code);  //can be uncommented if you want to see the code
 digitalPulse(LED2,1,20); //indicates a valid IR signal has been received by the Pico
 switch (code) {          //These codes will work for the "Car" remote used in class.  Other remotes - other codes.
   case 16724175:
     kb.type("1\n");   //note carriage return \n
     break;
   case 16718055:
     kb.type("2\n");
     break;
   case 16743045:
     kb.type("3\n");
     break;
   case 16716015:
     kb.type("4\n");
     break;
   case 16726215:
     kb.type("5\n");
     break;
   case 16734885:
     kb.type("6\n");
     break;
   case 16728765:
     kb.type("7\n");
     break;
   case 16730805:
     kb.type("8\n");
     break;
   case 16732845:
     kb.type("9\n");
     break;
   default:
     kb.type("USE 1-9 ONLY\n");   //letters must be in caps but will send in smalls
 }
 code = 0;
}

function pulseOn(e) {
 code = (code*2) | ((e.time - lastTime) > 0.001);
 if (timeout!==undefined) clearTimeout(timeout);
 timeout = setTimeout(codeHandler, 20);
}

function pulseOff(e) {
 lastTime = e.time;
}

setWatch(pulseOn, A5, {repeat:true, edge:"falling"}); //IR sensor signal line must be pinned to A5 for this code
setWatch(pulseOff, A5, {repeat:true, edge:"rising"});
```





### *• LED PushButton Demo*

This code demonstrates how to sync up the the LED and functionality of a lighted pushbutton momentary switch such as [Adafruit 1493](https://www.adafruit.com/product/1439).  Note that these switches can be purchased in both momentary and latching forms.

```javascript
//Code to demo LED switch.
//The switch uses 2 gpio pins, one for led, one for switch
//Wire power as Pico_GND to 1K_Ohm_Res to (-) LED
//(+) LED to PPIN
//Wire one switch lead to GND and the other to S_PIN

PPIN = "A5";  //GLOBAL for Power pin (+)
S_PIN = "A6"; //GLOBAL for Switch pin
ON = false; //true when led is on
INT1 = 0; //GLOBAL reference to pulse interval timer
BUSY = false; //true when switch is busy

digitalWrite(PPIN, 0); //initialize LED off
pinMode(S_PIN,"input_pullup");

function ledOff() {
  digitalWrite(PPIN,0);
}

function ledOn() {
  digitalWrite(PPIN,1);
}

function ledPulse() {
  ledOn();
  ON = true;
  INT1 = setInterval(function() {
    if (!ON) {
      ledOn();
      ON = true;
    }
    else {
      ledOff();
      ON = false;
    }
  }, 500);
}

function onPress() {
  if (!BUSY) {
    BUSY = true;
    console.log("contact");
    //THIS IS WHERE SWITCH FUNCTION CODE GOES
    ledPulse();
    setTimeout(function () {
      clearInterval(INT1);
      ledOff();
      BUSY = false;
    }, 3490);
  }
}

setWatch(onPress, S_PIN, {repeat: true, edge: "falling", debounce:50});
```



### *• USB Gamepad*

Sample code that works with cheap USB gamepads:

```html
<!DOCTYPE html>
<!-- This is demo code for gamepad interaction for a single gamepad-->
<!-- It is based mostly on https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API/Using_the_Gamepad_API -->
<!-- Successfully tested on Chrome 65.0.3325 Mac OS, USB Gamepad (Vendor: 0079 Product: 0011) -->

<html lang="en-us">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>GamePad Demo</title>
</head>

<body>
	<p id="gamepad-info">This will be replaced by gamepad info when a gamepad is attached.</p>
	<p id="bstatus">button status</p>
	<p id="axstatus0">axis 0 status</p>
	<p id="axstatus1">axes 1 status</p>
	
<svg style="width:100%; height:600px">
	<circle id="ball" cx="50" cy="50" r="20" stroke="green" stroke-width="4" fill="hsl(180,100%,50%)" />
</svg>

</body>

<script>
var gamepadInfo = document.getElementById("gamepad-info");
var bstatus = document.getElementById("bstatus");
var axstatus0 = document.getElementById("axstatus0");
var axstatus1 = document.getElementById("axstatus1");
var b = document.getElementById("ball");
var interval;
var x = 50;
var y = 50;
var sp = 5; //this is the movement speed in px.
var cr = 20; //radius of the svg ball
var ps = 40; //this is the gamepad polling speed in ms.
var hue = 180; //using hsl system to control the color of the svg fill
var sw = 4; //stroke width.

//the gamepadconnected event is sent to the focussed page when a gamepad is connected or if a button is pushed.
//there is also a gamepaddisconnected event that can be listened for.
//the navigator.getGamepads() function returns an array of all the connected gamepads and their button states, etc.
//for this demo we will assume only 1 gamepad, ie gamepad[0].
//if more than one gamepad is used, you need to read background info because it can get weird.

window.addEventListener("gamepadconnected", function(e) {
  var gps = navigator.getGamepads()[e.gamepad.index];
  gamepadInfo.innerHTML = "Gamepad connected at index " + gps.index + ": " + gps.id + ". It has " + gps.buttons.length + " buttons and " + gps.axes.length + " axes.";
  interval = setInterval(gameloop, ps); //this polls the gamepad status every ps ms.
});

window.addEventListener("gamepaddisconnected", function(e) {
  gamepadInfo.innerHTML = "Waiting for gamepad.";
  clearInterval(interval);
});

function gameloop() {
	var gp = navigator.getGamepads()[0]; //poll the gamepad
	
	  //button control
	  if (gp.buttons[0].pressed==true) {
    	bstatus.innerHTML = "b0 pressed";
    	y=y-sp;
    	b.setAttribute("cy",y);
	  } else if (gp.buttons[1].pressed==true) {
    	bstatus.innerHTML = "b1 pressed";
    	x=x+sp;
    	b.setAttribute("cx",x);
      } else if (gp.buttons[2].pressed==true) {
    	bstatus.innerHTML = "b2 pressed";
    	y=y+sp;
    	b.setAttribute("cy",y);
      } else if (gp.buttons[3].pressed==true) {
    	bstatus.innerHTML = "b3 pressed";
    	x=x-sp;
    	b.setAttribute("cx",x);
      } else if (gp.buttons[4].pressed==true) {
    	bstatus.innerHTML = "b4 pressed";
    	cr=cr-sp;
    	if (cr<=1) cr = 1; //to keep it from disappearing or going negative.
    	b.setAttribute("r",cr);
      } else if (gp.buttons[5].pressed==true) {
    	bstatus.innerHTML = "b5 pressed";
    	cr=cr+sp;
    	b.setAttribute("r",cr);
      } else if (gp.buttons[6].pressed==true) {
    	bstatus.innerHTML = "b6 pressed";
      } else if (gp.buttons[7].pressed==true) {
    	bstatus.innerHTML = "b7 pressed";
      } else if (gp.buttons[8].pressed==true) {
    	bstatus.innerHTML = "b8 pressed";
      } else if (gp.buttons[9].pressed==true) {
    	bstatus.innerHTML = "b9 pressed";
      } 
      
      //axes control
      if (Math.abs(gp.axes[0])>.1) {
      	axstatus0.innerHTML = "axis0 value " + gp.axes[0];
      	hue = hue + 4*gp.axes[0];
      	b.setAttribute("fill", "hsl("+hue+",100%,50%)");
      } else {
      	axstatus0.innerHTML = "axis0 value " + 0;
      }
      if (Math.abs(gp.axes[1])>.1) {
      	axstatus1.innerHTML = "axis1 value " + gp.axes[1];
      	sw = sw + gp.axes[1];
      	if (sw<=2) sw = 2;
      	b.setAttribute("stroke-width", sw);
      } else {
      	axstatus1.innerHTML = "axis1 value " + 0;
      }
}
</script>

</html>
```

<!----><a name="a4"></a>
## Appendix 4 - Apps with DroidScript

This was originally a chapter in the book but has been moved to the appendix although it still retains the book format.

### 4.1 DROIDSCRIPT BASICS

>**Target**: Be familiar with the DroidScript environment including layouts enough to be able to make and modify a simple hello app.

#### *• What's an App?*

So far we've written a lot of programs. You've been able to share code, you've been able to serve webpages on the internet, but you haven't been able to send someone else a self contained copy of a program to run that didn't require some other software to run it, like a browser or Brackets. These self-contained programs that can be shared or sold are called **applications**, or apps for short. They may only run on a Mac or PC or Android device, but if you have the required hardware and OS (**operating system**) you can expect to be able to run any program designed for that system without any additional helper programs. 

In this unit, we will use JavaScript to write programs for Android devices. We can then package those programs as apps which could be shared with Android users, or even sold on Google Play. The software environment in which we will do our work is called DroidScript. It is free (except the app packager which is \$7.00), it includes a WiFi IDE that runs as a Chrome extension, just like the Espruino Web IDE. Also as with Espruino, there are a lot of non-standard JavaScript functions/methods available to let you access the various sensors and capacities of the Android device as well as to control the screen, camera, sound output and other features. The documentation of DroidScript is unfortunately not as complete as Espruino but there are many code examples that can be used to see how the various objects and methods work.

At this point you need an Android device with DroidScript installed. The code examples in the book are assuming a 7" screen and have been tested on a Kindle Fire. It is very likely that they will work on Android phones or tablets with different screen sizes, but you may need to modify some dimensions. You also need a Mac or PC with DroidScript installed. Since it is a Chrome extension, it should work the same on either platform. The Mac/PC install is not really required since you can do everything on the Android device itself, but having a full keyboard and more screen space make writing software much less frustrating.

#### *• Hello App*

The following section is adapted from the tutorial at DroidScript.org, including the images. You can find the original [here](http://droidscript.org/tutorials/my-first-app-part-1/):

Start DroidScript on your Android device and make sure that you are connected to the local WiFi.

Press the WiFi Connect button on the DroidScript toolbar. See Figure 4.1.

This does not connect you to the local WiFi, rather it provides you with the IP of the Android device in a popup so that you can connect to the Android device from your PC via the WiFi. Unlike the Pico, we do not need a USB tether to communicate, we can make use of the WiFi. Note the :8088 at the end of the IP number. This is the port number. 
<img src="https://lyndenmath.org/CSAssets/wifi_connect_button.jpg" alt="DroidScript Connect button" width="100%">

*Figure 4.1 WiFi Connect button*

Now start the WiFi IDE on your PC and enter IP+port number. Alternatively you should be able to just type the IP+port number into the address bar of a browser to get the same thing.

![Figure 4.2 DroidScript Menus](https://lyndenmath.org/CSAssets/DroidScriptMenus.jpg "DroidScript Menus")

*Figure 4.2 DroidScript Menus*

Now we can make a new App. On your PC, make sure you are in Apps View and not Edit or Assets, Figure 4.2. Click the New App icon, not the New HTML App, Figure 4.3.

![Figure 4.3 New App](https://lyndenmath.org/CSAssets/wifi_ide_new_app_icons.jpg "New App")

*Figure 4.3 New App icon*

Enter the name **MyHello** and click **OK**. You should see it appear on your Android device with its green robot icon as well as on your PC.

When you create a new App, DroidScript automatically enters some boilerplate to get you started. This boilerplate contains a functional "Hello World" program. Click the **Run** button above the program on the PC and it should run on the Android device. You can stop the program by clicking the **Stop** button in the Editor. This is the typical programming cycle we will use: Edit the code on the PC then run/test it on the Android device.

Now let's take a look at the code. I've left out the comments to save space.

```javascript
function OnStart() {
 lay = app.CreateLayout( "linear", "VCenter,FillXY" );
 txt = app.CreateText( "Hello" );
 txt.SetTextSize( 32 );
 lay.AddChild( txt );
 app.AddLayout( lay );
}
```

The `OnStart() `function is similar to `onInit()` in Espruino. When the **MyHello** app icon is clicked on the Android device, this is the function that is run.

The second line makes use of the app object. Pretty much everything in DroidScript is connected to the app object. When you created the **MyHello** app, you also created its app object. The app object has methods to create all the things you need for your application.

In this case, we use the `app.CreateLayout()` method to create a new *layout* object called lay. You can call it anything you want, but if you include lay in the name, it makes it easier to remember what it is.

A layout object is used to arrange the visual elements on the screen such as text, buttons and images. These are all referred to in DroidScript as *controls*. To see a list of all the possible controls click the **Docs** tab and then the **Controls** tab. Similar to the different button types in HTML, these are built in features that you just call.

There are 3 types of layouts: *Linear*, *Frame* and *Absolute*. Each type has options to indicate how the layout fills the screen and whether it is vertical or horizontal. The syntax is

`lay = app.CreateLayout( type, options );`

The third line creates a text control which displays the words "Hello". Try replacing the words with something else and running the app again.

The fourth line adjusts the text size using a text method. There are lots of text methods. Go to **Docs → Controls → Text** for examples.

The fifth line may be a bit mysterious. What's going on is we are using a layout method to add the text control to the layout. Up to this point we had only defined what the text would be, we hadn't said that it would show up on the layout. By using the `AddChild()` method of our layout, we make the text control part of the layout. You may recall the parent-child-sibling DOM metaphor from Chapter 4; this is the same thing. The child inherits certain things from the parent. For instance, if the parent layout is vertical, the text will be vertical; if it is horizontal, the text will be horizontal.

Finally, we use the `app.AddLayout()` method to make it appear on the Android screen. It is easy to forget this step, but without it, we've only defined the object. It is a separate matter to display it.

At this point you should explore different layouts, add additional text controls and other kinds of controls. You don't need to worry about programming buttons to do anything, you are just exploring how to create them at this point. You will need to refer to the **Docs**. You can also get additional information from the Tutorials, Forum and Wiki linked at **Home → Getting Started**.

#### *• 4.1 Questions*

1.Since DroidScript is not yet well documented, where are the 3 best sources of information? Give their URL's.
2.How is an app different from a webpage?

### 4.2 STOPWATCH

>**Target**: Practice setting up button and text controls on a layout and connect button presses to JavaScript functions.

#### *• More about Layouts*

The project in this section will be to make a simple stopwatch. The purpose however is to learn about layouts and touch input via buttons. Even in other languages and on other development platforms, if you develop mobile apps for Android or iOS devices, you will likely encounter layouts or things similar to them as well as touch buttons.
These are basics.

**Part 1**: Start by pasting the following code in your DroidScript editor and running it.

```javascript
function OnStart() {
 app.SetOrientation("Portrait");
 app.PreventScreenLock(true);
 layVMain = app.CreateLayout("Linear", "Vertical");
 topText = app.CreateText("Stopwatch", 1, 0.07);
 topText.SetMargins(0, 0.03);
 topText.SetTextSize(20);
 layVMain.AddChild(topText);
 app.AddLayout( layVMain );
}
```

As before, we create an `OnStart()` function. We then set the screen orientation to Portrait. If we don't do this, most Android devices will detect the orientation that the screen is being held and try to match it. Comment out the orientation line and run it again to see how your device behaves.

Next we keep the screen from going into sleep mode while our app is running. This is optional, but if we are making a stopwatch, we probably don't want it going to sleep during a race.

Next we create a layout called `layVMain` using the `CreateLayout()` method. This layout is going to stack consecutive control items vertically, rather than in horizontal rows, as per the optional parameter. In nearly every case, we will also use Linear as the first parameter. You can look up what the other choices are and what they do under **Docs → Layouts**.

Next we create a text object called `topText` which contains the word "Stopwatch" in a box that is 90% of the width of the screen and 7% of the height. In the DroidScript and mobile app environment, dimensions are often given in percentages of screen width so that they are more likely to scale properly on different screen sizes and in different orientations.

Next we make some margins around our box, 0% to the left and 3% on top. We could specify right and bottom margins as well, but if we leave them out they default to 0%. This moves our text box down the screen a bit. Note that so far we have only changed the size and position of the text box, we do not do anything with the size of the text itself until we use the `SetTextSize()` method. It is important at this point that you try changing the various values and see what happens to the text position and size.

**Part 2**: We need a Start button, a Stop button and someplace to show the time. You can probably figure out how to make your own buttons now from the DroidScript documentation, but for a start button, you might try something like the following. Make sure you place it before the `app.AddLayout()` line.

```javascript
startBtn = app.CreateButton("START", 0.9, 0.16, "Custom");
startBtn.SetMargins(0, 0, 0, 0.015);
startBtn.SetStyle("green", "#006400", 10);
startBtn.SetTextSize(54);
layVMain.AddChild(startBtn);
```

Just like with webpages, you can spend a lot of time playing with colors and other formatting. The `SetStyle()` method is not well documented. The parameters are color1, color2, radius, strokeClr, strokeWidth, shadow, where color1 and color2 are *gradient* shades that go from top to bottom and radius sets the curvature of the button corners. Feel free to play around with those along with all of the other options described in **Docs → Controls → Buttons**.

**Part 3**: At this point our button doesn't do anything. To activate it, we can add the `startBtn.SetOnTouch()` method and specify a function to run as its parameter. By adding in this method, whenever a user touches the Start button, the function we specified will be called. In our case, we would like it to start a clock. I will name the clock starting function `startBtn_OnTouch()` but you can call it whatever you want.

```javascript
function startBtn_OnTouch() {
  var tStart = new Date();
  startTime = tStart.getTime();
}
```

This function gets the time at the point the button is pressed. In the DroidScript environment we need to create a new Date object before we can use the `getTime()` method. This is standard JavaScript. One problem we have in the DroidScript environment is that there is no console. We don't have a simple way to see what our program is doing. Instead, we can send values to a text object on the screen. Add a text object called consoleText into the layout and set its contents to "time". Then when it is working add the line `consoleText.SetText(startTime);` at the end of the `startBtn\_OnTouch()` function. When you run it and press the Start button you should get the number of milliseconds since 1970 as in Chapter 3. If you repeatedly press Start, you should see the number change about 1000 for each second that has gone by since your last press. Note that since we are using a vertical layout, the order of our `AddChild()` statements determines the order that the controls appear on our screen, from top to bottom. Try putting the controls in a different arrangement on the screen by changing the order of the `AddChild()` statements.

**Part 4**: For a typical stopwatch we would expect to have a Stop button. Create a Stop button below the Start button and have it trigger a function that calculates and displays the elapsed time in consoleText. Note that in the example code, `startTime` is a global variable since it was not declared using var. It would be better to declare it with var at the top of the program, which would keep it global, but make it more obvious. Recall how you calculated elapsed time in your Reaction Timer project in Chapter 3. If you are successful, your stopwatch should display the number of milliseconds between pressing start and stop.

**Part 5**: But what if we want to display seconds, minutes, etc. This requires a bit of arithmetic since minutes and seconds are in base 60. For instance, 2.5 minutes is 2.5 x 60 seconds = 150 seconds. Going the other direction we can do 150 seconds /60 = 2.5 minutes. But what if we want to display 2 minutes and 30 seconds? We would need to do 150/60 = 2.5, then 2.5 -- `Math.floor(2.5) = 0.5`, then 0.5 x 60 = 30 seconds. Using this algorithm we can go from seconds to minutes and seconds. Here's a function that uses the above algorithm to convert milliseconds to minutes and seconds out to 2 decimal places (hundredths of a second). See if you can follow how it works. You may need to recall that % is the remainder operator that gives you the remainder of the indicated division. Notice that the final values are a text string, not numbers. This is typical when working with time since time notation (0:00.00) contains characters and placeholders that are not used in arithmetic.

```javascript
function msecToTime(msecs) {
  var zero = "";
  var secs = Math.round(msecs / 10) / 100;
  var mins = Math.floor(secs / 60);
  var tsecs = Math.floor(secs) % 60 + (secs -- Math.floor(secs));
  if (tsecs < 10) zero = String(0);
  var tString = mins + ":" + zero + tsecs.toFixed(2);
  return tString;
}
```

On nice feature of this function is that it accepts the milliseconds as a parameter, returns a string as the time and uses only internally declared local variables. This makes it portable and you could use it in any program requiring a time display of this nature. If you think you might reuse some code, it is very helpful to encapsulate it in a function of this sort. The only part of the code that might be unfamiliar is the number method `toFixed(2)`. It is standard JavaScript and it returns a string matching the value of its number object to 2 decimal places. You can change the parameter of any number of decimal places you wish. In this case, 2 is the most appropriate because it is typical for a stopwatch to report time to the hundredth of a second. 

**Part 6**: Now we have the pieces for a simple stopwatch. Your implementation probably has some bugs/features like if you press Start, then Stop, Stop, Stop, Stop you see that your stopwatch isn't really stopping since the elapsed time continues to get bigger in the display. This can be fixed easy enough but don't do it yet. What you might miss from a traditional stopwatch is a readout of the running time. All we see is the end time. If you think about it though, we could display the running time by just pressing Stop, Stop, Stop every 100^th^ of a second. This is not convenient, but a setInterval() timer could do it just fine. To finish your simple stopwatch, use a setInterval() timer to make your stopwatch display the running time in minutes and seconds out to hundredths, and make your Stop button really stop the stopwatch.

**Part 7**: There are many features that you could add to your stopwatch: You could improve the layout and display format, you could add lap features, you could add a beep for the Start and/or Stop buttons, etc. You can play with a traditional stopwatch to get some ideas. Add some feature(s) to your stopwatch and be sure to thoroughly test it. Does it behave as it should in every situation? Let other people test it out to see if they can find bugs.

#### *• 4.2 Questions*

1.Complete parts 1 - 7 of the stopwatch project.
2.Report some UI feedback that you received on your stopwatch and how you revised your stopwatch based on that feedback.
3.Redesign your stopwatch in a landscape layout with stop and start being left and right thumb buttons and the elapsed time showing large in the middle.

### 4.3 TILT & SCROLL GAME

>**Target**: Code a simple scrolling game app with sprites and user input.

#### *• Images*

In this section we will make a simple scrolling game. The purpose is to learn about graphics and sensors in the Android/DroidScript environment. Much of the code is adapted from examples in the DroidScript app.

*Rocket*<img src="https://lyndenmath.org/CSAssets/rocket.png"  hover="rocket.png" alt="rocket.png">

**Part 1**: If we are going to make a game, we often need to deal with images. DroidScript allows us to import images into our projects by just dragging them into **Assets → Images**. The images can be .jpg or .png and perhaps other formats as well. Get the rocket.png image from your instructor or just copy the image above and add it to your assets. You can swap it with something else you prefer later. Then paste and run the following code:

```javascript
function OnStart() {
  app.SetOrientation( "Portrait");
  lay = app.CreateLayout( "linear", "FillXY" );
  imgRocket = app.CreateImage("Img/rocket.png");
  lay.AddChild (imgRocket);
  app.AddLayout( lay );
}
```

As before, we create an `OnStart()` function. We use the `SetOrientation()` method to lock the screen into the Portrait orientation when our app is running. We then create a layout named lay and an image control named imgRocket to put on that layout. Understand that the image control (imgRocket) is not the same thing as the image file rocket.png. We need to link the two using the `CreateImage()` method. Notice that the location of images in the assets tab are in the Img directory which must be included in the pathname. Also note that on some Android devices you may need to use /Sys/Img in the pathname instead of just Img. If you want to change the size of the image that is displayed, you can also do it using the options in the `CreateImage()` method, look them up.

We then add the image to the layout using the `AddChild()` method and then display the layout in the app with `app.AddLayout()`. Our rocket doesn't do anything, but at least we know how to get images on the screen.

**Part 2**: At this point any images we would add would be just be stacked by our layout vertically on the screen along with any other controls we might add which is not very useful for a game. Instead we would like to be able to have images anywhere on the screen and to reposition them using animation techniques. One way to accomplish this in the DroidScript environment is to attach the images to another image. This strategy gives us access to the `DrawImage()` method by which we can put secondary images at any location on the primary image.

Paste the following code above where you created imgRocket:

```javascript
gframe = app.CreateImage( null, 1.0, 1.0, "fix", 480, 800 );
lay.AddChild( gframe );
```

Here we create a primary image called `gframe` on which to place and move our other images. It turns out that you don't actually have to specify an image and if we just use null in the filename position, we can still move other images around on top of it. The 1.0's say that the image will fill screen 100% in both width and height. Fixed means that we are going to specify the number of pixels so there won't be scaling, and we do that at 480 by 800 pixels. The purpose of these settings is to improve the drawing performance of the Android device. We want our game images to move as smoothly as possible. Finally add

`gframe.DrawImage(imgRocket, 0.4, 0.7, 0.2, 0.2);`

at the end of your `OnStart() `function. This draws our rocket at a position 40% from the left and 70% from the top at a scale of 20% wide and 20% high. You should definitely play with those numbers to see their effect. Note that you no longer need `lay.AddChild(imgRocket);` since you are directly drawing the rocket onto gframe rather than adding it to lay. Since `gframe` is a Child of `lay`, anything that is drawn on `gframe` is also.

There is one additional way that we can improve the performance of the Android display. Instead of letting the device update its display whenever it it normally would, we can control the display updating process and have it redraw the screen when we want it to. To do this add

`gframe.SetAutoUpdate(false);`

right before the `AddChild(gframe);` Then at the very bottom of your `OnStart()` function, add `gframe.Update()`. With auto updating turned off, we will need to manually call the updating method.

At this point, you could use create a `setInterval()` timer that would continually redraw the rocket in different locations in order to make the rocket move. This is a standard animation technique that you are already familiar with, but we would actually like the rocket to respond to user input to move and we will use one of the sensors to accomplish that.

#### *• Sensors*

**Part 3**: One of the cool features of developing in DroidScript is that all you gain access to whatever sensors the Android device has. These vary with the device but most have light sensors and accelerometers. An **accelerometer** can detect motion or change in position. We will use this for user input on our game. We **instantiate** an accelerometer sensor as follows:

```javascript
sns1 = app.CreateSensor( "Accelerometer", "Medium" );
sns1.SetOnChange( sns1_OnChange );
sns1.SetMinChange( 0 );
sns1.Start();
```

The first line instantiates an Accelerometer sensor named sns1 and sets its checking rate to Medium speed. Slow is the default and Fast is the other option. The second line says that if the accelerometer detects a movement the function `sns1_OnChange()` should be called and it will pass its data as parameters to that function. The third line is optional, but it sets the amount of change required to trigger the accelerometer to the minimum of 0. The parameter can range from 0 to 1. The fourth line tells the sensor to start sensing. Add these lines to your `OnStart()` `function.

Next create a function called `sns1_OnChange(x, y, z, time)`. The parameters that it will receive indicate motion in the x, y and z directions and also report the time (ms) since the sensor was started. We would like to be able to see these numbers, but again we have no console. One simple solution is to add `gframe.DrawText(x, 0.5,0.5);` inside `sns1_OnChange()`. This almost works, but we need the following:

```javascript
function sns1_OnChange(x,y,z,time) {
  gframe.Clear();
  gframe.DrawText(x,0.5,0.5);
  gframe.Update();
}
```

We needed to move the `Update()` method down into our change handler so that our display would update every time the sensor detected movement. We also needed to `Clear()` our display before every update, otherwise it just writes on top of what is already there and we can read it. This "clear then update" sequence is very common in animation and generally keeps drawn items on the screen a larger percentage of the time than doing a "draw then clear" order. Run it and see what sort of values you get. Replace x with y, z and time. How hard is it to keep the numbers from changing? Where did the rocket go? It gets cleared the first time you call `gframe.Clear()` and doesn't get redrawn. Put it next to `gframe.DrawText()` instead so that it is part of the update.

#### *• Sprite Animation*

**Part 4**: Now we would like the rocket to move based on how the user tilts their device. To keep it simple, we will just use the `x` value and move the rocket horizontally. If we try to do all our animation within `sns1_OnChange()`, any motion in our game will be based on whether or not the sensor detects motion from the user. That would be OK for rocket motion, but what if we want to add asteroids? The asteroids would stop if the user didn't move. It would be better if we had a `setInterval()` timer that controlled all the motion and which checked at each loop to see what the sensor state was. If we run the interval timer fast enough, the user's motion will be reproduced well in our game.

So create a function called `DrawFrame()` and move everything from `sns1_OnChange()` into it. Add to `OnStart()` an interval timer to call `DrawFrame()` every 20 ms. Unfortunately, `DrawFrame()` doesn't know what `x` is; it needs to be a global variable. Create a global at the top of your program with `var` and call it `xtilt`. Let `xtilt = x` in `sns1_OnChange(x)` and then `gframe.DrawText(xtilt,0.5,0.5)` inside of `DrawFrame()`. In this way, we can get our functions to work together. `DrawFrame()` runs every 20 ms and uses whatever value `x` happens to be at the time.

Unfortunately the values of `x` we are getting are -10 < x < 10 and those are not the sort of values we need to draw our rocket. The `DrawImage()` values are screen width percentages ranging from 0 to 1. Figure out a mathematical process to get `xtilt` to range from 0 to 1. Once that is complete put `xtilt` into `DrawImage()` in place of the 0.4, which is the `x` position.

This is a good start, we can move our rocket around by tilting, but it's very jerky. We get some improvement by commenting out `DrawText()`, but not much. Here's another strategy:

```javascript
function sns1_OnChange(x,y,z,time) {
  xtilt = x/100;
}

function DrawFrame() {
  gframe.Clear();
  xdraw += xtilt;
  gframe.DrawImage(imgRocket, xdraw, 0.7, 0.2, 0.2);
  gframe.DrawText(xtilt,0.5,0.5);
  gframe.Update();
}
```

You will need to declare a global `var xdraw = 0.5;` at the top of your program to start the rocket in the middle of the screen. Since the accelerometer values range from -10 to +10, if we divide by 100, we get very small values which move the rocket right if they are positive and left if they are negative. Because the values are small, they cause a small change in the position of the rocket which makes for smooth motion. The problem is the rocket can slide off the screen. Write a couple of if statements to keep the rocket on the screen.

**Part 5**: To make it seem more like our rocket is in space, it would be nice to have some stars flowing by. A continually moving background image is the main feature of *scrolling* games. A common way to achieve this on digital devices is to have one image showing and a copy of the image off screen. Then as the showing image scrolls off screen, the second image follows it onto the screen. Eventually the first image is all the way off and the second image is all the way on. The roles are reversed and the process continues indefinitely. By carefully selecting or modifying a background image, it isn't apparent to the user where one image stops and the other starts. 

Get the StarField.jpg image from your instructor and add it to your assets. Then use `app.CreateImage()` to link it to an image named `imgBackground`. As with `imgRocket`, there's no need to add it to lay, we'll add it to `gframe` instead, inside `DrawFrame()`. The following code will set up the pair of images and scroll them slightly each time `DrawFrame()` is called. Make sure you can follow how the process works. You will also need to declare two globals at the top of your program. Start with `backGroundY=0;` and `backGroundShift=0.005;` You can play with the shift number to speed up or slow down the scroll. 

```javascript
gframe.DrawImage( imgBackground, 0, -1.0 + backGroundY, 1.0, 1.0 );
gframe.DrawImage( imgBackground, 0, backGroundY, 1.0, 1.0 );
backGroundY += backGroundShift;
if( backGroundY >= 1.0 ) backGroundY -= 1.0;
```

If you lose your rocket image, you may have it attached to `gframe` above the background image. You need to have the rocket second in order if it is going to be in a later (more foreground) layer.

*Piggy Asteroid*<img src="https://lyndenmath.org/CSAssets/piggy1.png" width="20%" hover="piggy1.png" alt="piggy1.png">

**Part 6**: What is a rocket in space without asteroids to hit or avoid? We want the position of the asteroids to be controlled by the game and somewhat random in their position. We will have them start at a random x position at the top of the screen and move down the screen toward the rocket. For fun we will use a pig image as our asteroid. Get piggy1.png from your instructor or just copy it from above. Write the code. Use imgPig as the name of the image object connected to piggy1.png. Don't worry about stopping the game or destroying the rocket and/or asteroid on hits. Just get an asteroid to go from top to bottom, then when it gets to the bottom, have it start over but from a different random `x` location.

When that code works, we can add rotation to the asteroid. Rotation can be accomplished by continually changing the image that we use for the asteroid. Get piggy2.png through piggy5.png. If you look at the images, you will see that each one is like a still picture of the pig in rotation. If we play them quickly in succession, the pig appears to rotate. The easiest way to handle items in succession is with an array. Use the following array assignments to connect each piggy image to a successive array element. You need the array to be global so declare it at the top of your program as 

```javascript
var imgPig=[];
imgPig[1] = app.CreateImage("Img/piggy1.png");
imgPig[2] = app.CreateImage("Img/piggy2.png");
imgPig[3] = app.CreateImage("Img/piggy3.png");
imgPig[4] = app.CreateImage("Img/piggy4.png");
imgPig[5] = app.CreateImage("Img/piggy5.png");
imgPig[6] = app.CreateImage("Img/piggy6.png");
```

Now, instead of `gframe.DrawImage(imgPig, etc)` you can write `gframe.DrawImage(imgPig[pignum]`, etc. where pignum is a global variable that increments each time `DrawFrame()` is called. Write the necessary code. This will make the asteroid rotate as it moves down the screen. But it is probably rotating too fast. To slow it down, we would like to not rotate `imgPig[]` every time `DrawFrame()` is called, but rather every two or three times. There are various ways to do this, here's one option that you could put inside `DrawFrame():`

```javascript
rota += 0.5;
if (rota > 6) rota = 1;
pignum = Math.floor(rota);
```

Note that rota needs to be a global declared at the top of the program. Can you see which number changes the speed of the rotation? Try making it bigger or smaller. Were you correct? Set the rotation speed to your taste.

The techniques we have been using to animate the rockets and asteroids is called **sprite** animation, because in computer science, a sprite is a 2 dimensional bitmap image that is integrated into a larger scene. Originally the term came from "spiritus", Latin for spirit, in the sense of a fairy or elf.

The next step in learning about sprite animation would be to use [sprite sheets](https://www.codeandweb.com/what-is-a-sprite-sheet). DroidScript also offers some built in methods that make it fairly easy to use sprite sheets, but we don't have time to do everything. If you are interested in animation and want to help with an appendix on sprite sheet animation, let your instructor know. You can take a look at **Samples → GLView SpriteSheet** to give you an idea of what it is about and also [here](http://gamedevelopment.tutsplus.com/tutorials/an-introduction-to-spritesheet-animation--gamedev-13099) to give you some background and examples of how you could do the same sort of thing with JavaScript on a webpage.

#### *• Sound*

**Part 7**: Finally, lets make an explosion sound play if we hit an asteroid. We first need to know if we've hit the asteroid, that is, if the location of the rocket is the same as the location of the asteroid. Below is an example of a function that you could use. Feel free to write your own. Since this function accepts parameters and just return true or false it is portable.

```javascript
function IsCollision( x1,y1,w1,h1, x2,y2,w2,h2, d ) {
  if( x2 < x1+w1-d && x2+w2 > x1+d && y2+h2 > y1+d && y2 < y1+h1-d )
    return true;
  else
    return false;
}
```

Hopefully you can work through the code and see how it works. It's tedious because of all the comparisons, but once it is written and working you can just call it. You might wonder about the purpose of the d parameter. In this case, d determines how much overlap the objects need to have before `IsCollision()` will return true. You may want to play with the value of d that you pass to `IsCollision` to give your game the sensitivity you want. To use `IsCollision()`, you might want to put something like the following into your `DrawFrame()` function. You will need to adjust the names of the variable that you are passing to `IsCollision()` to match the code that you have written.

```javascript
hit = IsCollision( x1,y1,w1,h1, x2,y2,w2,h2, 0.09 );
if (hit) {
//play a crash sound
}
```

Now we need to play a sound when hit is true. The easiest way to do this is to `app.Create` a Media Player object. Look in **Docs → Components → MediaPlayer** to see example code. You'll also need an .mp3 sound file to play. You can find your own on the internet or get a sample from your instructor. Put the sound file in your **Assets → Sounds** folder and use the same sort of pathname that you have been using for images, just replacing Img with Snd. If you follow the example, you should be able to get it to play whenever hit is true.

DroidScript has additional controls that are not listed in the app or the WiFi IDE. To find them you need to review the documentation on the [DroidScript ](http://wiki.droidscript.me.uk/doku.php)[Wiki](http://wiki.droidscript.me.uk/doku.php). One of those controls is an audio synthesizer that we could also use to create all sorts of sounds for our game. Unfortunately it is not well documented. If you are interested in digital sound production and want to help work on documenting the synth object for an appendix to this textbook, let your instructor know. You can get get an idea of what is possible with the synth object by looking at **Samples → Audio Signal** and **Samples → Audio Synth** in the DroidScript app. For a list of the available synth methods, go [here](http://wiki.droidscript.me.uk/doku.php?id=built_in:synth). These methods are what need to be documented. We need a description of what they do and what their parameters are. 

**Part 8**: There are many other enhancements you could add to this simple game: scoring, restarts, messages to players, more asteroids, asteroids at random speed, levels of difficulty, etc. Develop your own enhancement to the game and test it with users.

#### *• 4.3 Questions*

1. Develop your own scrolling game.
