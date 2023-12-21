# Matryoshka doll

>Solved 10/23/2023

>Points: 30

>Category: Forensics

## Overview 

>Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

## Hints

1. Wait, you can hide files inside files? But how do you find them?

2. Make sure to submit the flag as picoCTF{XXXXX}

## Approach

1. Downloading the file we see that it is just a regular jpeg file of a Matryoshka doll, how do we get the files hiddens inside of this file?

2. Doing some research, it seems you can zip files inside of a jpg. So, lets try `unzip` on the jpg.

3. Using `unzip` gives us a `2_c.jpg` file, this is on the right track but this is not the flag, lets try the `unzip` command again.

4. Doing this 3 more times gives us `3_c.jpg`, `4_c.jpg`, and `flag.txt`. Hurray! this is our flag.

## Flag
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}
