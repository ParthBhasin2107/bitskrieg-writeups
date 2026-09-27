# StegoRSA - cryptography


## Approach
- downloaded files and opened the image to see what it is
- read hint about metadata
- looked up on how to get metadata of a .jpg in the terminal, found exiftool
- installed it and used it. found key in the comments of the metadata of image.jpg
- looked up what file type .enc is exactly
- using the hint, googled how to convert hex to file. ended up using a website to do it, obtained a .dat file.
- ran: file privatekey.dat, got privatekey.dat: OpenSSH private key (no password)
- read CTF Primer and understood what RSA is. Still confused what to do with the .enc file
- checked resources that were given during induction for help
- had to google what to do to decrypt the .enc using the key
- found command: openssl pkeyutl -decrypt -inkey private.key -in file.enc -out decrypted_output.txt
- got the flag.

## Solution
- use tool like exiftool to get metadata of the image
- comments contains private key in hex text, convert it to a file (.dat in my case)
- use a tool like openssl to decrypt the RSA encrypted flag.enc file using the private key file
- you have gotten the flag

## Flag
picoCTF{rs4_k3y_1n_1mg_0a64c2f9}

## Takeaway
Learn methods to decrypt
