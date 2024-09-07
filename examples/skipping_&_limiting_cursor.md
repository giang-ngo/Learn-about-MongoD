## Truy vấn 1:

Truy vấn này truy xuất các tài liệu từ collection movies, sắp xếp chúng theo điểm đánh giá trung bình và thời lượng, rồi bỏ qua (skip) 239 tài liệu đầu tiên.

```
db.movies.find().sort({"rating.average": 1, "runtime": -1}).skip(239)
```

![alt text](/images/examples/image-29.png)

## Truy vấn 2:

Truy vấn này tương tự như truy vấn trước, nhưng có thêm giới hạn số lượng tài liệu truy xuất sau khi bỏ qua một số lượng tài liệu nhất định.

```
db.movies.find().sort({"rating.average": 1, "runtime": -1}).sort({"rating.average": 1}).skip(100).limit(2)
```

![alt text](/images/examples/image-30.png)

## Truy vấn 3:

Truy vấn này giống hệt truy vấn thứ hai nhưng với mục đích đếm số lượng tài liệu sau khi sắp xếp và giới hạn.

```
db.movies.find().sort({"rating.average": 1, "runtime": -1}).sort({"rating.average": 1}).skip(100).limit(2).count()
```

![alt text](/images/examples/image-31.png)
