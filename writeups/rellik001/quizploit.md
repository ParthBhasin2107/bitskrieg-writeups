# Quizploit - Binary Exploitation 


## Approach
The challenge description just hints to solve the the quiz and among the files they provided us with ,one won't run in my machine and the other is a c code so i
move on to creating an instance and doing nc resultin in starting a quiz...so quiz time it iz.

## Solution
The challenge provide us with a  "C" text file and a  executable file 
In the  c code there's clearly written 
"
This is not the challenge, just a template to answer the questions.
To get the flag, answer all the questions.
There are no bugs in the quiz.
There are 0xD questions in total.
"
So this and description combined hints that we maybe just have to solve some king of quiz

Launching the instance and using nc to that it actually start a quiz
1)For first question we just had to use file command to know which bit executable file this is 
2)second we find that the program uses dynamic linking 
3)Then the binary is not stripped
4)then it asks us to look at vuln and find the buffer length which is 0x15
5)The hint helps us to find the next answer which is 0x90.
6)Then it simply asks if theres a possibility of buffer vuln which there obv is .
7)then it asks for the function that causes the buffer overflow which is fgets.
8)Then the function which is not called at any point of time which is win function.
9)Then it asks for the name of the attack--Buffer Overflow
10)Then it asks for how many bytes of overflow is possible ,the hint helps us in this .But the subtraction is different but we get 0x7b after using gpt for that .
Cause we had to first convert them to integers then subtract then convert back .
11)Then it asks for which protection is enabled ,it also gives us the cmd required to check that ,we find that only NX is enabled.
12)For this I didn’t know the answer but it gives options and unlimited attemps so we brute force …hehe…..and finds that ROP is the one that sticks.
13)Then is asks us to find the address of win function using gdb 
Address = 0x401176

And we get the flag!

##Flag
academy{my_bIn@4y_3xpl0it_fL@g_95fef02a}

## Takeaway
Learned about different things it asked in quiz which i never knew like the protections a file have and how to subtract hex numbers .
