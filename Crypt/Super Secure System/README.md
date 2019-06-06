```
Keith made a SUPER SECURE SYSTEM!!! He claims it is so secure as long as he doesn't reuse his key...

nc crypto.hsctf.com 8111
```

Flag là  `my super secret message` nhưng ở dạng bị mã hóa. Ở dưới phần `Enter the message you want to encrypt: ` chỉ cần nhập đúng flag ra. Ví dụng nhập định dạng cờ `hsctf`.
![](https://i.imgur.com/Peb8Dep.png)
Thì ta thấy được đoạn đầu sẽ giống nhau. -> `Brute Force`

Sử dụng script sau:
```
from pwn import *
host='crypto.hsctf.com'
port=8111
r=remote(host,port)
r.recvuntil('secret message: ')
enc=r.recvuntil('\n').strip()
flag='hsctf{'
for i in range(5,200):
        for j in range(32,128):
                r.recvuntil('want to encrypt: ')
                payload=flag+chr(j)
                r.sendline(payload)
                r.recvuntil('Encrypted: ')
                check=r.recvuntil('\n').strip()
                if check in enc:
                        flag+=chr(j)
                        print flag
                        break
        if '}' in flag:
                break
print flag
```
![](https://i.imgur.com/XxXwvQO.png)

#### Flag: `hsctf{h0w_d3d_y3u_de3cryP4_th3_s1p3R_s3cuR3_m355a9e?}`
