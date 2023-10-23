# Tab Tab Attack

>Solved 10/22/2023

Points: 20
Categories: General Skills

## Overview

>Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)

## Hints

After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Approach

1. Opened the webshell and downloaded the zip file.

2. `unzip Addadshashanammu.zip` This gives us the first file.

3. `cd ` into this folder.

4. Next we just cd into each folder, using tabcomplete to make typing the long file names easier.

5. Finally, we get to a file, using `./fang-of-haynekhtnamet` runs the file, giving us the flag.

## Flag
picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
