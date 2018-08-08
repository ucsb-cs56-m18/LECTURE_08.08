# LECTURE_08.08

# Notes from Class

We showed a "bad" HS AP Java style program (your HS AP class was probably much better; sorry for the negative sterotyping.)

(Not sorry.)

What is bad about this program?

* No Encapsulation
* Global Variables
   * You can see them everywhere--it gets confusing.
   

# What is encapsulation

* Hides the how from the programmer (user of the class)
* Benefit: makes what you are trying to do simpler because you don't have to worry about some of the hows.
* Benefit: it makes the code easier to change:
   * Easier to find the place you need to make the change
   * Easier to know what change to make
   * Easier to make the change without breaking other things
   * Easier to write tests to know if the change is correct
   * Easier to isolate the effect of that change on other parts of the code..
   
As we will see, all of these benefits of "enscapsulation" are benefits of OOP in general, 
and more specifically, they are the main motivation for the things we call "design patterns".

# Tangents

* standard output vs. standard error---what are they, and why are they useful
* how do you redirect? <https://stackoverflow.com/questions/7901517/how-to-redirect-stderr-and-stdout-to-different-files-in-the-same-line-of-bash>

```
[pconrad@csil-10 08.08]$ java HelloWorld 
Hello World
Hello Error Stream
[pconrad@csil-10 08.08]$ java HelloWorld 1>>output
Hello Error Stream
[pconrad@csil-10 08.08]$ ls
BadHSAPProgram.class  BadHSAPProgram.java~  HelloWorld.java   output
BadHSAPProgram.java   HelloWorld.class      HelloWorld.java~
[pconrad@csil-10 08.08]$ more output 
Hello World
[pconrad@csil-10 08.08]$ java HelloWorld 2>>error
Hello World
[pconrad@csil-10 08.08]$ more error 
Hello Error Stream
[pconrad@csil-10 08.08]$ 
```

```java
public class HelloWorld {
    public static void main(String [] args) {
	System.out.println("Hello World");
	System.err.println("Hello Error Stream");
    }
}
```
