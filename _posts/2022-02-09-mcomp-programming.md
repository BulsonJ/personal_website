---
layout: post
title:  "MComp Programming for Games"
category: project
---

The first module that I completed at University was Programming for Games. For the first half of this module, we learnt C++ from the ground up and worked our way through a series of tutorials. Although having prior experience in C++, I still found these exercises useful as I approached them from a different point of view in the past. Whereas before I was trying to get my code to just work, this year I tried to really understand how C++ functions and what you can do with it.

Our coursework for this module was to use the Collatz conjecture to create an application that could encrypt passwords using it, and then also decrypt them. It was essentially, a basic password manager.

<img src="/assets/images/programming-for-games/main-menu.png" alt=""/>

To test the strength of the passwords, the program was able to generate a file consisting of 20000 random passwords, varying in length and character used. We then had to make our program be able to crack these passwords.

<img src="/assets/images/programming-for-games/cracked-password.png" alt=""/>
<img src="/assets/images/programming-for-games/cracked-password2.png" alt=""/>

The final challenge we were set was to crack a string "27322810313331033910211452912207344136146925461033281533271031012815108114101". To be able to crack this string, I loaded a dictionary into the program. My solution for this was to only consider collatz values that matched with a lowercase character(information we were given). My program then went through the string and found all possible combinations of words and possible letters. Then, I checked each possible combination of letters to check if it was a valid word. If it was, it was added to list of possibilities. I then printed out all possible solutions to the string at the end of the program.

<img src="/assets/images/programming-for-games/sentence.png" alt=""/>

