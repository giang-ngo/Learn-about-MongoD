## Truy vấn 1:

Truy vấn này nhằm sắp xếp các tài liệu trong collection movies theo trường rating.average theo thứ tự giảm dần (từ cao đến thấp).

```
db.movies.find().sort({"rating.average": -1})
```

![alt text](/images/examples/image-27.png)

## Truy vấn 2:

Truy vấn này sắp xếp các tài liệu trong collection movies trước tiên theo trường rating.average theo thứ tự tăng dần (từ thấp đến cao), sau đó theo trường runtime theo thứ tự giảm dần (từ dài đến ngắn).

```
db.movies.find().sort({"rating.average": 1, "runtime": -1})
```

![alt text](/images/examples/image-28.png)
