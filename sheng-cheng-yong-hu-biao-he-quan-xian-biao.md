#生成用户表和权限表
###1.初始化项目
见1.5项目初始化
###2.配置参数
#####2.1新建数据库：
    #在本地数新建数据库yii2advanced 略

#####2.2配置数据库连接参数：
```
<?php
return [
    'components' => [
        //在此处配置db参数
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=yii2advanced',
            'username' => 'root',
            'password' => '',
            'charset' => 'utf8',
        ],
        'mailer' => [
            'class' => 'yii\swiftmailer\Mailer',
            'viewPath' => '@common/mail',
            // send all mails to a file by default. You have to set
            // 'useFileTransport' to false and configure a transport
            // for the mailer to send real emails.
            'useFileTransport' => true,
        ],
    ],
];
```

#####2.3配置组件authManager参数：  
```
<?php
return [
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=yii2advanced',
            'username' => 'root',
            'password' => '',
            'charset' => 'utf8',
        ],
        'mailer' => [
            'class' => 'yii\swiftmailer\Mailer',
            'viewPath' => '@common/mail',
            // send all mails to a file by default. You have to set
            // 'useFileTransport' to false and configure a transport
            // for the mailer to send real emails.
            'useFileTransport' => true,
        ],
        //在此处配置authManager参数
        'authManager'=>[
            'class' => 'yii\rbac\DbManager',
            //'class'=>'yii\rbac\PhpManager',
        ],
    ],
];
```
###3.执行命令