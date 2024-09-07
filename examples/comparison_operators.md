    [Xem thêm tại đây](https://www.mongodb.com/docs/manual/reference/operator/query/)

trường **runtime** với các toán tử so sánh khác nhau:

## 1. Toán tử bằng nhau ($eq)

```
 db.movies.find({ runtime: {$eq:60}})
```

![alt text](/images/examples/image-10.png)

## 2. Toán tử không bằng ($ne)

```
db.movies.find({ runtime: {$ne:60}})
```

![alt text](/images/examples/image-11.png)

## 3. Toán tử bé hơn ($lt)

```
db.movies.find({ runtime: {$lt:40}})
```

![alt text](/images/examples/image-12.png)

## 4. Toán tử bé hơn hoặc bằng ($lte)

```
 db.movies.find({ runtime: {$lte:40}})
```

## 5. Toán tử lớn hơn ($gt)

```
db.movies.find({ runtime: {$gt:40}})
```

![alt text](/images/examples/image-13.png)

## 6. Toán tử lớn hơn hoặc bằng ($gte)

```
db.movies.find({ runtime: {$gte:42}})
```

![alt text](/images/examples/image-14.png)
