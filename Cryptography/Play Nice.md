# Play Nice
---
On entering the nc mercury.picoctf.net 30568 in the webshell,We got\
Here is the alphabet: 0fkdwu6rp8zvsnlj3iytxmeh72ca9bg5o41q\
Here is the encrypted message: herfayo7oqxrz7jwxx15ie20p40u1i\
What is the plaintext message? \
this is a playfair cipher of size 6x6(we get to know this by the program playfair.py)\
so we can use a online playfair decoder like [dcode](https://www.dcode.fr/playfair-cipher)\
![image](https://github.com/Bg652/ctf/assets/144695497/11ee6f89-48db-4905-9567-066059921e0f)

where alphabet forms the grip and encrypted text message is the cipher text,which on decryption gives us this"EMF57MGC51TP693DHOEOQNT9K6GDWQLH" which is in Capitals so should be converted to lower cases,which can be done by the lower.py program which gives the output"emf57mgc51tp693dhoeoqnt9k6gdwqlh" which when entered int the websell gives us the flag
![image](https://github.com/Bg652/ctf/assets/144695497/5aeb5e39-af24-4d49-ac23-bf65a7991946)
