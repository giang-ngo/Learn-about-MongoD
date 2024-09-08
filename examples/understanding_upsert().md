dữ liệu ban đầu
![alt text](/images/examples/image-49.png)

## sử dụng để cập nhật hoặc chèn tài liệu nếu dữ liệu không tồn tại

```
db.users.updateOne(
  { name: "Maria" },
  { $set: { age: 29, hobbies: [{ title: "Good food", frequency: 3 }], isSporty: true } },
  { upsert: true }
)
```

![alt text](/images/examples/image-50.png)
