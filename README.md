### spring boot demo 工程说明

sping boot demo 服务CURD （嵌入式数据库H2）

- 运行环境  
java 1.8+   
window, linux , MaxOS
- 编译环境   
java 1.8+  
maven 3.25+
- 编译运行
```bash
   #进入工程目录
   cd springboot-demo
   mvn clean install -U
   java -jar target/springboot-demo-1.0-SNAPSHOT.jar

```
- 本地测试服务CURD  
curl测试记录如下，可按顺序依次执行。
```bash

 #查询测试
 curl http://localhost:8000/user
 [{"id":1,"userid":"user1","username":"lily","balance":101.00},{"id":2,"userid":"user2","username":"mic","balance":102.00},{"id":3,"userid":"user3","username":"jacy","balance":103.00},{"id":4,"userid":"user4","username":"pony","balance":104.00}]

 #查询根据用户id
 curl http://localhost:8000/user/2
 {"id":2,"userid":"user2","username":"mic","balance":102.00}
 
 #新增用户
 curl -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"userid":"user101","username":"xiaomage","balance":120.00}' http://localhost:8000/user
 
 #查询新增
 http://localhost:8000/user/5
 {"id":5,"userid":"user101","username":"xiaomage","balance":120.00}
 
 #更新新增用户
 curl -X PUT -H "Content-Type: application/json" -d '{"userid":"user101101","username":"xiaomage001","balance":130.00}' http://localhost:8000/user/5
 
 #更新新增用户
 curl -X DELETE http://localhost:8000/user/5
  

```
