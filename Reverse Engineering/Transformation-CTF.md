# Reverse Engineering - Transformation

Xem đề tại [Transformation](https://battle.cookiearena.org/challenges/reverse-engineering/transformation)

### Tải file enc và phân tích code

![Imgur](https://i.imgur.com/LY8CUZK.png)

Theo kiến thức có sẵn thì tôi có hể phân tích và định dạng mỗi chữ trên sẽ có 16bit. Đồng thời ta được cung cấp một manh mối khác.<br>
![Imgur](https://i.imgur.com/XeX82ia.png)

Đoạn code trên rõ ràng là code được viết bằng ngôn ngữ python nếu dịch ngược thì dễ dàng chúng ta sẽ có POC như sau:

### Code POC

```python
poc = lambda x: "".join([f"{chr(ord(i)>>8 & 0xff)}{chr(ord(i)&0xff)}" for i in x])
```

Và khi chạy chúng ta dễ dàng Pass được CTF này.<br>
![Imgur](https://i.imgur.com/PosJJs6.png)

### Kết bài

Chân thành cảm ơn đàn anh [Cookie hân hoan](https://www.facebook.com/cookie.han.hoan) đã tạo ra sân chơi đầy bổ ích cho mọi người, creator [COLLECTOR](https://battle.cookiearena.org/challenges/reverse-engineering/transformation) và author [MADSTACKS](https://play.picoctf.org/practice/challenge/104?category=3&page=1)

[Go to catalogue](../README.md)
