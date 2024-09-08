## Trước đó

![alt text](/images/examples/image-58.png)

## sau khi xóa

Tìm phần tử trong mảng hobbies có title: "Hiking" và xóa nó.

```
db.users.updateOne({name:"Maria"},{$pull:{hobbies:{title:"Hiking"}}})
```

![alt text](/images/examples/image-59.png)

## Trước đó

![alt text](/images/examples/image-60.png)

## sau khi xóa

Phần tử đầu tiên trong mảng hobbies của Chris sẽ bị xóa.

```
db.users.updateOne({name:"Chris"},{$pop:{hobbies:-1}})
```

![alt text](/images/examples/image-61.png)
