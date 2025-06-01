# 安装步骤说明

## 1️⃣ 下载源码、导入项目

- 打开 **IntelliJ IDEA**
- 选择 **File > Open**，打开项目目录
- 项目为 **Maven 工程**，会自动识别并导入依赖（确保网络畅通）

## 2️⃣ 配置环境

- JDK1.8
- Maven
- MySQL 8：创建数据库`blog`

## 3️⃣ 修改配置

- 在 `src/main/resources/application-dev.yml` 中配置数据库信息，例如：

```yaml
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/blog?useSSL=false&serverTimezone=UTC&characterEncoding=utf8
    username: root
    password: app_password
```

## 4️⃣ 初始化数据库

在本地 MySQL 手动创建后台初始用户：

```sql
insert into `t_user` (`id`, `username`, `nickname`, `password`, `avatar`, `email`, `type`, `create_time`, `update_time`) 
values ('1', 'admin', '管理员', '96e79218965eb72c92a549dd5a330112', 'https://unsplash.it/100/100?image=1005', 'hh@163.com', '1', '2017-10-15 12:36:04', '2017-10-15 12:36:23');
```

## 5️⃣ 启动项目

- 直接运行主类：`com.hzx.BlogApplication.java`
- 或使用 Maven 命令：

```bash
mvn spring-boot:run
```

## 6️⃣ 登录后台

- 后台地址：http://127.0.0.1:8080/admin
- 账号密码：

```
用户名：admin
密码：111111
```