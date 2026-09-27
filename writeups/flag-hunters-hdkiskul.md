# File Hunters - Reverse Engineering


## Approach
- started with inspecting source code
- variable flag has the flag
- read content of variables secret_intro and song_flag_hunters, flag is in the starting part of the song.
- carefully traced reader for vulnerabilities
- checked online what re.match() does, and what parameters it takes
- found that lip is reassigned based on number following "RETURN"
- tried using \b escape sequence then following with RETURN 0 in the input to remove 'Crowd: ' from the line being updated, was unsuccessful. wasted a lot of time in trying to delete 'Crowd: '
- started checking again for ways
- noticed split(';') and thought that there were no ; in the lyrics, hence i am supposed to use that.

## Solution
- Input ";RETURN 0" for Crowd, making the line split into 2 lines 
- this makes the lip value 0 when the program continues, allowing the part of the song play where the flag is

## Flag
picoCTF{70637h3r_f0r3v3r_befbccb7}

## Takeaway
Check all lines of code properly
