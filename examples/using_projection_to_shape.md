## 1. Truy vấn đầu tiên:

ruy xuất các tài liệu từ collection movies và hiển thị các trường cụ thể.

```
db.movies.find({}, {name: 1, genres: 1, runtime: 1, rating: 1}).pretty()
```

![alt text](/images/examples/image-32.png)

## 2. Truy vấn thứ hai:

Truy vấn tương tự như trên nhưng loại bỏ trường \_id.

```
 db.movies.find({},{name:1,genres:1,runtime:1,rating:1,_id:0}).pretty()
```

![alt text](/images/examples/image-33.png)

## 3. Truy vấn thứ ba:

Truy xuất các tài liệu từ collection movies và hiển thị một số trường chi tiết hơn, bao gồm trường con.

```
db.movies.find({}, {name: 1, genres: 1, runtime: 1, "rating.average": 1, "schedule.time": 1, _id: 0}).pretty()
```

![alt text](/images/examples/image-34.png)
