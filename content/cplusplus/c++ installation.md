
<meta name="twitter:title" content=”C++ Installation and Environment Setup” />


C++ is a general purpose programming language that is popularly used worldwide. C++ is efficient in terms of both memory and performance that makes it handy in competitive programming. C++ provides features like reusability of code, abstraction, polymorphism, inheritance, etc.
C++ can be run on many platforms like linux, windows, mac.
To start coding we need to first set up the environment to compile and run our C++ programs. We can also use online IDE’s for the compilation if we don't want to set up the environment locally. We will go through both the processes in this article.

**Note :** IDE is Integrated Development Environment

## Programming through Online IDE’s:
There are many online IDE’s that provide us with the comfort of running our programs online without setting up the environment locally. Examples are GFG IDE, Codechef IDE etc.

### 1. Geeks for Geeks ( https://ide.geeksforgeeks.org/ )
We can choose from other languages also from the left side bar. We can write our code and then hit the RUN button at the bottom. We can also provide input at bottom from beside the run button.

![C++ Installation and Environment Setup](/images/cplusplus/1_GFG_IDE.png "GFG")

**Output :** We will get our output at bottom of page like this
![C++ Installation and Environment Setup](/images/cplusplus/2_GFG_Output.png "GFG")


### 2. Codechef IDE ( https://www.codechef.com/ide )
In this also we can choose from multiple languages. We can also provide a custom input from the bottom next to the RUN button.

![C++ Installation and Environment Setup](/images/cplusplus/3_Codechef_IDE.png "Codechef")

**Output -** Output will be displayed at the bottom 
![C++ Installation and Environment Setup](/images/cplusplus/4_Codechef_output.png "Codechef")


### 3. Ideone ( https://ideone.com/ )

![C++ Installation and Environment Setup](/images/cplusplus/5_Ideone_IDE.png "Ideone")

**Output -** After compilation we an see output like this
![C++ Installation and Environment Setup](/images/cplusplus/6_Ideone_output.png "Ideone")


## Setting up the local environment 
To run a C++ code on a local machine we need two main things. 
- Text Editor 
- C++ compiler

### 1. Text Editor - 
This is used to write and edit our C++ programs. One important thing that is to be considered here is that the file must be saved with a .cpp extension. This file contains our source code. We can simply use a text editor or notepad for writing our source code. Compiler identifies that the file has a C++ program if it is saved with a .cpp extension.

### 2. C++ Compiler - 
A compiler is a program that converts the high level programming language to machine understandable low level programming language. We will see how to set up our compiler in linux - 

We will be installing a GNU GCC compiler.

First of all open the command prompt by pressing CTRL+ALT+T
Then run these following commands.
‘’’c
sudo apt-get update
‘’’
Then enter the password to your computer
![C++ Installation and Environment Setup](/images/cplusplus/7_img.png "update")

Now to install GCC compiler use command 
‘’’c
sudo apt-get install GCC
‘’’
![C++ Installation and Environment Setup](/images/cplusplus/8_img.png "install")

Then run this command that will install all libraries required to compile and run the program.
‘’’c
sudo apt-get install build-essential
‘’’
![C++ Installation and Environment Setup](/images/cplusplus/9_img.png "build")


Now check if the GCC is installed correctly by command.
‘’’c
g++ --version
‘’’
![C++ Installation and Environment Setup](/images/cplusplus/10_img.png "check")

Now the GCC is successfully installed.


## Now we will walk through examples to run and compile a program

### Example 1 - Print a message Hello World

First we have to open a text editor and write our code 
![C++ Installation and Environment Setup](/images/cplusplus/11_img.png "open")

Save the programme with name lets say here first_programme on desktop with .cpp extension.
![C++ Installation and Environment Setup](/images/cplusplus/12_img.png "save")

Then open the command prompt with command CTRL+ALT+T.

Then move to the directory where our programme file is saved by using cd _.
![C++ Installation and Environment Setup](/images/cplusplus/13_img.png "move")

Then write the following command to compile 
‘’’c
G++ filename.cpp -o output-file-name
‘’’

**Note -** filename.cpp is source code file
**Note -** output-file-name is name given to executable file which will be created by compiler

In this case we make a output file with name Output_file_1
![C++ Installation and Environment Setup](/images/cplusplus/14_img.png "execute-file")

On running this command an executable file with name Output_file_1 will be saved in the same directory where our source code is saved.
![C++ Installation and Environment Setup](/images/cplusplus/16_img.png "desktop")

To run the programme we need to write this command in the terminal window which will show us the output of the programme.
![C++ Installation and Environment Setup](/images/cplusplus/15_img.png "output")

Output Hello World is printed in the terminal window.


### Example 2 - Programme which also takes an input. We have to write a program that takes in radius and prints the area of the circle.

Open text editor and write programme
![C++ Installation and Environment Setup](/images/cplusplus/17_img.png "text-2")

Then save the programme with name lets say here second_programme on desktop with .cpp extension.
![C++ Installation and Environment Setup](/images/cplusplus/18_img.png "save-2")

Go to the programme directory in command prompt and type compile command.
‘’’c
g++ second_programme.cpp -o Output_file_2
‘’’
Then run the executable file through command ( ./Output_file_2 )
![C++ Installation and Environment Setup](/images/cplusplus/19_img.png "run-2")

The terminal will wait for the input of radius, here let us provide **5** and hit enter.
![C++ Installation and Environment Setup](/images/cplusplus/20_img.png "final")

We will get output area as 78.5.







