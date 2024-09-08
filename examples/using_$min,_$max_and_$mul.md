truy vấn và lấy tất cả các tài liệu từ collection users

```
db.users.find()
```

![alt text](/images/examples/image-44.png)

## Set tuổi của Manuel là 20

Toán tử $min chỉ thay đổi giá trị tuổi nếu giá trị hiện tại lớn hơn 20

```
db.users.updateOne({name:"Manuel"},{$min:{age:20}})
```

![alt text](/images/examples/image-45.png)

## Set tuổi của Chris là 35

Toán tử $max chỉ thay đổi giá trị tuổi nếu giá trị hiện tại nhỏ hơn 35

```
db.users.updateOne({name:"Chris"},{$max:{age:35}})
```

![alt text](/images/examples/image-46.png)

## Nhân tuổi của Chris lên 1.1

Lệnh này nhân giá trị tuổi hiện tại của Chris với 1.1 sử dụng toán tử $mul. Điều này tăng giá trị tuổi của Chris lên 10% so với giá trị hiện tại.

```
db.users.updateOne({name:"Chris"},{$mul:{age:1.1}})
```

![alt text](/images/examples/image-47.png)
