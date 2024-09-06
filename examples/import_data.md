## Import dữ liệu vào MongoDB

Bạn sử dụng lệnh mongoimport để nhập dữ liệu từ tệp JSON tv-shows.json vào MongoDB.

```
mongoimport tv-shows.json -d movieData -c movies --jsonArray --drop
```

![alt text](/examples/image-7.png)

## Truy cập MongoDB bằng mongosh

sử dụng lệnh mongosh để mở MongoDB shell

```
mongosh
```

## Xem các cơ sở dữ liệu

```
show dbs
```

![alt text](/examples/image-8.png)

## Xem dữ liệu trong collection movies

(kiểm tra) dữ liệu trong collection movies

```
use movieData      # Chuyển vào cơ sở dữ liệu movieData
db.movies.find()   # Hiển thị dữ liệu trong collection movies
```

![alt text](/examples/image-9.png)
