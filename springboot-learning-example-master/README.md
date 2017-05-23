# springboot-learning-example
spring boot 实践学习案例，是 spring boot 初学者及核心技术巩固的最佳实践。

项目包含：
  springboot-helloworld
  springboot-propertie
  springboot-restful     Spring Boot 之 RESRful API 权限控制
  springboot-freemarker  Spring Boot 集成 FreeMarker 详解案例
  springboot-validation-over-json Spring Boot HTTP over JSON 的错误码异常处理
  springboot-mybatis
  springboot-mybatis-annotation
  springboot-mybatis-mutil-datasource

#### d. 『 基础 – 数据缓存篇 』
- springboot-mybatis-redis <br>

#### e. 『 其他篇 』
- springboot-elasticsearch <br>
 [《Spring Boot 整合 Elasticsearch，实现 function score query 权重分查询》]
- springboot-dubbo-server <br>
- springboot-dubbo-client <br>
Dubbo 服务提供者工程和 Dubbo 服务消费者工程 <br>
 [《Springboot 整合 Dubbo/ZooKeeper 详解 SOA 案例》]
 [《Spring Boot 中如何使用 Dubbo Activate 扩展点》]


## 二、项目 Quick Start 快速开发指南
#### a. 基本环境配置
在 MySQL 中，创建数据库 springbootdb：
````
CREATE DATABASE springbootdb;
````
创建表 city 城市 (因为我喜欢徒步)
````
DROP TABLE IF EXISTS  `city`;
CREATE TABLE `city` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT COMMENT '城市编号',
  `province_id` int(10) unsigned  NOT NULL COMMENT '省份编号',
  `city_name` varchar(25) DEFAULT NULL COMMENT '城市名称',
  `description` varchar(25) DEFAULT NULL COMMENT '描述',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
````
插入基础数据
````
INSERT city VALUES (1 ,1,'温岭市','BYSocket 的家在温岭。');
````
 <br>
### 《 springboot-mybatis 工程 Quick Start 》
首先 check 基本环境配置完成，创建好数据库和表。

#### 1. 修改数据库配置
配置文件地址：springboot-mybatis/src/main/resources/application.properties
修改相应的数据源配置，比如账号、密码等

#### 2. 编译工程
在项目根目录 `springboot-learning-example`，运行 maven 指令：
````
mvn clean install
````
#### 3. 运行工程
右键运行工程包中 `org.spring.springboot.Application` Spring Boot 应用启动类的 main 函数，然后在浏览器访问：
`````
http://localhost:8080/api/city?cityName=温岭市
`````
可以看到返回的 JSON 结果：
````
{
    "id": 1,
    "provinceId": 1,
    "cityName": "温岭市",
    "description": "我的家在温岭。"
}
````
最后，<br/>

推荐
 [《Spring Boot教程与Spring Cloud教程》](https://git.oschina.net/didispace/SpringBoot-Learning "Spring Boot教程与Spring Cloud教程")<br>
