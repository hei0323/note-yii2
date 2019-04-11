#Gii脚手架工具
- ####什么是gii?
GII是代码开发的辅助工具，基于web生成模型，控制器，表单等功能代码，被称为脚手架。

- ####使用：
    - 1.配置文件中开启GII
    
    - 2.打开gii页面，填写表单，生成代码
文件/yii2-app-advanced/backend/config/main-local.php
        ```
        <?php
        $config = [
            'components' => [
                'request' => [
                    // !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
                    'cookieValidationKey' => '1rNBmEkdWjPkItDN4QQEBQhmQIneCXmz',
                ],
            ],
        ];
        if (!YII_ENV_TEST) {
            // configuration adjustments for 'dev' environment
            $config['bootstrap'][] = 'debug';
            $config['modules']['debug'] = [
                'class' => 'yii\debug\Module',
            ];
        
            $config['bootstrap'][] = 'gii';
            $config['modules']['gii'] = [
                'class' => 'yii\gii\Module',
            ];
        }
        return $config;
        ```