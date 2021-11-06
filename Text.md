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

###### tags: `apcsp txt` `cs`

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
