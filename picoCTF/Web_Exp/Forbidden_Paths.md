# Forbidden Paths

**Flag:** `picoCTF{7h3_p47h_70_5ucc355_26b22ab3}`

This challenge was fairly easy.<br>
At first we are told where the flag resides and then we are told to find it using a site that filters absolute paths.<br>
So after a confused first few minutes i looked at the location `/usr/share/nginx/html/` and then got the idea to use `..`.<br>
Just like i learned in pwn college `..` means the parent directory or the directory that contains our file or pwd.<br>
so i used `../../../../flag.txt` to get and guess what it worked.<br>
i used `..` four times because tha path had 4 directories in and in the last one `flag.txt` was stored.<br>


![screenshot]()

What you learned through solving this challenge:

1. first concept
2. second concept
3. etc.

Other incorrect methods you tried:

- a
- b
- c

References

- reference 1
- reference 2
- etc.
