# Secure Password Database - Reverse Engineering


## Approach
- started with file system.out, noticed not stripped
- then strings system.out, didn't see flag but noticed flag.txt as a string
- then opened ghidra to read the code
- found function called make_secret() which was getting the value vs which there was a check and based on it the flag.txt file would open
- read the block of code in make_secret(), found a for loop XORing some values
- double clicked and checked what was being XORed. googled what to check for. Got bunch of Hexadecimal values that were being XORed
- put this into cyberchef, from hex and XOR. got iUbh81!j*hn! as output.
- that must be the required password. 
- saw make_secret() calling hash(). googled what to do to get my password hashed.
- found hashing algorithm name djb2 hash
- hashed the password to get -3209081493549540382
- input everything, got the flag.

## Solution
- check for stripped/not stripped. on checking file is not stripped, get into ghidra
-make ghidra decompile the .out into code and check for the code block that will give us the flag
- in this case it was inside an if condition that depended on a weird function named make_secret
- check the structure of make_secret, notice that the function is creating the password that is required for printing the flag using an already creating and XORing it.
- use cyberchef to obtain the password
- make_secret then hashes this password using a function hash
- by inspecting the code, we see hash is using djb2 hash algorithm
- obtain the hash of the password using the same logic as used in the function
- input the password, bytes in password, hash to finally get the flag printed.

## Flag
picoCTF{d0nt_trust_us3rs}

## Takeaway
use google occasionally to check algorithm names to decode and also for help with software
