# Timestamped Secrets - cryptography


## Approach and Solution
- read the contents of the given files
- the python program generates a ciphertext using your current timestamp by AES and sha256 hashing
- checked the message.txt file. it had a timestamp and a ciphertext
- googled ways to decrypt this, found a python script that did it for me
- hard coded the timestamp and ciphertext into the script and ran it
- i got the flag

## Flag
picoCTF{sa3S_sEc9t_f5019bd4}

## Takeaway
don't hesitate to use python scripts
