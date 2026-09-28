# Old Sessions- Web Exploitation
Difficulty = Easy

Description=
Proper session timeout controls are critical for securing user accounts. If a user logs in on a public or shared computer but doesn’t 
explicitly log out (instead simply closing the browser tab), and session expiration dates are misconfigured, the session may remain active indefinitely.
This then allows an attacker using the same browser later to access the user’s account without needing credentials, exploiting the fact that 
sessions never expire and remain authenticated.

#Add on description after launching the instance=

Your friend tells you to check out a new social media platform he built a few years ago. Although its still under development, he
said the site is almost complete. He also mentioned that he hates constantly logging into sites, and so has made his page that 
'once you login, you never have to log-out again'!
Browse here, and find the flag!


HINT1--Do you know how to use the web inspector?
HINT2--Where are cookies stored?



## Approach
Reading the description looks like it is aimed towards making us learn the importance of expiring the session id after a certain time by
showing how someone can use this vulnerability.

## Solution
Clicking on the link we get after launching instance takes us to a site which asks for username and password to login or register .
As currently we don’t have anything ,only thing to try is to register a new user 
So first we register a new username and password
Then we login using those credentials 

After loggin in we see something suspicious
One of the user says
"
Hey I found a strange page at /sessions
"
As this challenge clearly hints towards session id ,/sessions rings the bell in our head.
Appending / sessions to our current URL takes us to a new page where we can see our current session id and what interesting is that there's another session id for admin,as the session id ones created,it never expires ,clearly told  to us in the description ,so we can use that session id to login as admin.
Then we go to the cookies section in the developer tool ,where we can see and change our current session id ,after changing we just have to go back to the page we were at before appending /session to out url and bam we get the flag right there straight looking at me .


## Flag
Flag : picoCTF{s3t_s3ss10n_3xp1rat10n5_efbf6d5f}

## Takeaway
To check about session ids,are they expiring or not ,can we use them to exploit or not in web challenges.
