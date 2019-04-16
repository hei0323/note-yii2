##数据库操作

Yii2 有三种方式操作数据库：分别是yii\db\command,ActiveRecord和QueryBuilder

- ###1.yii\db\command 的使用：
    - 优缺点：高效快速简单，通用性差，不易维护，安全性差！
    - 使用：
    ```markdown
    $result = Yii::$app->db->command('SELECT * FROM post')->queryAll();
    ```

- ###2.ActiveRecord 的使用：

- ###3.QueryBuilder 的使用：
