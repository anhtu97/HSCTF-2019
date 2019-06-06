Ở đây chúng ta có 2 ảnh là `koala.png` và `koala2.png`.
Ở đây tôi sử dụng `zsteg`.
Đối với ảnh `koala.png`. Tôi phát hiện được trong ảnh có chứa một liên kết đến `https://www.mediafire.com/file/0n67qsooy8hcy30/hmmm.txt/fileA`

![](https://i.imgur.com/9kbUZNV.png)

Đối với ảnh `koala2.png`.Tôi có được `passkey: whatdowehavehereJo`

![](https://i.imgur.com/M9CClEq.png)

Sau đó tôi đến `https://www.mediafire.com/file/0n67qsooy8hcy30/hmmm.txt/fileA` thì có được một file `hmmm.txt`. Kiểm tra thì đã bị mã hóa `GPG symmetrically encrypted data (AES cipher)`

![](https://i.imgur.com/iGbzaMC.png)

Admin có thông báo `Double Trouble has a small issue; take two characters off the end of the key if you're having problems.` -> passkey là: `whatdowehavehere` 

Tôi sử dụng gpg với passkey để decrypt và có được flag.

![](https://i.imgur.com/z9Bh3vb.png)

#### Flag: `hsctf{koalasarethecutestaren'tthey?}`
