Ở đây sau khi `strings` file ảnh của đề cho thì phát hiện rất có thể đã có file nào đó ẩn trong ảnh.

![](https://i.imgur.com/nnOgK41.png)

Sau đó kiểm tra dòng cuối thì được `bobross63` rất có thể là passphrase.

Sau đó tôi sử dụng `steghide extract -sf fish.jpg` với passphrase là `bobross63` tôi có được file flag.txt.

![](https://i.imgur.com/tNtgHi7.png)

#### Flag: `hsctf{fishy_fishy_fishy_fishy_fishy_fishy_fishy123123123123}`
