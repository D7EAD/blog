<p align="right"><a href="https://blog.dreadsec.me/">Return to Main Page</a></p>

<p align="center">
  <img src="logo.png" width="200px">
</p>
<h3 align="center">Introduction to x86/x64 Assembly: Part One, The Basics</h3>

<p align="left">
  
Assembly is perhaps one of, if not the most, daunting languages one can learn in the realm of computer science and engineering. It’s like the deep end of the pool – that place where you tread cautiously, trying not to flounder in a sea of what seems like foreign instructions. It's raw, it's bare-bones, and it's fundamental to how a computer operates. So, in one form or another, it manages to worm its way into the lives of computer science and engineering students, typically in their first or second year.

In this blog series, we're aiming to make the beast called assembly a bit more approachable. We'll attempt to untangle its complexities and delve deep into its core. This first installment will walk you through the foundational aspects of assembly language.

So, whether you're a seasoned programmer looking to get back to the basics or a curious beginner raring to dive into the exhilarating world of low-level programming, this blog is for you. If the term 'assembly' incites a sense of foreboding, or if you merely want to understand what the fuss is all about, stick around.
  
<p>
  
<h3>Table of Contents</h3>

- Introduction to Assembly
  - Brief Overview of Assembly Language
  - The Importance of Learning Assembly
- Historical Context of Assembly Language
  - Brief History and Evolution
  - Role in Modern Computing
- Basics of Assembly Language
  - Structures Relevant to Assembly Language
  - Fundamental Components: Registers, Operands, and Instructions
- Getting Started with Assembly Language
  - Setting up Your Environment
- Writing Your First Assembly Program
  - A Look at Assembly Syntax
  - Understanding Basic Assembly Commands
  - Creating and Running a Simple Program
- Concluding Remarks and What to Expect in Part Two
- Resources for Further Learning

## Introduction to Assembly
### Brief Overview of Assembly Language
<p align="left">

  Assembly language, also commonly referred to as simply 'assembly', is a low-level programming language that has a strong correspondence with the architecture's machine code instructions. Think of it as the bridge between high-level languages (like Python, Java, or C++) and the computer hardware itself. While programming in high-level languages involves writing more human-readable code, assembly deals directly with the computer's nuts and bolts.

  <p align="center">
    <img src="langchart.png" />
  </p>
  
  The code written in assembly is processed by an assembler, which translates it into machine code—the lowest level of code that's directly executed by the computer's central processing unit (CPU). This means assembly gives you the power to write code that speaks directly to your computer's hardware.

  One of the key aspects of assembly language is that it is specific to a particular computer architecture, meaning the assembly language for one type of processor will differ from another. You'll often see terms like 'x86 assembly' or 'ARM assembly', referring to the specific hardware architectures.

  Now, you might be asking, "Why would I want to get my hands dirty with assembly when I could use Python or JavaScript?" That's a fair question. The answer lies in the level of control and optimization assembly provides. In certain situations—like systems programming, performance-critical applications, or when working with embedded systems—being able to control hardware at this granular level is a major advantage.

  For the sake of our collective sanity, we will be learning and making use of Intel’s syntax for x86 and x64 assembly in this series of blog posts. There are two major syntaxes for x86 and x64, Intel and AT&T, and, as you can tell from the previous remark, one is much better than the other.
  
  For example, just take a look at the difference between the two below.
</p>

<table align="center" style="margin: 0px auto;">
<tr>
<th>x86 (Intel)</th>
<th>x86 (AT&T)</th>
</tr>
<tr>
<td>

```asm
push eax     
mov eax, [ebx]
add eax, 5  
inc eax       
mov ebx, eax
pop eax      
add eax, ebx    
```

</td>
<td>

```asm
pushl %eax        
movl (%ebx), %eax   
addl $5, %eax   
incl %eax        
movl %eax, %ebx   
popl %eax      
addl %ebx, %eax  
```

</td>
</tr>
</table>

<p align="center">We will be using the syntax on the left throughout this series.</p>

### The Importance of Learning Assembly

<p align="left">
  
You might be wondering why we should bother learning assembly language when we have powerful high-level languages at our disposal. Surely, it's easier to write a Python script or a C++ program, but there are several reasons why learning assembly is still highly beneficial, even in our modern computing landscape. For instance:

1. <b>Understanding How Computers Truly Work</b>:
Assembly language is a window into the heart of your computer. When you learn assembly, you get to understand the intricate mechanisms that allow your computer to function. You learn about registers, how data is managed in memory, how instructions are processed, and much more. It's like peeking under the hood of your car – you get to see the engine that drives the entire system.

2. <b>Performance Optimization</b>:
There are instances where the speed and efficiency of a program are absolutely critical, such as in game development, real-time systems, or high-frequency trading systems. With assembly, you have the ultimate control over your code, allowing you to squeeze out every ounce of performance from your hardware.

3. <b>Debugging and Reverse Engineering</b>:
Sometimes, to find an elusive bug or to understand a piece of malware, you'll need to dive into the assembly code of a program. Debuggers often show you the assembly instructions that correspond to your high-level code. By understanding assembly, you'll be better equipped to tackle these tasks.

4. <b>Writing Drivers and Embedded Systems Programming</b>:
Assembly language is often used to write drivers and for programming embedded systems, where hardware-specific code is necessary, and resources like memory and processing power are limited.

5. <b>Broadens Your Skill Set</b>:
Finally, having assembly language in your repertoire is an excellent way to stand out. It demonstrates your willingness to dive deep into complex topics and your understanding of computers at a fundamental level.
  
</p>

<p align="center">brought to you by <a href="https://github.com/D7EAD">d7ead</a></p>
