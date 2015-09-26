Bài này mình thấy dễ nhất trong tất cả các bài mình làm được nên tiện thể viết WriteUp luôn.

Đề Bài

```
File được nén nhiều lớp. Mật khẩu giải nén chính là tên của file.

Ví dụ: ở lớp đầu tiên, tên file bên trong là say_my_name. Do đó, mật khẩu giải nén sẽ là say_my_name.

Lớp cuối cùng chính là cờ.

Nếu cờ không có dạng matesctf{...}, bạn hãy thêm nó vào cờ
Link: [what_am_i](http://files.matesctf.org/binary/what_am_i_bd6788043be8300f6f5ed298be42ed91)
```

Đề bài gợi ý là mật khẩu giải nén sẽ là tên file bên trong nên mình phải viết 1 chương trình để làm sao lấy được tên bên trong của file nén và điền vào để giải nén

Xem header thì thấy file có định dạng nén là 7z

Lúc đầu mình nghĩ sẽ viết bằng python nhưng tìm mãi không biết sử dụng thư viện py7zlib nên dùng bash shell

Sử dụng 7z trên linux dùng tham số l để xem thông tin file

<img src="http://i.imgur.com/nYAN5KH.png">


Như vậy có thể lấy được tên file bên trong file 7z.

Giờ chuyển đống kia sang array rồi tìm xem tên file bên trong nằm ở vị trí bao nhiêu rồi nhập vào thôi.

Đây là code của mình. Rất ngắn

```
#!/bin/bash
file="say_my_name.7z"
while :
do
extract=`7z l $file`
arr=($extract)
passwd=${arr[58]}
7z e $file -p$passwd
file=${arr[58]}
done

```

Cho chạy chương trình khi nào báo lỗi tức đã giải nén được hết..

Vào thư mục tìm flag thôi

Đây rồi 
<img src="http://i.imgur.com/V8f5vyL.png">

Mở lên và submit. Đã có 200 points

<img src="http://i.imgur.com/FM3R4Zd.png">


