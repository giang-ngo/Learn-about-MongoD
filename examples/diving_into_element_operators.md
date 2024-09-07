chuyển MongoDB sang cơ sở dữ liệu user.

## Chèn nhiều tài liệu vào collection users:

```
db.users.insertMany([{name:"Max",hobbies:[{title:"Sports",frequency:3},{title:"Cooking",frequency:6}],phone:865491,age:30},{name:"Manuel",hobbies:[{title:"Cooking",frequency:5},{title:"Cars",frequency:2}],phone:03232323,age:30}])

```

Lệnh trả về acknowledged: true, có nghĩa là các tài liệu đã được chèn thành công với các ID duy nhất cho từng tài liệu.
![alt text](/images/examples/image-18.png)

## Truy vấn tất cả tài liệu trong collection users

```
db.users.find().pretty()
```

![alt text](/images/examples/image-19.png)

## Truy vấn tài liệu có trường age tồn tại:

```
db.users.find({age:{$exists:true}}).pretty()
```

![alt text](/images/examples/image-20.png)

## Truy vấn tài liệu có trường age tồn tại và age > 30:

```
db.users.find({age:{$exists:true,$gt:30}}).pretty()
```

![alt text](/images/examples/image-21.png)

## Chèn tài liệu mới vào users

```
db.users.insertOne({name:"Anna",hobbies:[{title:"Sports",frequency:2},{title:"Yoga",frequency:3}],phone:"0231323",age:null})
```

## Truy vấn các tài liệu có trường age tồn tại và không phải null:

```
db.users.find({age:{$exists:true,$ne:null}}).pretty()

```

![alt text](/images/examples/image-22.png)
