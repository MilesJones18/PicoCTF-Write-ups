# Strings it

>Solved 10/22/2023

Points: 100
Category: General Skills

## Overview

>Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Hints

1. [strings](https://linux.die.net/man/1/strings)

## Approach

1. Download the file from the PicoCTF website.

2. The hint on the problem wants us to use the `strings strings` command. Using it gives us a lot of human readable text, which is a start.

3. We can use `grep picoCTF` in our previous command to search through the text, which gives us our flag.

## Flag
picoCTF{5tRIng5_1T_d66c7bb7}
