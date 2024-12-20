# 一、官方

## 1.官方示例程序





## 2.使用代码建立连接

~~~ java
        String connectionString = "mongodb://root:密码@dds-bp19604d5e206a541465-pub.mongodb.rds.aliyuncs.com:3717/?authSource=admin";

        // 创建MongoClientURI对象
        MongoClientURI uri = new MongoClientURI(connectionString);
        // 连接MongoDB数据库
        MongoClient mongoClient = new MongoClient(uri);

        // 获取指定数据库和集合
        MongoDatabase database = mongoClient.getDatabase("hueir");

        MongoCollection<Document> collection = database.getCollection("originalInfo");

//        //1。遍历整个集合
//        MongoCursor<Document> cursor = collection.find().iterator();
//        // 遍历结果并打印
//        while (cursor.hasNext()) {
//            Document document = cursor.next();
//            System.out.println(document.toJson());
//        }
~~~





## 3.使用模板建立连接

~~~ 
~~~

