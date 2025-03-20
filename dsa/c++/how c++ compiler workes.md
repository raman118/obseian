The C++ compiler transforms human-readable source code into machine-executable binary through a multi-stage process. This compilation pipeline consists of four primary stages:

## Preprocessing

The preprocessor runs before actual compilation begins and performs text substitution and file inclusion:

- Processes directives that start with `#` symbols[3](https://roadmap.sh/cpp/compilers/stages)[5](https://stackoverflow.com/questions/12982106/what-does-preprocessing-exactly-mean-in-compiler)
    
- Replaces `#include` directives with the entire content of the included header files[1](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)[6](https://www.scaler.com/topics/how-to-compile-cpp/)
    
- Expands macros defined with `#define`[3](https://roadmap.sh/cpp/compilers/stages)[5](https://stackoverflow.com/questions/12982106/what-does-preprocessing-exactly-mean-in-compiler)
    
- Evaluates conditional compilation blocks (like `#if`, `#ifdef`, `#ifndef`) and removes code that evaluates to `false`[1](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)[5](https://stackoverflow.com/questions/12982106/what-does-preprocessing-exactly-mean-in-compiler)
    
- Generates a translation unit (sometimes called intermediate code with .i extension)[1](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)[2](https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger)
    

For example, a simple "hello world" program with just a few lines can expand to thousands of lines after preprocessing due to included header files[1](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation).

## Compilation

After preprocessing, the compiler proper takes over:

- Translates the preprocessed code into assembly language specific to the target processor architecture[3](https://roadmap.sh/cpp/compilers/stages)[7](https://www.freecodecamp.org/news/c-compiler-explained-what-is-the-compiler-and-how-do-you-use-it/)
    
- Performs syntax checking and semantic analysis[3](https://roadmap.sh/cpp/compilers/stages)
    
- Identifies and reports errors in the source code[7](https://www.freecodecamp.org/news/c-compiler-explained-what-is-the-compiler-and-how-do-you-use-it/)
    
- Generates assembly code (.s files)[2](https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger)[3](https://roadmap.sh/cpp/compilers/stages)
    

This stage transforms C++ language constructs into low-level assembly instructions that represent the same operations.

## Assembly

The assembly phase converts the assembly code into machine code:

- Translates assembly language instructions into binary object code[3](https://roadmap.sh/cpp/compilers/stages)[8](https://www.prepbytes.com/blog/cpp-programming/cpp-compilation-process/)
    
- Creates object files (typically with .o extension)[2](https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger)[6](https://www.scaler.com/topics/how-to-compile-cpp/)
    
- Object files contain machine code but may have unresolved references to external symbols[8](https://www.prepbytes.com/blog/cpp-programming/cpp-compilation-process/)
    

These object files contain the compiled code but are not yet executable.

## Linking

The final stage connects all the pieces together:

- Combines multiple object files into a single executable[1](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)[3](https://roadmap.sh/cpp/compilers/stages)
    
- Resolves references to external symbols and functions across object files[3](https://roadmap.sh/cpp/compilers/stages)[8](https://www.prepbytes.com/blog/cpp-programming/cpp-compilation-process/)
    
- Links required libraries (standard or third-party)[3](https://roadmap.sh/cpp/compilers/stages)
    
- Allocates memory addresses for functions and variables[3](https://roadmap.sh/cpp/compilers/stages)
    
- Produces the final executable program[2](https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger)[3](https://roadmap.sh/cpp/compilers/stages)
    

The linker handles situations where code in one file references functions or variables defined in another file or library.

## Compilation Commands Example

Using GCC on Linux, the entire process can be executed with these commands:

bash

`# Preprocessing: generate intermediate file gcc -E source.cpp -o source.i # Compilation: generate assembly file gcc -S source.i -o source.s # Assembly: generate object file gcc -c source.s -o source.o # Linking: generate executable program gcc source.o -o program`

Alternatively, all these steps can be performed with a single command:

bash

`g++ source.cpp -o program`

This comprehensive process ensures that C++ code is correctly translated into efficient machine code that can be executed by the computer.

### Citations:

1. [https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)
2. [https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger](https://www.linkedin.com/pulse/c-compilation-steps-amit-nadiger)
3. [https://roadmap.sh/cpp/compilers/stages](https://roadmap.sh/cpp/compilers/stages)
4. [https://dev.to/shreyosghosh/behind-the-scenes-of-c-compiling-and-linking-j0n](https://dev.to/shreyosghosh/behind-the-scenes-of-c-compiling-and-linking-j0n)
5. [https://stackoverflow.com/questions/12982106/what-does-preprocessing-exactly-mean-in-compiler](https://stackoverflow.com/questions/12982106/what-does-preprocessing-exactly-mean-in-compiler)
6. [https://www.scaler.com/topics/how-to-compile-cpp/](https://www.scaler.com/topics/how-to-compile-cpp/)
7. [https://www.freecodecamp.org/news/c-compiler-explained-what-is-the-compiler-and-how-do-you-use-it/](https://www.freecodecamp.org/news/c-compiler-explained-what-is-the-compiler-and-how-do-you-use-it/)
8. [https://www.prepbytes.com/blog/cpp-programming/cpp-compilation-process/](https://www.prepbytes.com/blog/cpp-programming/cpp-compilation-process/)
9. [https://icarus.cs.weber.edu/~dab/cs1410/textbook/1.Basics/compiler_op.html](https://icarus.cs.weber.edu/~dab/cs1410/textbook/1.Basics/compiler_op.html)
10. [https://www.udacity.com/blog/2020/02/c-compilers-explained.html](https://www.udacity.com/blog/2020/02/c-compilers-explained.html)
11. [https://www.youtube.com/watch?v=3tIqpEmWMLI](https://www.youtube.com/watch?v=3tIqpEmWMLI)
12. [https://stackoverflow.com/questions/8833524/what-are-the-stages-of-compilation-of-a-c-program](https://stackoverflow.com/questions/8833524/what-are-the-stages-of-compilation-of-a-c-program)
13. [https://subscription.packtpub.com/book/programming/9781789801491/1/ch01lvl1sec03/the-c-compilation-model](https://subscription.packtpub.com/book/programming/9781789801491/1/ch01lvl1sec03/the-c-compilation-model)
14. [https://www.youtube.com/watch?v=ksJ9bdSX5Yo](https://www.youtube.com/watch?v=ksJ9bdSX5Yo)
15. [https://stackoverflow.com/questions/6264249/how-does-the-compilation-linking-process-work](https://stackoverflow.com/questions/6264249/how-does-the-compilation-linking-process-work)
16. [https://www.tutorialspoint.com/cplusplus/cpp_preprocessor.htm](https://www.tutorialspoint.com/cplusplus/cpp_preprocessor.htm)
17. [https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2021/03/17115658/Sample-18-1024x724.png?sa=X&ved=2ahUKEwjn1qf34_2LAxW2dvUHHT3bNDoQ_B16BAgLEAI](https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2021/03/17115658/Sample-18-1024x724.png?sa=X&ved=2ahUKEwjn1qf34_2LAxW2dvUHHT3bNDoQ_B16BAgLEAI)
18. [https://cplusplus.com/doc/tutorial/preprocessor/](https://cplusplus.com/doc/tutorial/preprocessor/)
19. [https://www.ibm.com/docs/en/i/7.4?topic=reference-preprocessor-directives](https://www.ibm.com/docs/en/i/7.4?topic=reference-preprocessor-directives)
20. [https://en.cppreference.com/w/cpp/preprocessor](https://en.cppreference.com/w/cpp/preprocessor)
21. [https://learn.microsoft.com/en-us/cpp/preprocessor/c-cpp-preprocessor-reference?view=msvc-170](https://learn.microsoft.com/en-us/cpp/preprocessor/c-cpp-preprocessor-reference?view=msvc-170)
22. [https://www.programiz.com/cpp-programming/preprocessor-macros](https://www.programiz.com/cpp-programming/preprocessor-macros)

---

Answer from Perplexity: [pplx.ai/share](https://www.perplexity.ai/search/pplx.ai/share)