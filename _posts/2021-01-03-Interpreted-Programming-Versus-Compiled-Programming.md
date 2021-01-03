---
layout: post
excerpt: Interpreted Programming Versus Compiled Programming
permalink: /Compile vs Interpreted Programming
published: true
---

From my research it seems that the big difference is that there is one more layer of converting the code into instructions that the computer can understand in interpreted programming.

One of my favorite languages to use is Java.

After diving a little deeper into java, interestingly enough, Java is neither of these type of programming if it were to be fit into a specific bucket. Java is written in java files then compiled using a java compiler. But java compiler does not convert this code into native code. This byte code cannot be directly executed by the CPU. This compiled code is then executed but a Java virtual machine. 	

On the other hand Go is a compiled language. Thus go code needs to be compile everytime before it can be run. Because the code is instantly converted into machine code this process tends to be faster then interpreted programming. But why would interpreted programming be use if compile programming tends to be faster?

One reason would be the flexibility of interpreted programming. For example, a language like ruby provides a lot of runtime libraries which bloats the program. In exchange for speed it allows for faster code shipping. 
