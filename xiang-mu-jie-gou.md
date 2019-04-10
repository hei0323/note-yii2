## 项目文件结构

#### 1.basic版本文件结构图:

![](/assets/QQ截图20190409154032.png)

#### 2.basic目录介绍：

```markdown
  assets/             contains assets definition 资源包，定义静态资源
  commands/           contains console commands (controllers)控制台应用程序(控制器)
  config/             contains application configurations应用及其他配置
  controllers/        contains Web controller classes web应用控制器
  mail/               contains view files for e-mails 邮件视图文件
  models/             contains model classes 模型层文件
  runtime/            contains files generated during runtime 运行时产生的日志缓存等
  tests/              contains various tests for the basic application 测试单元
  vagrant/            
  vendor/             contains dependent 3rd-party packages yii核心文件及第三方依赖包
  views/              contains view files for the Web application 视图文件
  web/                contains the entry script and Web resources 网站程序
  widgets/            
```

#### 3.advanced版本文件结构图:

![](/assets/advanced.png)

#### 4.advanced目录介绍：

```markedown
common
    config/              contains shared configurations
    mail/                contains view files for e-mails
    models/              contains model classes used in both backend and frontend
    tests/               contains tests for common classes    
console
    config/              contains console configurations
    controllers/         contains console controllers (commands)
    migrations/          contains database migrations
    models/              contains console-specific model classes
    runtime/             contains files generated during runtime
backend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains backend configurations
    controllers/         contains Web controller classes
    models/              contains backend-specific model classes
    runtime/             contains files generated during runtime
    tests/               contains tests for backend application    
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
frontend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains frontend configurations
    controllers/         contains Web controller classes
    models/              contains frontend-specific model classes
    runtime/             contains files generated during runtime
    tests/               contains tests for frontend application
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
    widgets/             contains frontend widgets
vendor/                  contains dependent 3rd-party packages
environments/            contains environment-based overrides
```

#### 5.advanced与basic区别：

其实没太大区别。yii2-app-basic只有一个web应用，而yii2-app-advanced是默认带了前台和后台两个web应用，将两个应用整合在一个project里面，然后用common应用存放一些两个应用公共的一些东西。  
  
  



