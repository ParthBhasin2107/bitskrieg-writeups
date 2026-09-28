# Secure Password Database - Reverse Engineering

## Approach
I first see what file does the challenge provide us with,which in this case is  a executable so first see what its doing then move onto ghidra to understand 
what's actually happening behind the scenes.

## Solution
The challenge provides us with a 64 bit ElF exeutable file .
""""
Please set a password for your account:
1
How many bytes in length is your password?
1
You entered: 1
Your successfully stored password:
49 10
Enter your hash to access your account!
1
""""

This is the dry run to how the file works .

Now we look into the executable.
For that we use ghidra 

After using chatgpt to understand the main function and allocates 90 bytes of memory 
The program asks us for password and then instead of writing the actual byte length of our input we use 90 as that’s all the memory the program allocates for it 

Then theres a make secret function that takes some hidden bytes and xor them with 0xaa and puts the result into buffer and passes it into hash function.
now the hash function return a hash value which is independent of the password we enter .And if we enter that hash when the program asks us for hash to access our
account,we get the flag.




## Flag
academy{d0nt_trust_us3rs}

## Takeaway
ghidra is lethal for rev engineering challenges and how empty bytes can be used to store important data.
