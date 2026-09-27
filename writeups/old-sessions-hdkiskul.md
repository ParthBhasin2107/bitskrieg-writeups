# Old Sessions - Web Exploitation


## Approach
- on opening website, registered and logged in to one account
- using the hint checked the session under cookies under Applications
- one line on the website spoke of /sessions page on the website
- put /sessions at the end of the url
- was able to access the active session ids, it had the admin's account
- copy pasted the session id into my session value in the web inspector
- got the flag

## Solution
- start off with registering and logging in to one account
- open the inspector and go to the applications tab, there go under the active cookies
- there we can see our active session
- add /sessions to the url on top, this shows us all active sessions
- there is one active admin session, replace your session id with it
- reload the page and remove the /sessions from the url
- you are now into the admin's account and have the flag right in front of you

## Flag
academy{s3t_s3ss10n_3xp1rat10n5_3b59378b}

## Takeaway
remember you can change the url to reach pages that are not visible to you normally
