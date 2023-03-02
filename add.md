#### guid (Globally Unique Identifier)
  - Định danh duy nhất trên toàn cầu

#### doveadm fetch
  - Dùng để fetch nội dung và metadata của mess => được sử dụng cho script và debugging
  - Tìm guid: 
  
    ``` doveadm search -u demo@vtaedha.site mailbox inbox ```
    
   ![](https://i.imgur.com/OVTuEXS.png)
   
   - Lấy mail từ người dùng với guid là d05224362b79fc63cd260700701ce355 với uid là 1,3
    ![](https://i.imgur.com/aR81GJ4.png)
        + date.sent: lấy ngày và giờ gửi
        + body: lấy body mess
        + text: lấy toàn bộ thông điệp
        + mailbox: tên mailbox => nơi lưu trữ tin nhắn
        + mailbox-guid: tên mailbox + guid
#### doveadm-move
   - di chuyển tin nhắn của test1@vtaedha.site trong tháng 2 năm 2023 từ Inbox của test1 sang archive
    ![](https://i.imgur.com/0RmUtkG.png)
#### doveadm-deduplicate
  - expunge các tin nhắn trùng lặp
  
  ```doveadm -f table fetch -u demo@vtaedha.site 'guid uid' mailbox inbox```
  ```deveadm deduplicate -u demo@vtaedha.site mailbox inbox```
  ```doveadm -f table fetch -u demo@vtaedha.site 'guid uid' mailbox inbox ```
  ![](https://i.imgur.com/k5odAxo.png)
  
#### doveadm-expunge 
  - expunge mess match given search query
  - expunge mess từ inbox mailbox được lưu 1 ngày trước
  ```doveadm expunge -u test1@vtaedha.site mailbox inbox savedbefore 2d```
  ![](https://i.imgur.com/XkTzArN.png)
  
#### doveadm flags add/remove/replace 
  - add, remove hoặc replace flag của mess
  ```doveadm fetch -u demo@vtaedha.site 'uid flags' mailbox inbox uid 1```
  ![](https://i.imgur.com/OJMLpVv.png)
#### doveadm mailbox
  - Dòng lệnh liên quan đến xử lý hộp thư
  - list folder của người dùng
    - list mailbox đã đăng kí, bắt đầu với dovecot của demo
  ```doveadm mailbox list -s -u demo@vtaedha.site dovecot```
    - xem trạng thái hộp thư mailbox dovecot của demo
  ```doveadm -f table mailbox status -u demo@vtaedha.site "messages vsize" dovecot```
  ![](https://i.imgur.com/0tZaE5j.png)
  ```doveadm -f table mailbox status -u demo@vtaedha.site all INBOX```
  ![](https://i.imgur.com/LbcLbqA.png)
