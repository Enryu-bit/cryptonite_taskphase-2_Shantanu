# Forbidden Paths

**Flag:** `picoCTF{7h3_p47h_70_5ucc355_26b22ab3}`

This challenge was fairly easy.<br>
At first we are told where the flag resides and then we are told to find it using a site that filters absolute paths.<br>
So after a confused first few minutes i looked at the location `/usr/share/nginx/html/` and then got the idea to use `..`.<br>
Just like i learned in pwn college `..` means the parent directory or the directory that contains our file or pwd.<br>
so i used `../../../../flag.txt` to get and guess what it worked.<br>
i used `..` four times because tha path had 4 directories in and in the last one `flag.txt` was stored.<br>


<img width="1037" alt="Screenshot 2024-11-08 at 4 16 10 PM" src="https://github.com/user-attachments/assets/224f6b73-91a4-43b5-a2a5-a34efe733126"> <br>
Didn't learn anything new but got a new perspective to bypass absolute path filter by `..`
<br>
One incorrect method was that first i put the absoulute path as i didn't pay attention to the absolute filter line.<br>

