## đổi tên trường age thành totalAge

```
db.users.updateMany({}, {$rename: {age: "totalAge"}})
```

![alt text](/images/examples/image-48.png)
