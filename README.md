# 1.spring-data-jpa-example
spring data jpa操作mysql 编写 api接口 dome
# 2.注意：
Spring Boot2.x 执行schema.sql初始化数据库

## 2.1 配置schema.sql
把需要初始化的sql文件放在项目resources目录下，也可以是其他目录（需要写入绝对路径相对路径不方便部署）
如果是项目resources目录，则路径必须添加classpath:
如果有多个sql文件，可以用逗号分隔
Spring Boot2.x 必须添加 initialization-mode配置才会执行，默认为EMBEDDED也就是嵌入式数据库（H2这种），如果要在mysql下执行需要设置成为always

spring:
  datasource:
	...
    schema: classpath:scheam.sql
    initialization-mode: always
************************************************************
设置schema执行的username和password
如果sql脚本执行的数据库用户名和密码不相同，需要设置单独的属性

spring:
  datasource:
  	...
    schema: classpath:scheam.sql
    initialization-mode: always
    schema-username: root
    schema-password: 1234
    
    
data.sql的配置schema的基本相同，只需把schema改为data即可

备注:schema为建表语句，data为数据
