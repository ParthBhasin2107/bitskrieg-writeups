#Flag Hunters - Reverse Engineering


#Approach
This being a reverese engineering problem and them giving us a code ,the first thought is to understand the code what its doing and how,the description also hints that 
there is a paragraph of something which is not printing right now and we have to find a way to print it.

## Solution
The program provides us with the source code.
Theres the written song and understanding the code we can know how does the code iterates over the song .

Our flag  is in the secret intro verse which is at the start of the song but the song starts from verse1 ,so we have to somehow print that verse and it prints the line according to the index in lip

We see that it takes a input and doesn't check it for malicious code 
So when it asks for input we do 

HI;RETURN 0

So the code works such that it first creates a list for ["HI";"RETURN 0"]
Then it takes the one with index 1 and split it and the integer part is assigned to lip 
As now we sent lip variable to start it would print out flag verse and we get the flag .


## Flag
academy{70637h3r_f0r3v3r_577e16ad}


## Takeaway
Learn to understand already working code in different languages.
