# Mini RSA
---

Firstly I read about RSA online what does it mean,\
![image](https://github.com/Bg652/ctf/assets/144695497/b8dfd592-8eea-491f-90e9-5ce888936554)\
The script aims to find the padding value by iterating over a range of possible values of k from 0 to 9,999. For each k, it performs a calculation to reverse the encryption operation, effectively computing m as the e-th(3rd) root of (k * N + c). This operation undoes the RSA encryption and extracts the padded message. The result m is then converted to ASCII using the int_to_ascii function. If the string "pico" is found in the ASCII representation of m, it means the correct padding has been found, and the value of k is recorded as the padding. The loop breaks when the correct padding is found.\
After getting the code to reverse it when i run the code for a range randomly I got the flag\
![image](https://github.com/Bg652/ctf/assets/144695497/4be08216-feda-4b15-a0ad-d6bb71a9ffa8)



