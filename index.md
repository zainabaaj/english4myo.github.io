# 1  The Python programming language

Two kinds of programs process high-level languages into low-level languages: interpreters and compilers. An interpreter reads a high-level program and executes it, meaning that it does what the program says. It processes the program a little at a time, alternately reading lines and performing computations. Figure 1.1 shows the structure of an interpreter.

![Image](http://www.greenteapress.com/thinkpython/html/thinkpython001.png)
Figure 1.1: An interpreter processes the program a little at a time, alternately reading lines and performing computations.
A compiler reads the program and translates it completely before the program starts running. In this context, the high-level program is called the source code, and the translated program is called the object code or the executable. Once a program is compiled, you can execute it repeatedly without further translation. Figure 1.2 shows the structure of a compiler.

![Image](http://www.greenteapress.com/thinkpython/html/thinkpython002.png)
Figure 1.2: A compiler translates source code into object code, which is run by a hardware executor.
Python is considered an interpreted language because Python programs are executed by an interpreter. There are two ways to use the interpreter: interactive mode and script mode. In interactive mode, you type Python programs and the interpreter displays the result:

>>> 1 + 1
2
The chevron, >>>, is the prompt the interpreter uses to indicate that it is ready. If you type 1 + 1, the interpreter replies 2.

Alternatively, you can store code in a file and use the interpreter to execute the contents of the file, which is called a script. By convention, Python scripts have names that end with .py.

To execute the script, you have to tell the interpreter the name of the file. If you have a script named dinsdale.py and you are working in a UNIX command window, you type python dinsdale.py. In other development environments, the details of executing scripts are different. You can find instructions for your environment at the Python website http://python.org.

Working in interactive mode is convenient for testing small pieces of code because you can type and execute them immediately. But for anything more than a few lines, you should save your code as a script so you can modify and execute it in the future.

# 2  What is a program?
A program is a sequence of instructions that specifies how to perform a computation. The computation might be something mathematical, such as solving a system of equations or finding the roots of a polynomial, but it can also be a symbolic computation, such as searching and replacing text in a document or (strangely enough) compiling a program.

The details look different in different languages, but a few basic instructions appear in just about every language:input:Get data from the keyboard, a file, or some other device.output:Display data on the screen or send data to a file or other device.math:Perform basic mathematical operations like addition and multiplication.conditional execution:Check for certain conditions and execute the appropriate code.repetition:Perform some action repeatedly, usually with some variation.

Believe it or not, that’s pretty much all there is to it. Every program you’ve ever used, no matter how complicated, is made up of instructions that look pretty much like these. So you can think of programming as the process of breaking a large, complex task into smaller and smaller subtasks until the subtasks are simple enough to be performed with one of these basic instructions.

That may be a little vague, but we will come back to this topic when we talk about algorithms.

# 3  What is debugging?
Programming is error-prone. For whimsical reasons, programming errors are called bugs and the process of tracking them down is called debugging.

Three kinds of errors can occur in a program: syntax errors, runtime errors, and semantic errors. It is useful to distinguish between them in order to track them down more quickly.

## 3.1  Syntax errors
Python can only execute a program if the syntax is correct; otherwise, the interpreter displays an error message. Syntax refers to the structure of a program and the rules about that structure. For example, parentheses have to come in matching pairs, so (1 + 2) is legal, but 8) is a syntax error.

In English, readers can tolerate most syntax errors, which is why we can read the poetry of e. e. cummings without spewing error messages. Python is not so forgiving. If there is a single syntax error anywhere in your program, Python will display an error message and quit, and you will not be able to run your program. During the first few weeks of your programming career, you will probably spend a lot of time tracking down syntax errors. As you gain experience, you will make fewer errors and find them faster.

## 3.2  Runtime errors
The second type of error is a runtime error, so called because the error does not appear until after the program has started running. These errors are also called exceptions because they usually indicate that something exceptional (and bad) has happened.

Runtime errors are rare in the simple programs you will see in the first few chapters, so it might be a while before you encounter one.

## 3.3  Semantic errors
The third type of error is the semantic error. If there is a semantic error in your program, it will run successfully in the sense that the computer will not generate any error messages, but it will not do the right thing. It will do something else. Specifically, it will do what you told it to do.

The problem is that the program you wrote is not the program you wanted to write. The meaning of the program (its semantics) is wrong. Identifying semantic errors can be tricky because it requires you to work backward by looking at the output of the program and trying to figure out what it is doing.

## 3.4  Experimental debugging
One of the most important skills you will acquire is debugging. Although it can be frustrating, debugging is one of the most intellectually rich, challenging, and interesting parts of programming.

In some ways, debugging is like detective work. You are confronted with clues, and you have to infer the processes and events that led to the results you see.

Debugging is also like an experimental science. Once you have an idea about what is going wrong, you modify your program and try again. If your hypothesis was correct, then you can predict the result of the modification, and you take a step closer to a working program. If your hypothesis was wrong, you have to come up with a new one. As Sherlock Holmes pointed out, “When you have eliminated the impossible, whatever remains, however improbable, must be the truth.” (A. Conan Doyle, The Sign of Four)

For some people, programming and debugging are the same thing. That is, programming is the process of gradually debugging a program until it does what you want. The idea is that you should start with a program that does something and make small modifications, debugging them as you go, so that you always have a working program.

For example, Linux is an operating system that contains thousands of lines of code, but it started out as a simple program Linus Torvalds used to explore the Intel 80386 chip. According to Larry Greenfield, “One of Linus’s earlier projects was a program that would switch between printing AAAA and BBBB. This later evolved to Linux.” (The Linux Users’ Guide Beta Version 1).

Later chapters will make more suggestions about debugging and other programming practices.


# 4  The first program
Traditionally, the first program you write in a new language is called “Hello, World!” because all it does is display the words “Hello, World!”. In Python, it looks like this:

print 'Hello, World!'
This is an example of a print statement, which doesn’t actually print anything on paper. It displays a value on the screen. In this case, the result is the words

Hello, World!
The quotation marks in the program mark the beginning and end of the text to be displayed; they don’t appear in the result.

In Python 3, the syntax for printing is slightly different:

print('Hello, World!')
The parentheses indicate that print is a function. We’ll get to functions in Chapter 3.

For the rest of this book, I’ll use the print statement. If you are using Python 3, you will have to translate. But other than that, there are very few differences we have to worry about.

# 5  Debugging
It is a good idea to read this book in front of a computer so you can try out the examples as you go. You can run most of the examples in interactive mode, but if you put the code in a script, it is easier to try out variations.

Whenever you are experimenting with a new feature, you should try to make mistakes. For example, in the “Hello, world!” program, what happens if you leave out one of the quotation marks? What if you leave out both? What if you spell print wrong?

This kind of experiment helps you remember what you read; it also helps with debugging, because you get to know what the error messages mean. It is better to make mistakes now and on purpose than later and accidentally.

Programming, and especially debugging, sometimes brings out strong emotions. If you are struggling with a difficult bug, you might feel angry, despondent or embarrassed.

There is evidence that people naturally respond to computers as if they were people. When they work well, we think of them as teammates, and when they are obstinate or rude, we respond to them the same way we respond to rude, obstinate people (Reeves and Nass, The Media Equation: How People Treat Computers, Television, and New Media Like Real People and Places).

Preparing for these reactions might help you deal with them. One approach is to think of the computer as an employee with certain strengths, like speed and precision, and particular weaknesses, like lack of empathy and inability to grasp the big picture.

Your job is to be a good manager: find ways to take advantage of the strengths and mitigate the weaknesses. And find ways to use your emotions to engage with the problem, without letting your reactions interfere with your ability to work effectively.

Learning to debug can be frustrating, but it is a valuable skill that is useful for many activities beyond programming. At the end of each chapter there is a debugging section, like this one, with my thoughts about debugging. I hope they help!

# 6  Glossary
- **problem solving:**
The process of formulating a problem, finding a solution, and expressing the solution.
- **high-level language:**
A programming language like Python that is designed to be easy for humans to read and write.
- **low-level language:**
A programming language that is designed to be easy for a computer to execute; also called “machine language” or “assembly language.”
- **portability:**
A property of a program that can run on more than one kind of computer.
- **interpret:**
To execute a program in a high-level language by translating it one line at a time.
- **compile:**
To translate a program written in a high-level language into a low-level language all at once, in preparation for later execution.
- **source code:**
A program in a high-level language before being compiled.
- **object code:**
The output of the compiler after it translates the program.
- **executable:**
Another name for object code that is ready to be executed.
- **prompt:**
Characters displayed by the interpreter to indicate that it is ready to take input from the user.
- **script:**
A program stored in a file (usually one that will be interpreted).
- **interactive mode:**
A way of using the Python interpreter by typing commands and expressions at the prompt.
- **script mode:**
A way of using the Python interpreter to read and execute statements in a script.
- **program:**
A set of instructions that specifies a computation.
- **algorithm:**
A general process for solving a category of problems.
- **bug:**
An error in a program.
- **debugging:**
The process of finding and removing any of the three kinds of programming errors.
- **syntax:**
The structure of a program.
- **syntax error:**
An error in a program that makes it impossible to parse (and therefore impossible to interpret).
- **exception:** 
An error that is detected while the program is running.
- **semantics:**
The meaning of a program.
- **semantic error:** 
An error in a program that makes it do something other than what the programmer intended.
- **token:** 
One of the basic elements of the syntactic structure of a program, analogous to a word in a natural language.
- **parse:**
To examine a program and analyze the syntactic structure.
- **print statement:** 
An instruction that causes the Python interpreter to display a value on the screen.
