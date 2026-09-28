# Timestamped Secrets - Reverse Engineering


## Approach
The challenge provided us with one text file and one python executable.By the name of the file ,looks like its the code to how the flag was encrypted and the
description clearly tells us that the time at which the file was encrypted can be used to decrypt and the text file gives us the time for that so lets now we have
understand how its being used by understanding encryption.py.

## Solution
We got two files with the problem,one is a text file and other is a file containing the redacted code which is used in encryptioin.
The text file had the timestamp to when the text was encrpted and the encrypted ciphertext.
This has the function used for encryption
After understanding it we know that the function uses timestamp to create  the key for the AES encryption 
So we just have to reverse it 
We create another script for decryption and use the timestamp given in the txt file as it is the time when the encrption was done .
But there was a problem in running the code as I was not able to download some libraries so I had to use docker for that .
Created a docker container and image and put then ran decryption code inside it and got the flag.

## Flag
academy{sa3S_sEc9t_f9ccd007}

## Takeaway
Always try to understand how the encryption is being done and check whether its symmetric or asymmetric.
