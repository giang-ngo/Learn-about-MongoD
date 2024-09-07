## 1. Truy vấn đầu tiên:

Truy vấn này tìm các bộ phim thuộc thể loại "Drama" và chỉ trả về một phần tử của mảng genres khớp với giá trị "Drama".

```
db.movies.find({genres:"Drama"},{"genres.$":1}).pretty()
```

![alt text](/images/examples/image-35.png)

## 2. Truy vấn thứ hai:

Truy vấn này tìm các bộ phim thuộc cả hai thể loại "Drama" và "Horror", nhưng chỉ trả về phần tử đầu tiên trong mảng genres khớp với giá trị trong điều kiện.

```
 db.movies.find({genres:{$all:["Drama","Horror"]}},{"genres.$":1}).pretty()
```

![alt text](/images/examples/image-36.png)

## 3. Truy vấn thứ ba:

Truy vấn này tìm các bộ phim thuộc thể loại "Drama" và kiểm tra xem trong mảng genres có phần tử nào khớp với "Horror" hay không.

```
db.movies.find({genres:"Drama"},{genres:{$elemMatch:{$eq:"Horror"}}}).pretty()
```

![alt text](/images/examples/image-37.png)

## 4. Truy vấn thứ tư:

Nó sẽ trả về danh sách các phim có điểm đánh giá trung bình cao hơn 9 và thuộc thể loại kinh dị ("Horror").

```
db.movies.find({genres:"Drama"},{genres:{$elemMatch:{$eq:"Horror"}}}).pretty()
```

![alt text](/images/examples/image-38.png)
