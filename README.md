开机命令
>mongod --storageEngine=mmapv1 --dbpath d:/mongo
mongod //开机命令
--storageEngine=mmapv1  //修改数据库类型为mmapv1 针对win7系统 32位 只能用这个类型
--dbpath d:/mongo 新建数据库的地址 会生成一系列的文件

再开一个cmd (上面那个不能关)
输入
mongo
会连接打开的数据库

任务：新建一个dbname的数据库 添加student集合 往student里添加数据

show dbs 列出所有数据库
use dbname  //新建或使用数据库 use一个不存在的 就是新建，但是 如果是创建 必须往这个数据库的集合里插入一个数据 才能把这个数据库创建成功
db  //查看当前在哪个数据库里  显示dbname

show collections //查看有哪些集合

往当前的dbname数据库里加集合 往集合里添加数据 （如果student不存在 就会创建一个student集合 同时链式操作 添加数据）
db.student.insert({'name':'abeng','age':12})

student就是所谓的集合 存放着很多json数据

db.student.find() //查看这个student集合里面所有的数据

查找一条数据
db.student.find({'name':'abeng'})//查找name 是abeng的数据

可视化工具：
mongovue

删除数据库
db  //查看当前数据库
db.dropDatabase();//删除当前数据库


导入数据库
另外开一个cmd
mogoimport --db dbname --collection collectionmame --drop --file filepathandname
--db dbname //往哪个数据库里导入
--collection collectionmame //往哪个集合里导入
--drop //把原来的集合清空 可选
--file filepathandname //可以用sublime创建一个json数据 填写完整的这个json文件的路径 即可
 json的格式是  
 {}
 {}
 {}
 ---
 
 
