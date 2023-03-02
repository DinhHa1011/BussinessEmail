#### Các loại mailbox 
- obox
- mbox
- maildir
- dbox 
  + sdbox
  + mdbox
- imapc
- pop3c
#### Dovecot object storage
  - Một object storage:
    + có thể được phân phối toàn cầu
    + Có thể tạo bản sao và fail-safe bằng cách lưu data object nhiều lần ở các vị trí địa lý khác nhau, do đó lỗi của một nút OSD riêng lẻ là không cần thiết
    + luôn sẵn sàng cho cho các truy vấn từ khách hàng
    + có thể vận hành theo kiểu song song => hiệu suất bị giới hạn bởi băng thông
#### mbox, Maildir, mdbox
  - tìm file mbox cho inbox trong /var/spool/mail hoặc /var/mail
  ![](https://i.imgur.com/5t9JhSa.png)
  
