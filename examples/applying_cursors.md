[Tham khảo thêm tại đây](https://www.mongodb.com/docs/manual/tutorial/iterate-a-cursor/)

## Số lượng tài liệu trong collection movies

```
db.movies.find().count()
```

![alt text](/images/examples/image-23.png)

## Tạo con trỏ để duyệt tài liệu trong collection

```
const dataCursor=db.movies.find()
```

## Truy xuất tài liệu tiếp theo bằng con trỏ

```
dataCursor.next()
```

![alt text](/images/examples/image-24.png)

## Kiểm tra xem con trỏ có tài liệu tiếp theo không

```
 dataCursor.hasNext()
```

![alt text](/images/examples/image-25.png)

## Duyệt qua và in tất cả tài liệu trong con trỏ

```
dataCursor.forEach(doc => { printjson(doc); })
```

![alt text](/images/examples/image-26.png)
