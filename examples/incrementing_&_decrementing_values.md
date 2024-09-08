Manuel trước đó là 30 tuổi

```
 db.users.find()
```

![alt text](/images/examples/image-39.png)

## 1. Tăng tuổi thêm 2:

```
db.users.updateOne({name: "Manuel"}, {$inc: {age: 2}})
```

Trường age của Manuel sẽ tăng thêm 2 tuổi. Nếu trước đó anh ta 30 tuổi, sau lệnh này tuổi sẽ trở thành 32.
![alt text](/images/examples/image-40.png)

## 2. Giảm tuổi 4:

```
db.users.updateOne({name: "Manuel"}, {$inc: {age: -4}})
```

Sau khi tuổi của Manuel là 32, lệnh này sẽ giảm tuổi xuống 28.
![alt text](/images/examples/image-41.png)

## 3. Giảm tuổi và đặt trường mới isSporty:

```
db.users.updateOne({name: "Manuel"}, {$inc: {age: -4}, $set: {isSporty: false}})
```

Sau khi giảm tuổi từ 28 xuống 24, MongoDB sẽ thêm trường mới isSporty với giá trị false vào tài liệu của Manuel.
![alt text](/images/examples/image-42.png)

## 4. Giảm tuổi và đồng thời đặt lại giá trị tuổi (age) thành 30 (gây ra lỗi):

```
db.users.updateOne({name:"Manuel"},{$inc:{age:-4},$set:{age:30}})
```

Đây là hai hành động mâu thuẫn cùng áp dụng trên trường age trong cùng một lần cập nhật. MongoDB không thể thực hiện cả hai hành động (giảm giá trị rồi lại đặt giá trị mới cùng một lúc) và do đó, gây ra lỗi.
![alt text](/images/examples/image-43.png)
