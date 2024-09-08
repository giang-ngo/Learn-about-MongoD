## 1. Tìm tài liệu có sở thích là "Sports" và tần suất (frequency) ≥ 3

-   $and: Toán tử logic để kết hợp các điều kiện:
-   {"hobbies.title": "Sports"}: Điều kiện đầu tiên, tìm kiếm tài liệu trong đó trường hobbies.title có giá trị là "Sports".
-   {"hobbies.frequency": { $gte: 3 }}: Điều kiện thứ hai, tìm kiếm tài liệu có trường hobbies.frequency lớn hơn hoặc bằng 3.

```
db.users.find({$and:[{"hobbies.title":"Sports"},{"hobbies.frequency":{$gte:3}}]})
```

![alt text](/images/examples/image-51.png)

## 2. Tìm tài liệu có phần tử trong mảng hobbies khớp với điều kiện

Toán tử $elemMatch đảm bảo rằng cả hai điều kiện (title và frequency) đều áp dụng cho cùng một phần tử trong mảng hobbies.

```
db.users.find({hobbies:{$elemMatch:{title:"Sports",frequency:{$gte:3}}}})
```

![alt text](/images/examples/image-52.png)

## 3. Cập nhật tài liệu, thêm trường highFrequency: true cho sở thích "Sports" có tần suất ≥ 3

Kết quả là mọi tài liệu có sở thích "Sports" với tần suất ≥ 3 sẽ có thêm một trường highFrequency: true cho phần tử sở thích đó.

```
db.users.updateMany(
  { hobbies: { $elemMatch: { title: "Sports", frequency: { $gte: 3 } } } },
  { $set: { "hobbies.$.highFrequency": true } }
)
```

![alt text](/images/examples/image-53.png)
