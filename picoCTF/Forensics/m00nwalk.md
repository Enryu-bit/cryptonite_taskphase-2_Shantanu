
# mOOnwalk

**Flag:** `picoCTF{beep_boop_im_in_space}`

when i listened to the audio file. it didn't give me much of a hint. Then when i looked at the hint of how images were sent from the space i got to know about [SSTV](https://en.wikipedia.org/wiki/Slow-scan_television).<br>
To use SSTV i used this [link](https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04).<br>
<br>
What you learned through solving this challenge:
That images can be transferred in the form of sounds aswell.<br>
Learnt to use qsstv and loading modules and all.<br>
The major hint in this challenge was the CMU mascot. Its name was **Scotty** which made me choose the mode for qsstv as scottie 1.<br>
Making qsstv run on parrot os was a whole another task i had to use a different software to trap audio from my sound card then make qsstv catch that audio from the null channel.<br>
The final image had the flag written on it.<br>
https://github.com/user-attachments/assets/76946e1a-2900-4180-ad11-e5debaffa9e6

References.<br>
https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04
