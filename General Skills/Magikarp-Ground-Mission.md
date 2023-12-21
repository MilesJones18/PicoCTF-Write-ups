# Magikarp Ground Mission

>Solved: 10/22/2023
>
>Points: 30
>
>Category: General Skills

## Overview

>Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88`

## Hints

1. Finding a cheatsheet for bash would be really helpful!

## Approach

1. First I started the instance on the PicoCTF website.

2. Next, I `ssh ctf-player@venus.picoctf.net -p 50242` into the instance.

3. `ls` gives us 2 files, `1of3.flag.txt` and `instructions-to-2of3.txt`

4. `cat 1of3.flag.txt` gives us the first third of the flag, but we have to find the second and third.

5. `cat instructions-to-2of3.txt` tells us to go to the root.

6. `cd /` takes us to root, and running `ls` gives us `2of3.flag.txt` which gives us the 2 third of the flag.

7. The instructions file tell us to go home.

8. `cd ~` takes us home.

9. Running `ls` gives us `3of3.flag.txt` which gives us the last half of the flag.

## Flag
picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}
