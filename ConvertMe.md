# Convert Me

>Solved: 12/20/2023

>Points: 100

>Category: General Skills

## Overview

>Run the Python script and convert the given number from decimal to binary to get the flag. <br>
>[Download convertme.py](https://artifacts.picoctf.net/c/24/convertme.py)

## Hints

1. Look up a decimal to binary number conversion app on the web or use your computer's calculator!
2. The `str_xor` function does not need to be reverse engineered for this challenge.
3. f you have Python on your computer, you can download the script normally and run it. Otherwise, use the wget command in the webshell.
4. To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
5. Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
6. Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`
   
## Approach

1. After using `wget` to download the file, and running `python convertme.py`, we are asked a question.
   `If 67 is in decimal base, what is it in binary base?`
2. We can get this by dividing 67 by 2 until we get a quotient of 0.
3. Doing this gives us 1000011.
4. Entering that into the programs gives us our flag.

## Flag

picoCTF{4ll_y0ur_b4535_722f6b39}
