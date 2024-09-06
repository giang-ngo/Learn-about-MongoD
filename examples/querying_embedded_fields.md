lệnh truy vấn MongoDB mà bạn đã sử dụng để tìm kiếm trong collection movies:

## 1. Tìm kiếm dựa trên giá trị trong một trường lồng nhau ($gt cho giá trị lớn hơn)

```
 db.movies.findOne({"rating.average":{$gt:7}})
```

Tìm một bộ phim có đánh giá trung bình (rating.average) lớn hơn 7.
![alt text](image-15.png)

## 2. Tìm kiếm dựa trên giá trị trong mảng (so khớp với phần tử trong mảng)

```
db.movies.findOne({"genres":"Drama"})
```

Tìm một bộ phim mà thể loại (genres) có chứa giá trị "Drama".
![alt text](image-16.png)

## 3. Tìm kiếm dựa trên giá trị chính xác của mảng

```
db.movies.findOne({"genres":["Drama"]})
```

Tìm một bộ phim mà mảng thể loại (genres) chỉ chứa duy nhất giá trị "Drama".
![alt text](image-17.png)
