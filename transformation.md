# Transformation

>Solved 12/20/2023

>Points: 20

>Category: Reverse Engineering

## Overview

>I wonder what this really is... [enc](https://mercury.picoctf.net/static/77a2b202236aa741e988581e78d277a6/enc)<br>
>`''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Hints

1. You may find some decoders online.

## Approach

1. After downloading the file, I used `cat` in order to read the contents of the file. That gave me this...
   `灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸強㕤㐸㤸扽`
   Ok... Not sure what to do with this but lets figure it out. The example code should be a clue.
2. I did a little research, I am not super familier with encoding techniques so understanding what
   the example code to a little time.
3. Basically, what the example code is doing is iterating over each the `flag` string, 2 characters at a time, then
   adding them together, creating a 16 bit character
5. So feasibly we could iterate through each character in the cipher and 'deconstruct' them into the 2 bytes that
   hold the flag text. But with python, their is almost always an easier way. :)
6. Here is a short script I wrote...
   ```Python
   input = open('./enc','r')
   text = input.readline()
   print(text.encode('utf-16-be'))
   ```
   Because each character is Unicode, we can use the utf-16 big endian encoder to do it for us, instead of writing a longer
   program and do it by hand. Oh the glories of python.
7. Running this program gives us our flag.

## Flag

picoCTF{16_bits_inst34d_of_8_75d4898b}
