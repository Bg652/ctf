# dont-use-client-side
---
After inspecting i by checking cookies ,storage and other things I got the code in the Sources having a flag but not in the order 
![image](https://github.com/Bg652/ctf/assets/144695497/decdeb7f-0c67-467f-a65b-057b0305208d) 
after concatenating it in the order given we get the flag : picoCTF{no_clients_plz_7723ce}
```python 
function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
```
