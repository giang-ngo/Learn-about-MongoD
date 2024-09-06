# MongoDB CRUD Operations Example

## 1. Xem các cơ sở dữ liệu trên máy chủ MongoDB

Sử dụng lệnh dưới đây để xem các cơ sở dữ liệu có sẵn trên máy chủ MongoDB:

```
show dbs
```

Chuyển sang cơ sở dữ liệu flights hoặc tạo một cơ sở dữ liệu mới nếu chưa tồn tại:

```
use flights
```

## 2. Thêm dữ liệu vào collection flightData

Thêm một dữ liệu mới vào collection flightData với thông tin về chuyến bay:

```
db.flightData.insertOne({
      "departureAirport": "MUC",
      "arrivalAirport": "SFO",
      "aircraft": "Airbus A380",
      "distance": 12000,
      "intercontinental": true
    })
```

![alt text](/images/examples/image.png)
Xem dữ liệu vừa thêm:

```
db.flightData.find().pretty()
```

![alt text](/images/examples/image-1.png)

## 3. Thêm nhiều dữ liệu vào flightData

Thêm nhiều dữ liệu vào collection flightData:
```
db.flightData.insertMany([{
"departureAirport": "MUC",
"arrivalAirport": "SFO",
"aircraft": "Airbus A380",
"distance": 12000,
"intercontinental": true
},
{
"departureAirport": "LHR",
"arrivalAirport": "TXL",
"aircraft": "Airbus A320",
"distance": 950,
"intercontinental": false
}])
```
![alt text](/images/examples/image-2.png)

## 4. Xóa một dữ liệu từ flightData

Xóa tài liệu có departureAirport là "TXL":

```
 db.flightData.deleteOne({"departureAirport":"TXL"})
```

![alt text](/images/examples/image-3.png)

## 5. Xóa tất cả dữ liệu trong flightData

Xóa tất cả tài liệu trong collection:

```
 db.flightData.deleteMany({})
```

### 6. Cập nhật một dữ liệu trong flightData

Cập nhật dữ liệu có distance là 1200, thêm một trường marker với giá trị là "delete":

```
db.flightData.updateOne({"distance":1200},{$set:{marker:"delete"}})
```

![alt text](/images/examples/image-4.png)

### 7. Cập nhật tất cả dữ liệu trong flightData

Thêm một trường marker với giá trị là "toDelete" cho tất cả các dữ liệu:

```
  db.flightData.updateMany({},{$set:{marker:"toDelete"}})
```

![alt text](/images/examples/image-5.png)

### 8. Xóa các dữ liệu có marker là "toDelete"

Xóa tất cả dữ liệu có trường marker với giá trị là "toDelete":

```
 db.flightData.deleteMany({marker:"toDelete"})
```

Kiểm tra lại collection sau khi thực hiện các thao tác:

```
 db.flightData.find().pretty()
```

![alt text](/images/examples/image-6.png)
