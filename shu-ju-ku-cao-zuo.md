##数据库操作

Yii2 有三种方式操作数据库：分别是yii\db\command,ActiveRecord和QueryBuilder

- ###1.yii\db\command 的使用：
    - 优缺点：高效快速简单，通用性差，不易维护，安全性差！
    - 使用：
    ```markdown
    //使用应用主体$app 调用db主件 创建command对象来执行SQL语句并返回数组数据
    $result = Yii::$app->db->createCommand('SELECT * FROM post')->queryAll();
    //绑定参数
    $result = Yii::$app->db->createCommand('SELECT * FROM post WHERE id=:id AND status=:status')
    ->bindValue(':id',88)
    ->bindValue(':status',2)
    ->queryOne();
    ```

- ###2.ActiveRecord 的使用：

- ###3.QueryBuilder 的使用：
