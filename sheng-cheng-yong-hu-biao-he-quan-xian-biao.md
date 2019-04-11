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
```
#执行命令./yii migrate
ZDYTYF@DESKTOP-NTUVM29 MINGW64 /d/website/yii2-app-advanced
$ ./yii migrate
Yii Migration Tool (based on Yii v2.0.17)

Total 2 new migrations to be applied:
        m130524_201442_init
        m190124_110200_add_verification_token_column_to_user_table

Apply the above migrations? (yes|no) [no]:y
*** applying m130524_201442_init
    > create table {{%user}} ... done (time: 0.519s)
*** applied m130524_201442_init (time: 0.618s)

*** applying m190124_110200_add_verification_token_column_to_user_table
    > add column verification_token string NULL DEFAULT NULL to table {{user}} ... done (time: 0.421s)
*** applied m190124_110200_add_verification_token_column_to_user_table (time: 0.468s)


2 migrations were applied.

Migrated up successfully.

#执行命令：./yii migrate --migrationPath=@yii/rbac/migrations
ZDYTYF@DESKTOP-NTUVM29 MINGW64 /d/website/yii2-app-advanced
$ ./yii migrate --migrationPath=@yii/rbac/migrations
Yii Migration Tool (based on Yii v2.0.17)

Total 3 new migrations to be applied:
        m140506_102106_rbac_init
        m170907_052038_rbac_add_index_on_auth_assignment_user_id
        m180523_151638_rbac_updates_indexes_without_prefix

Apply the above migrations? (yes|no) [no]:y
*** applying m140506_102106_rbac_init
    > create table {{%auth_rule}} ... done (time: 0.202s)
    > create table {{%auth_item}} ... done (time: 0.241s)
    > create index idx-auth_item-type on {{%auth_item}} (type) ... done (time: 0.201s)
    > create table {{%auth_item_child}} ... done (time: 0.224s)
    > create table {{%auth_assignment}} ... done (time: 0.175s)
*** applied m140506_102106_rbac_init (time: 1.052s)

*** applying m170907_052038_rbac_add_index_on_auth_assignment_user_id
    > create index auth_assignment_user_id_idx on {{%auth_assignment}} (user_id) ... done (time: 0.149s)
*** applied m170907_052038_rbac_add_index_on_auth_assignment_user_id (time: 0.151s)

*** applying m180523_151638_rbac_updates_indexes_without_prefix
    > drop index auth_assignment_user_id_idx on {{%auth_assignment}} ... done (time: 0.131s)
    > create index {{%idx-auth_assignment-user_id}} on {{%auth_assignment}} (user_id) ... done (time: 0.124s)
    > drop index idx-auth_item-type on {{%auth_item}} ... done (time: 0.193s)
    > create index {{%idx-auth_item-type}} on {{%auth_item}} (type) ... done (time: 0.124s)
*** applied m180523_151638_rbac_updates_indexes_without_prefix (time: 0.574s)


3 migrations were applied.

Migrated up successfully.
```