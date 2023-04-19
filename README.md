# DỰ ÁN THỰC TẬP Fastfood
Video demo: [https://youtu.be/oMjQpy_Knds](https://youtu.be/oMjQpy_Knds)

## POINT TO PROJECT SOURCE
```
cd ..[project location]/Fastfood/source
```
`Check and config file properties` [./source/src/main/resources/application.properties](./source/src/main/resources/application.properties)
##
`execute file database` <br/>
Create database: [CREATE_DATABASE_DSMT.sql](./database/CREATE_DATABASE_DSMT.sql)<br/>
Insert database: [INSERT_DATABASE_DSMT.sql](./database/INSERT_DATABASE_DSMT.sql)<br/>
Create logic update database: [VIEW_PROC_FUNC.sql](./database/VIEW_PROC_FUNC.sql)<br/>

## DOWNLOAD DEPENDENCIES (LIBRARIES)
```
mvn mvn -X dependency:copy-dependencies | mvn -X dependency:get
```
## START PROJECT WITH MAVEN
```
mvn -X clean exec:java
```
`If cannot run with maven then Open main and run with java`
[./source/src/main/java/rrs/Application.java](./source/src/main/java/rrs/Application.java)

Dự án thực tập `Fastfood`
```diff
! Phần quên mật khẩu không sài `cookie`
`Nếu 2 tài khoản đăng sử dụng quên mật khẩu cùng lúc thì thay cookie vào biến code`
* 
  - B1 random code + username lưu vào cookie 
    EX 
      Cookie cookie = new Cookie("RRs_jEka4mKalsjen", 'admin')
      cookie.setMaxAge(60 * 5);
      response.addCookie(cookie);
      -- gửi code form tới email

  - B2 sau khi xác nhận từ email chuyển action tới server EX: "http://localhost:8080/forget-pass"
      bên nhận SecurityController nhận "/forget-pass" xử lý đúng -> xóa cookie || sai -> callback
```

Các chức năng cần xây dựng trong hệ thống
  - RESTful
  - Bảo mật
    + Trang riêng cho OWNER(chủ website) nắm toàn bộ quyền trong hệ thống
    + AMDIN sử lý các đơn hàng
    + SELLER: đối tác bán bán hàng
    + SHIPPER: Người giao hàng
    + BUYER: Khách hàng tham gia mua hàng

Kiến trúc MVC
Công nghệ sử dụng
  - Frontend: Bootstrap, AngularJS(1)
  - Backend: Spring-boot
  - Hệ quản trị: MSSQL (SQL Server 2019)
