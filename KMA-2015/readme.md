
Hôm nay KMA có tổ chức CTF và mình cũng tham gia. Nói chung hôm nay hơi phế. Chỉ làm được 2 bài Forensic ko giúp cho đội lên rank được. Làm được nên viết writeup luôn chờ các writeup khác vậy.

#Forensic 150

Đề bài cho 2 file bin và không nói gì thêm. 

Download về dùng command file và binwalk để kiểm tra

<img src="http://i.imgur.com/I02s7gE.png">

Nhận định đây là file Squashfs file system. Mình cũng ko biết nó là gì nhưng khi dùng hex để xem thì mới biết đó là một firmware của 1 con router.

Vậy thì cứ extract ra xem có gì ko? Vẫn dùng lệnh binwalk để extract

<img src="http://i.imgur.com/LT68lPg.png">

<img src="http://i.imgur.com/gLzrj25.png">

Kiểm tra 2 thư mục thấy giống nhau hoàn toàn

Vậy thì compare xem nó có điểm gì khác. Mình có search được 1 script của python là binwally.py vậy dùng cái này để compare thôi

Kết quả:

<img src="http://i.imgur.com/MMIEjT7.png">

99% giống nhau.

Dùng tiếp binwally

<img src="http://i.imgur.com/T5xb2M5.png">

Rồi. đây là cái shell hacker upload lên


Truy cập vào để xem thôi

<img src="http://i.imgur.com/ihXMRXS.png">


