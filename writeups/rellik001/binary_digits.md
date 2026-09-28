# Binary Digits - Forensics


## Approach
The challenge gave us a file that contains onoly binary numbers and the description hints that it's not just random noise and actually means something so first 
i would try to convert it to readable english.

## Solution
So if we convert them all at once using cyberchef,it would just give us gibberish .So after reading upon things i found i had to seperate them in 8 bits(1byte) and
then convert from binary using cyberchef.That gave us something that start with ff d8,thats how jpeg image file starts so we know this is a image converted to binary.
So now I will first try to reverse this.For that we can use any binary to image converter .I used " https://capitalizemytitle.com/binary-to-image-converter/ ".
And in the image there was the flag staring at me so ....chao amigos.


## Flag
academy{h1dd3n_1n_th3_b1n4ry_1b150ee9}

## Takeaway
Learn about different formats,how a file starts in hex view of a specific format .Keep an eye out for these things .
