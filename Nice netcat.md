# Nice Netcat...

>Solved: 10/22/2023

## Overview

Points: 15
Catagory: General Skills

>There is a nice program that you can talk to by using this command in a shell: $ nc mercury.picoctf.net 7449, but it doesn't speak English..

## Hints

1. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2. You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Approach

1. I did not know what a Netcat was so I followed the first hint and learned about Netcats.

2. Next, I connected to the webshell and ran the command `nc mercury.picoctf.net 7449`. Giving me:
>112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
102 
50 
100 
55 
99 
97 
102 
97 
125 
10

3. Based on the hint this is ASCII in hexadecimal. Looking online gave me a few options on how to decode this, but I settled on practicing a bit of Python.
   Thank you to [vivian-dai](https://github.com/vivian-dai/PicoCTF2021-Writeup/blob/main/General%20Skills/Nice%20netcat/Nice%20netcat.md?plain=1)
   ```Python
   numbers = [112, 105, 99, 111, 67, 84,
          70, 123, 103, 48, 48, 100,
          95, 107, 49, 116, 116, 121,
          33, 95, 110, 49, 99, 51,
          95, 107, 49, 116, 116, 121,
          33, 95, 102, 50, 100, 55,
          99, 97, 102, 97, 125, 10]

    flag =''

    for num in numbers:
        flag += chr(num)

    print(flag)
    ```

## Flag
picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}
