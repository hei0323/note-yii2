#启动内置web serve 运行yii2  
- ###1.basic版本启动
```
#进入项目根目录执行命令（端口自定义） ./yii serve --port=8080
ZDYTYF@DESKTOP-NTUVM29 MINGW64 /d/website/yii2-app-basic
$ ./yii serve --port=8080
Server started on http://localhost:8080/
Document root is "D:\website\yii2-app-basic/web"
Quit the server with CTRL-C or COMMAND-C.
```
####图示如下：
![](/assets/basic.png)  

- ###2.advanced版本启动
```
#1.启动前端应用程序 进入项目根目录执行命令（端口自定义） ./yii serve --port=8081 --docroot="@frotened/web" 
ZDYTYF@DESKTOP-NTUVM29 MINGW64 /d/website/yii2-app-advanced
$ ./yii serve --port=8081 --docroot="@frontend/web"
Server started on http://localhost:8081/
Document root is "D:\website\yii2-app-advanced/frontend/web"
Quit the server with CTRL-C or COMMAND-C.
```  
###图示如下：

```
#1.启动前端应用程序 进入项目根目录执行命令（端口自定义） ./yii serve --port=8082 --docroot="@backend/web"
```