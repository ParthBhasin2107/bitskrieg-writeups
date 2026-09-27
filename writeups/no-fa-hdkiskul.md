# No FA - Web exploitation


## Approach
- opened users.db user sqlite3 and queried the table
- using cyberchef, found out passwords were in SHA256 hash
- decoded admin's credentials
- got to the two_fa page, asks otp
- googled what i can do with the session's cookie 
- found: flask-unsign --decode --cookie "<cookie>"
- installed flask-unsign
- got otp and logged in

## Solution
- get usernames and passwords from users table
- unhash the password of admin using cyberchef
- username: admin password: apple@123
- after reaching the two_fa page, get the value of the active cookie session
- using flask-unsign --decode --cookie '.eJwty0sKgCAQANC7zFpCkzS9TEhOIvjDsVV091y0ffAeSDUE9GDhcokQGNTRDsKz45go1Wp-GzEjDZcbWKENl2o3XC9qU5ILzeAm7MVlnMn5HAu8H0bvHGU.arbcmg.T08xsjAz74pdeyjZBm1KMDkRMcM'
- got: {'logged': 'false', 'otp_secret': '3629', 'otp_timestamp': 1790368907.6563017, 'username': 'admin'}
- used the otp to login, got the flag

## Flag
academy{n0_r4t3_n0_4uth_4cdada19}

## Takeaway
remember how to access tables for .db, remember there are tools like flask-unsign for decoding cookie session values. 
