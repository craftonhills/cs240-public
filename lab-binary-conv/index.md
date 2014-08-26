#Lab - Binary Number Conversion

## Exercises

1. Convert the following 8-bit 2's complement numbers to decimal by hand:
  1. 10101010
  2. 01010101

2. Convert the following decimal integers to 8-bit two’s complement binary numbers by hand.
  1. 88
  2. -123

## Programming

Write a C program that prompts the user to enter a *2's complement* binary number, multiplies it by ten, then displays the result in both decimal and binary. 

Format the I/O of your program as follows (`*text*` represents program input):

    Enter a 2's complement binary number: *1001*
    1001 (base 2) = -7 (base 10)
    -7 (base 10) x 10 = -70 (base 10) = 10111010 (base 2)
    
    Enter a 2's complement binary number: *0*
    0 (base 2) = 0 (base 10)
    0 (base 10) x 10 = 0 (base 10) = 0 (base 2)
    
    Enter a 2's complement binary number: *1*
    1 (base 2) = -1 (base 10)
    -1 (base 10) x 10 = -10 (base 10) = 10110 (base 2)
    
    Enter a 2's complement binary number: *00011110*
    00011110 (base 2) = 30 (base 10)
    30 (base 10) x 10 = 300 (base 10) = 0100101100 (base 2)

The input binary number does not have a fixed bit width (i.e. it can contain any number of bits but no more than 64 bits).  Since it is in 2's complement format, the sign of the binary number is determined by the most significant (leftmost) bit. For example, binary number 1001 is -7 in decimal. The result in binary should be displayed with the minimum number of bits possible to representative the number.

Name your C file `binary_conv.c`.

## How to Submit Your Completed Lab

Put the following files in a directory named `lab-binary`:
* `answers.txt`: a text file containing answers to the exercises
* `binary_conv.c`: binary conversion C program
* `results.txt`: your program outputs given representative test cases

Make sure the directory `lab-binary` is posted to your private cs240 repository. Always double check that your files are pushed successfuly to GitHub.
