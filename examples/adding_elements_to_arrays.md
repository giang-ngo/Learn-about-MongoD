## 1. Truy vấn đầu tiên:

Mảng được thêm vào có tên là hoobies

```
db.users.updateOne({name:"Maria"},{$push:{hoobies:{title:"Sports",frequency:2}}})
```

![alt text](/images/examples/image-56.png)

## 2. Truy vấn thứ hai:

Thêm mảng hobbies và hai hoạt động "Good wine" và "Hiking" vào mảng hobbies, sau đó sắp xếp chúng theo tần suất giảm dần (frequency).

```
db.users.updateOne(
  { name: "Maria" },
  { $push: { hobbies: { $each: [{title: "Good wine", frequency: 1}, {title: "Hiking", frequency: 2}], $sort: {frequency: -1} } } }
)
```

![alt text](/images/examples/image-57.png)
