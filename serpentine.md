# Serpentine

>Solved: 12/20/2023

>Points: 100

>Category: General Skills

## Overview

>Find the flag in the Python script! [Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)

## Hints

1. Try running the script and see what happens.
2. In the webshell, try examining the script with a text editor like `nano`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.

## Approach

1. Running the program gives us 3 options, `encourage`, `print key`, and `exit`, obviously the one we want is `print key`.
2. Choosing this option gives us an error, telling us that the print_key() function is not used. Let's fix that.
3. Using `nano` to look at the code, we are looking for 2 specific functions in the program
   1. The `print_flag()` function.
      ```Python
         def print_flag():
         flag = str_xor(flag_enc, 'enkidu')
         print(flag)****
      ```
   2. And the function that allows us to choose to print the flag in the menu.
      ```Python
      elif choice == 'b':
        print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
      ```
  4. This is a pretty simple fix, we just need to delete the print error statement, and add in a call to the `print_flag`
     function.
     ```Python
     elif choice == 'b':
       print_flag()
     ```
## Flag

picoCTF{example}
