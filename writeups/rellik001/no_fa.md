# NO FA - Web Exploitation


## Approach
The challenge hints that we have to use the leaked data and it also gave us a sql databse file ,so first lets see whats inside it .

## Solution
The challenge provides us with two files ,one of them is the users database and the other is a python script.
From the database we can get the admins username and password.The password is in hash so we go to crackstation to get the password in 
readable english from the hash.
It was sha-256  and we got the admin's password which is "apple@123".

Now to understand the python code I used chat gpt and found that our otp is places into the flask session and then stored in the client side session in a cookie.
But we are not able to download flash unsign as kali blocks it so we use venv and then cmd
1)Python -m install flask-unsign 
 This installs the flask-unsign
2)flask-unsign --decode --cookie '.eJwty0sKgCAQANC7zFrC6Wd2mZCcRPCHTqvo7rlo--A9ELJzZGGHy4RGICBzORqdlbjjhhp_Yx-psYkFdlRazhOOqxyUVKgWAXejmkykfoyNPsH7AStbHCI.
arfQHA.Gru-S8Mymh2gDk02b9kLmLbb6Nk'
This gives us the otp and then we can use that to get the flag.(obv use your own session cookie ,exact this command wont work.)

## Flag
academy{n0_r4t3_n0_4uth_4cdada19}

## Takeaway
Learn flask and its commands,and burp suite tools.And one more thing,how one can try to convert sha 256 to readable english bu brute force ,wont work always 
but worth a try.
