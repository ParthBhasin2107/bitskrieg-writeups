# StegoRSA-Cryptography

## Approach
The description mention RSA ,which means it’s a asymmetric cryptography algorithm problem .
To solve a RSA  ctf,we have to look for the key.
Hint 1 wants us to look into the meta data of the files this challenge gives us so we will start from there and see where it takes us .

## Solution
The hint want us to look at meta data so who are we to say no to it ,we will look at meta data of both the files.
Flag.enc didn't give us anything useful ,just says data ,probably cause its encrypted ,our machine can't detect which kind of file this is but on the other hand ,
looking at the metadata of the other file ,we see there's a comment which has a very large text ,which looks like hex,and the hint also mentions hex so we first 
try to convert this to a readable english format .
Converting it we can see that it’s the RSA private key as it says that at the start of the text .
So now we have the key ,we just have to use that to decrypt flag.enc(hopefully).Doing that gave us the flag .

#Commands used
To decrypt the key -> echo 'HEX' | xxd -r -p > key.txt
To use the key to get the flag-> openssl pkeyutl -decrypt -inkey key.txt -in flag.enc -out flag.txt


## Flag
picoCTF{rs4_k3y_1n_1mg_4eedd678}


## Takeaway
To remember RSA functioning,how its key looks and the commands to use the keys to encrypt and decrypt the text.
