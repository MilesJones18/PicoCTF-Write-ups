# Codebook

>Solved: 12/20/2023

>Points: 100

>Category: General Skills

## Overview

>Run the Python script code.py in the same directory as codebook.txt. <br>
>[Download code.py](https://artifacts.picoctf.net/c/1/code.py) <br>
>[Download codebook.txt](https://artifacts.picoctf.net/c/1/code.py)

## Hints

1. On the webshell, use `ls` to see if both files are in the directory you are in.
2. The `str_xor` function does not need to be reverse engineered for this challenge.

## Approach

1. `wget` both files into the same directory.
2. Running `python code.py` in the same directory gives us the flag, but why?
3. `nano code.py` shows us the inner workings of this mysterious file.
   ```Python
    import random
    import sys
    
    def str_xor(secret, key):
        #extend key to secret length
        new_key = key
        i = 0
        while len(new_key) < len(secret):
            new_key = new_key + key[i]
            i = (i + 1) % len(key)        
        return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
    
    
    flag_enc = chr(0x13) + chr(0x01) + chr(0x17) + chr(0x07) + chr(0x2c) + chr(0x3a) + chr(0x2f) + chr(0x1a) + chr(0x0d) + chr(0x53) + c>
    
    def print_flag():
      try:
        codebook = open('codebook.txt', 'r').read()
        
        password = codebook[4] + codebook[14] + codebook[13] + codebook[14] +\
                   codebook[23]+ codebook[25] + codebook[16] + codebook[0]  +\
                   codebook[25]
    
        flag = str_xor(flag_enc, password)
        print(flag)
      except FileNotFoundError:
        print('Couldn\'t find codebook.txt. Did you download that file into the same directory as this script?')
    
    def main():
      print_flag()
    
    
    
    if __name__ == "__main__":
      main()
    ```
   Breaking this down we can see that the `str_xor` function decodes a key using a secret and key arguement.
   The `print_flag` function opens the `codebook.txt` file, then it stores indexes from the text into the `password`
   variable. Finally, it calls the `str_xor` function which uses `password` and `flag_enc` (which is the encoded flag) to
   decode the correct flag.
   
## Flag

picoCTF{c0d3b00k_455157_d9aa2df2}
