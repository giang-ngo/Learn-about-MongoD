# Giải thích hai câu lệnh MongoDB liên quan đến việc cập nhật mảng hobbies dựa trên giá trị frequency:

## 1. Lệnh ban đầu:

-   Vấn đề: Lệnh này chỉ cập nhật một phần tử đầu tiên trong mảng hobbies có giá trị frequency > 2. Toán tử $ trong MongoDB chỉ áp dụng cho phần tử đầu tiên trong mảng thỏa mãn điều kiện, vì vậy nếu có nhiều phần tử trong mảng hobbies có frequency > 2, chỉ phần tử đầu tiên trong số đó được cập nhật.

-   Kết quả: Nếu có hai phần tử thỏa mãn điều kiện frequency > 2, chỉ phần tử đầu tiên được cập nhật với trường goodFrequency.

```
db.users.updateMany({"hobbies.frequency":{$gt:2}},{$set:{"hobbies.$.goodFrequency":true}})
```

![alt text](/images/examples/image-54.png)

## 2. Lệnh đã được sửa lỗi:

-   Kết quả: Lệnh này sẽ cập nhật tất cả các phần tử trong mảng hobbies có frequency > 2 với trường goodFrequency: true.

```
db.users.updateMany(
  {"hobbies.frequency": {$gt: 2}},
  {$set: {"hobbies.$[el].goodFrequency": true}},
  {arrayFilters: [{"el.frequency": {$gt: 2}}]}
)
```

![alt text](/images/examples/image-55.png)
