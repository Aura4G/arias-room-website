---
title: "One header One file?"
description: "Learning the key distinctions between having only 1 .cpp file, and have one for every header."
pubDate: 2026-08-05
tags: ["Tech", "Discussion", "C++", "Pre-processing"]
---

In 2025, I took on two C++ based projects, one after the other. This was an interesting experience for me as I embodied two different learning styles when it came to putting the code together, and a key thing regarding file structure became apparent to me. My question is, how badly does it matter?

For my first project, I was following a tutorial on youtube on how to build a compiler in C++. It was this brilliant series of videos by
<a href="https://www.youtube.com/watch?v=vcSijrRsrY0&list=PLUDlas_Zy_qC7c5tCgTMYq2idyyT241qs" target="_blank" rel="noopener noreferrer" class="text-blue-600">Pixeled</a>,
with an emphasis on creating a lightweight language and looking in-depth at program compilation's tie to assembly language. On a tangent real quick, I'd love to pick this project back up. My compiler reached a state in which variables and basic addition could be completed.

My second was a "Sudokrazy", a sudoku videogame passion project using SFML as a graphics interface (you can see more details about this project on the projects page). I followed no tutorial during the development of this game, instead relying on C++ and SFML documentation as well as my programming principles I've attained through lengthy experience with C and C++.

Though across my experience making both of these games, it struck me as odd, that the compiler tutorial had only one .cpp file, with the rest of the source code being contained in header files. Meanwhile I am far too used to the structure of one hpp per cpp file, a rhythm I'd argue I find comforting. I know if I want to make a new class in my program, I have the structure of declaring the class and its functions in headers and defining them in main code; the system has good bones right out of the gate.

Header files are a preprocessing step in C and C++ development. The preprocessor scans for any lines starting with #'s and performs quite literally a copy and paste operation at its position in the file. If you are writing one cpp file per header, this necessitates the use of include guards, ensuring if the header has not already been defined at an earlier point in the code, it is pasted there and then. This negates any duplicate symbol errors (any classes being defined more than once). So, is the benefit of only having the one cpp file negating this guarding step, given that they'll all be used in just that one file? Well, no. Some function definitions in a header may require structs or public variables defined in other headers, thus requiring the guards regardless.

The real boon behind using just one cpp file and the rest being headers (this indicating both the function definitions and declarations are in the same file), is distribution. By distributing these "header-only libraries", the folder of headers can simply be added to a new project and only require #include-ing it in the main file. This also eliminates linker dependencies and allows for the aggressive optimisation of a single cpp file, rather than leveraging multiple files that need compilation.

After learning this, it made far more sense to me! Now being far more informed I can ask myself the question as I embark on more C/C++ journeys or reignite old ones: what will I favour more? Fast optimisation and increased distribution capabilities in the form of header-only libraries, or the increased emphasis on encapsulation and immutability the definition-declaration split offers to create clean APIs? The choice is mine.
