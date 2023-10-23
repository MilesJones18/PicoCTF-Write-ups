# Static ain't always noise

Points: 20
Category: General Skills

## Overview

>Can you look at the data in this binary: [static?](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static) This [BASH](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh)
script might help!

## Hints

None

## Approach

1. First I wget both the static file and the bash script.

2. Reading the bash script with nano gave me a quick overview of what it does and how to run it.

3. Running `bash ltdis.sh static` outputted four files, `-D.ltdis.x86_64.txt`, `-j.ltdis.x86_64.txt`, `static.ltdis.strings.txt` and `static.ltdis.x86_64.txt`.
   Reading most of these didn't really give me anything I needed except for `static.ltdis.strings.txt`. This gave me a list of all human readable text
   in the static file. Inside here was the flag.

## Flag
picoCTF{d15a5m_t34s3r_f5aeda17}
